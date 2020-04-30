---
layout: post
title:  "Flaky Tests Explained: Why it happens and What should we control?"
author: "Ziad"
comments: false
---

[![](https://images.unsplash.com/photo-1444427169197-de497742b62d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=4800&q=80)](https://images.unsplash.com/photo-1444427169197-de497742b62d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=4800&q=80)

An important assumption of regression testing is that test outcomes are deterministic: an unmodified test is expected to either always pass or always fail for the same code under test. Unfortunately, in practice, some tests—often called flaky tests*—have non-deterministic outcomes. Such tests undermine the regression testing as they make it difficult to rely on test results.

*flaky means unreliable.

Some approaches I have seen to tackle flaky tests are rather not good enough. The most common approaches I have seen:

1. **Run a flaky test multiple times** , and if it passes in any run, declare it passing, even if it fails in several other runs. For example, the process we have at my most recent employer, a failing test is rerun at least 3 times against the same code version on which it previously failed, and if it fails in an of those 3 reruns, **it is labeled as a flaky test**. Some open-source testing frameworks also have annotations (e.g. Android has **@FlakyTest**, Jenkins has **@RandomFail**) to label flaky tests that require a few reruns upon failure.
2. **Remove flaky tests from the test suite**, or to mentally ignore their results most of the
time (in the limit, ignoring the failure every time is equivalent to removing the test). In **JUnit** the **@Ignore** annotation is used to exclude a test from the test suite to be run. Needless to say this is a very dangerous approach and an invitation to miss out bugs on your codebase and it spreads low-confidence on the tests among your team!

The thing is not any of the above approaches really address the problem or root causes of flaky tests, it's mostly workarounds and some mitigation patterns to keep the wheel running.

**Flaky tests root causes:**

1. Occasionally flaky tests are resulted either from the application codebase or the first time it was written
2. Synchronization between tests, actions inside each test account for a relative percentage for test flakiness
3. Test Order Dependency  where tests are dependent on each other during execution
4. Concurrency and threading where tests use background and main threads which sometimes produce some unpredictability among the tests
5. Memory leaks, time and IO operations could also be an issue

**How should we fix causes of flaky tests?**

There is no perfect solution or one size fits all but you can start with the following:

1. **Synchronization**: address the order violation between different threads or processes in the application under test
2. **Concurrency**: introduce asynchronous processes if you can without affecting codebase to ensure tests are supposed to be accessed by one thread at a time and make processes in test more deterministic.
3. **Network**: the best fixes for this category is to use mocks. Whenever the use
of mocks is non practical, fallback to synchronization
4. **Randomness**: always run tests in random order, include random data within your tests as well but don't let it be unpredictable in your tests.

**There is still flaky tests, how should we deal with that?**

Again, no perfect solution here but you can try the following:

- **Run until it passes!**
- **Quarantine and fix** (e.g. mark down flaky tests as you go, quarantine it and once you have the chance go fix them!)

Let’s keep the conversation going! Do you have any interesting flaky test stories? What is your team’s approach for dealing with the problem?

**References:**

- [CircleCI: Using Insights to Discover Flaky, Slow, and Failed Tests](https://circleci.com/blog/using-insights-to-discover-flaky-slow-and-failed-tests/)
- [Eradicating Non-Determinism in Tests by Martin Fowler](https://martinfowler.com/articles/nonDeterminism.html)
- [Google Testing Blog: Where do our flaky tests come from?](https://testing.googleblog.com/2017/04/where-do-our-flaky-tests-come-from.html)
