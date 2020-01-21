---
layout: post
title:  "Things I learned at TestBash Munich 2018 #OKTOBERTEST"
author: "Ziad"
comments: false
---

**TL;DR** **TestBash Munich** was awesome! the talks and the people were well worth it and **Open Space** was even better than I thought it would be. Only 3 talks left (to be updated). Also, Thanks to [**Instabug**](https://instabug.com/) for making it happen!

**&hellip;**

Okay, let’s do this. I don’t know if I mentioned beforehand but this would be my first time sharing an experience through a blog, I will try to make it a good one!

I have been following [TestBash](https://www.ministryoftesting.com/events) events for some time now and a couple of weeks ago, I got to experience my first ever TestBash at Munich!

# What’s so special about TestBash?

It’s a conference where the testing community meets and discusses several topics. The conference format usually a two-day event (could be more):

1. **Day One**: Line-up of **selected speakers** to talk about anything **testing.**

1. **Day Two: Open space** which is a free-structured where anyone can write down any idea or a topic to discuss, share or learn and everyone gets to vote according to their preference. (It was awesome!).

# Interesting, how did it go?

First, there was a meetup that is custom before and after the conference, I arrived in Munich and straight away got to attend the Pre TestBash hosted at [**QualityMinds GmbH**](https://qualityminds.de/en). The meetup was a chance to say hello to the speakers and the attendees and get people into the spirit of TestBash.

For an introvert, meetups might be overwhelming and networking functions maybe naturally stressful.

![](https://cdn-images-1.medium.com/max/1000/1*BgjLsToiW2B0knuFlKazaA.gif)

Once I arrived, everyone was so inviting and after some time, I felt relaxed and enjoyed a lot of conversations for the rest of the night.

# Conference Day

It included a line-up of 9 talks and I will point out my take on some of the talks

# Doubt builds trust — [Elizabeth Zagroba](https://twitter.com/ezagroba)

Elizabeth focused on **interviewing and hiring**. We always need to find out what candidates bring to the table and whether you will be able to build trust in them to get things done in a **very short interview time span.**

She illustrated the definition of **trust** and **distrust** according to [The Thin Book of Trust](https://www.thinbook.com/the-thin-book-of-trust/).

![](https://cdn-images-1.medium.com/max/6072/1*mv7PfBmOOGJKZ0ix1JoiyA.jpeg)

Try to understand them. So the thing that might help was to **sit on the same side of the table as the candidate** — and **pair test with them** on an application. She also presented **Frances Frei **pillar**:** **Authenticity**, **Logic,** and **Empathy **and provided points like:

- Encouraging the candidates to be themselves (it’s okay not to know everything and some areas can be taught).

- She was looking for candidates to identify problems and whom that might affect, or to whom might be relevant for (it’s fine if people didn’t know who to get to exactly!).

- The best thing candidates may ask “Is this what you had in mind” when an area of the website was taking a very long time to load. Expressing this kind of doubt meant being authentic.

I really liked the reasoning points, the great stories illustrated and I agree that doubt helps us becoming better testers.

# Storytelling and Software Testing — [Christian Vogt](https://twitter.com/EisUndDamp)

Christian started by showing pictures: some of them are of films or just pictures. And instantly, we aren’t just seeing the picture, but remembering or imagining the story behind them. **Facts with a story help us to remember them**. Stories also put us in the situation of a participant which makes us able to experience things, it sticks!

![](https://cdn-images-1.medium.com/max/6072/1*Lj6XcQN7DcCKOkymE5I6uA.jpeg)

**To get to software testing**: our customer can be the hero. The call to adventure is to use the software. What does that journey then look like for them? I was confused at first while listening to Christian’s talk and after some reflection, I found out that **testers are always providing facts with a storytelling context in an everyday job** (e.g. What caused this bug? How to reproduce a bug? How might that affect the user?).

He also encouraged to use storyboards where each little picture helps to tell a user journey.

# Testing for Purpose — [Ravneet Kaur](https://twitter.com/ravneetkj)

We do need purpose. Ravneet asked why we develop software at all?. Answers are **“to solve a problem”** or **“to make people’s life easier”**.

She summed up: we’re trying to change the world for the better. And yet, a lot of the time we end up developing products and features that no one wants. She mentioned the **well-known figure of 65% of features not being used** most of the time citing examples of failed projects (e.g. [Google Glass](https://www.youtube.com/watch?v=4EvNxWhskf8), [Juicero](https://www.youtube.com/watch?v=X1oHp-VvhDE), etc…)

So how do we avoid making products and services that no one wants? **We need a culture of experimentation**. Software development is inherently uncertain. We make plans, have long meetings. And these plans and meetings are inconclusive. We should be out there experimenting and testing.

How can we create a culture of experimentation? There are three questions:

- Should we build it? Does it matter?

- Is it usable?

- Does it break?

The first two questions are quite tricky but the answer is **Minimal Viable Product**. This surely doesn’t have to be a v1.0, it doesn’t have to contain a single line of code. It was really enlightening to talk and I could definitely relate to that. I have previously worked in a product where most of the features aren’t used and eventually it became obsolete.

# How to Scale Mobile Testing Across Several Teams — [Daniel Knott](https://twitter.com/dnlkntt)

Daniel is a well-known mobile expert, speaker at various conferences in Europe and this was my favorite talk 🤓 He talked about the **history of mobile technology, how did it change our life?** and how companies like [**_XING_**](https://www.xing.com/en) had to develop strategies to keep up the pace. He mentioned the challenges they were facing in scalability. The pace of development from the web teams just couldn’t be matched by the mobile teams and once the mobile usage exceeded web hits, the company needed to come up with a new initiative — mobile unleashing but there were more challenges along the way.

First thing is to get away from “web thinking”, and the next problem was “hiring”, communication was also an overhead challenge. The pace of development means that a lot needs to be clarified. (e.g. Face to face, Slack, Github — whatever channel) and it’s just not possible to just “rollback” a mobile app once it’s shipped. With so many teams, so many challenges like the above, they introduced **Release Trains **which meant planned code freezes, fixed dates, so the train is always on time, if you missed the train, the feature doesn’t go live!

![Release Train](https://cdn-images-1.medium.com/max/6072/1*z-6qg9D2eLcW0ziNNoqvbw.jpeg)

He then gave a walkthrough about some of the challenges faced in test automation, how they overcame it by migrating from Espresso & Keep It Functional to Calabash and release process.

![Build Pipeline](https://cdn-images-1.medium.com/max/6072/1*V9Nd8e35XAtPIgt3JlQgwg.jpeg)

It was an awesome talk, most of the challenges mentioned I could relate to and we happily overcame most of those challenges at [**_Instabug_**](https://instabug.com/). 💪

# Testing in Production: Anti-pattern or Future? [Lukasz Raslonek](https://twitter.com/testdetective)

Disclaimer: Something controversial is coming! This was an insightful topic, I have learned ways how to expose your environment and get rapid feedback on how your services work.

Obviously, Lukasz is not talking about **someone who only checks if anything works once it’s released**. it’s a bit more than this. It’s about **why would you want to test in production?** after all, customers use the product in the production environment!

![](https://cdn-images-1.medium.com/max/6072/1*0ZGAkcbxCN8UVcn5lFwNcw.jpeg)

Lukasz’s first reason is distributed systems. Creating a test system for that is difficult and expensive. Consider **_Netflix Service Oriented Architecture._**

![](https://cdn-images-1.medium.com/max/1280/1*LQzPd12M_DHJQRAR1y2a4g.png)

The more complex and distributed your architecture is, the harder it is to maintain your test environment. It’s all fine and well the plenty of test scenarios covered but **there are some situations when you can’t know in advance all the scenarios happening in your production environment**. He then used the word which I really like **“Unknown unknowns”. **If you are into this word, you can google [**The Five Orders of Ignorance]\*\*(https://www.researchgate.net/publication/27293624_The_Five_Orders_of_Ignorance).

It’s like driving a car no matter how an expert in your navigation, there’s always something unpredictable that can happen. Lukasz also gave a walkthrough on how to tackle it.

- The first approach is the **Canary Testing**. When we deploy a new version, we keep the stable version in production too and only divert a small amount of traffic to the new version. We minimize the risk of problems being wide-reaching in this way. (e.g. [Facebook](https://code.fb.com/web/rapid-release-at-massive-scale/) uses New Zealand a testing location to analyze logs and metrics to decide whether a feature to be kept or not).

- The second approach is **Chaos Engineering**. This will test the high availability of the production environment by introducing deliberate errors. (e.g. Netflix created a tool “[Chaos Monkey](https://github.com/Netflix/chaosmonkey)” that shuts down or reboots random production servers).

- The third approach is **Test Automation**. It’s not a luxury anymore, you may implement test suites in your pre-production environment but it would be also a good idea to execute a smoke test suite in production to ensure that the core features are still operational. On top of that, it’s a way of creating metrics, it’s better to have data of the peak hours and non-peak hours for your services.

Production is not predictable, it’s always unexpected and that’s why we should have different ways of testing and monitoring.