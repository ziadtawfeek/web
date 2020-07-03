---
layout: post
title:  "Android UI Tests on a CI"
author: "Ziad"
comments: false
---


## Why do we need this?

- A CI/CD pipeline is a software build and delivery process where changes go through sequential steps to build, test, and deploy. They both serve as **mistake-proofing process** and as **a feedback mechanism**.
- Even more broadly, a pipeline can be modeled as the following which is a directed graph with finite nodes and no cycles. Each step in the build process is a node(circle), and the directed edges(connections) lead the code to its next sequential step.

![https://fastersafely.com/images/pipeline_1.png](https://fastersafely.com/images/pipeline_1.png)

## Back Story

3 years ago when I was developing **UI Tests** for Android apps, it was challenging to integrate these tests on CI and include it on pipeline (Specifically talking about UI Tests using Espresso). So, we covered only Unit Tests & Integration Tests.

Here are the challenges we encountered especially if you are part of a small team:

1. The pipeline we used included **CircleCI**, it was painful to make it work with because **[x86 emulators are not supported](https://www.reddit.com/r/androiddev/comments/7hsar5/has_anyone_been_able_to_run_espresso_tests_in/)**, and running ARM emulators is way too slow to be useful.
2. Setting up and managing an **[in-house device farm](https://bughuntersam.com/setting-up-a-homemade-charging-station/)** is **expensive** and requires long-term investment and on-going infrastructure support - **not a viable option for most teams especially if you are a small one**.
3. Cloud-based device farms such as **Firebase Test Lab** are a much more cost-effective solution for most teams as they take care of managing the infrastructure while offering simple APIs for integrating with existing CI pipelines. However, if you are willing to spend 💰💰💰💰 then go for it. But if you need a reasonable price with a large number of tests, you might need to consider something else.

## Pre-requisites

We need to have these checkboxes on our environment to run in a CI:

[ ]  Supports configuring the Android Emulator system images used - API level, target: (default or google_apis), arch / ABI (x86 or x86_64).
[ ]  Supports running modern x86 and x86_64 based emulators with **hardware acceleration (KVM) enabled** for better performance.
[ ]  Provides enough RAM for running both **Gradle** and an instance of **Emulator**.

## What tools check these boxes?

### [1. Bitrise](https://www.bitrise.io/)

- Bitrise provides an **Android Build for UI Testing** and **Virtual Device Testing** for Android steps that use **Firebase Test Lab** to run tests for the chosen module/build variant with no limit on device hours / no. of test executions.
- What I like about Bitrise how easy you can set up your workflow using their **Online Workflow Editor**. It makes your life easy instead of configuring your own `YAML` file like this

<script src="https://gist.github.com/ziadtawfeek/fd775a57e799a01917688776be25cbb3.js"></script>

to this ⤵️

![https://raw.githubusercontent.com/ziadtawfeek/web/master/assets/bitrise-workflow.png](https://raw.githubusercontent.com/ziadtawfeek/web/master/assets/bitrise-workflow.png)

After getting this to work, you will get something like this ⤵️

![https://raw.githubusercontent.com/ziadtawfeek/web/master/assets/bitrise-summary.png](https://raw.githubusercontent.com/ziadtawfeek/web/master/assets/bitrise-summary.png)

### Conclusion:

- **Easy setup, a great tool for iOS & Android, Great Support**  are the top reasons why you should use Bitrise.
- **Just be careful that when you are relying on a platform** and ecosystem makes it harder to port pipelines to potentially better alternatives in the future

### [2. GitHub Actions](https://github.com/features/actions)

- GitHub recently added support for CI/CD and is free for public repositories. As a result, many open-source projects on GitHub are starting to migrate their CI/CD workflows to GitHub Actions which has integration with GitHub itself and **strong infrastructure support from Azure.**
- Looking into their [virtual environments reference](https://docs.github.com/en/actions/reference/software-installed-on-github-hosted-runners#android). They don't support a [hardware-accelerated emulator](https://github.com/actions/virtual-environments/issues/836#issuecomment-624574235) within a docker container on a Linux / Ubuntu VM but they offer macOS machines, and these macOS VMs ticks our checkboxes.
- But we will need to install and configure Android SDK components, create a new instance of an AVD, launch the emulator and run the tests via Gradle.
- Luckily for us, there's a [Custom GitHub Action](https://github.com/marketplace/actions/android-emulator-runner) on the marketplace that helps us to do that.
- A major feature that GitHub Actions brings, that you can test multiple versions of an application in parallel using **[Matrix Builds](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions)** which lets you, for example, test three different versions of Android APIs at the same time. Because GitHub Actions are defined in a basic YAML file, making those changes is only a matter of adding a few lines to the file.

After getting this to work, you will get something like this ⤵️

[![](https://raw.githubusercontent.com/ziadtawfeek/web/master/assets/github-actions.png)](https://raw.githubusercontent.com/ziadtawfeek/web/master/assets/github-actions.png)

### Conclusion:

- **Open-source friendliness**, **Integration with many tools** and **Community Support** why you should use **GitHub Actions**.
- As we run the workflow directly a macOS VM, not a Docker container to overcome the HAXM. We are missing out on some runtime optimization and as tests increase, time will increase. It also remains to be seen how easy to migrate from **GitHub Actions** to other CI/CD providers in the future.
