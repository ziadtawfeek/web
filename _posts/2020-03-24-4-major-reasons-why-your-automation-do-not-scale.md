---
layout: post
title:  "4 Major Reasons Why Your Automation Don't Scale!"
author: "Ziad"
comments: false
---

## 1. If tests go well, you always question if you are doing it right. If everything doesn't go well, you spend a lot of time to fix it

You know when you have a great automation architecture that you release fast and often, the team is not stressed and releases go smoothly. You release and boom, you need to release a hotfix for a crash. So what do we learn from this? You might be doing an anti-pattern.

#### What many teams do?
[![What many teams do](https://i0.wp.com/saeedgatson.com/wp-content/uploads/2015/10/softwaretestingicecreamconeantipattern.png "What many teams do")](https://i0.wp.com/saeedgatson.com/wp-content/uploads/2015/10/softwaretestingicecreamconeantipattern.png "What many teams do")

#### How it should be done?
[![How it should be done?](https://watirmelon.files.wordpress.com/2018/02/ideal-automated-testing-pyramid.jpg "How it should be done?")](https://watirmelon.files.wordpress.com/2018/02/ideal-automated-testing-pyramid.jpg "How it should be done?")

------------

##  2. Although you automate 100% of what could be automated because you believe manual testing sucks. You aim to catch bugs, provide fast feedback and release confidently but this DOES NOT PREVENT BUGS.

Great tests are designed about how to approach a testing problem, then figure out what’s suitable for automation, and what’s not suitable. Nevertheless, finding the automation line can be a tricky business. Test automation is just one tool from our tester toolbox that we can use to solve a specific set of testing problems. You need to work on how to prevent bad code from getting in your production code, make use of a static analysis code to check for code smells.

[![Code Smells](https://lh3.googleusercontent.com/proxy/BOIhnmo00hg0S8xIZFYLRualb1w_8xCdwa6ha6yutEoPk0cINOAMvYjpnjkdYW4LWTpqHicPYLAntpxmkE3yQYwWY62hhARaar2FhGZhGxo30geaXUkPrkWtI2lp5CNKiPaG6w0RaOyXALqWNcgaly4bXUpRmnIii1Y "Code Smells")](https://lh3.googleusercontent.com/proxy/BOIhnmo00hg0S8xIZFYLRualb1w_8xCdwa6ha6yutEoPk0cINOAMvYjpnjkdYW4LWTpqHicPYLAntpxmkE3yQYwWY62hhARaar2FhGZhGxo30geaXUkPrkWtI2lp5CNKiPaG6w0RaOyXALqWNcgaly4bXUpRmnIii1Y "Code Smells")

------------

## 3. 10K automated tests are better than 0 automated tests. Maybe that's right but are they flaky?

Flaky tests are worse than no tests in my opinion and you should attack it once faced, that's should be everyone's priority or it could be moved to the backlog for the next 2 years! Assume a zero-tolerance culture on flakiness.

------------

## 4. Code coverage may be queen but test design is KING!

Basic verification that would be hit by anyone walking through the basics of the application isn’t worth much to me.
However, if your automation takes advantage of automation – meaning that loops, randomness, input variations, and loads of other ideas are part of the automation approach.
