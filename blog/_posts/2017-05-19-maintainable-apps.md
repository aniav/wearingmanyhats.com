---
layout: post
title: "5 Common Mistakes in Developing Maintainable Apps"
description: ""
date: 2017-05-19
permalink: /5-common-mistakes-in-developing-maintainable-apps-f20de0b1bbdc/
---

Writing maintainable apps can be described as: don’t leave your t-shirt on the chair, because you will eventually have to put it back in the wardrobe… along with all the other t-shirts, trousers and jumpers, and it will require much more time and energy in the end. Your cat can also rip it in the meantime, sharpening its claws, and you will be sorry.
<!--more-->

## Apps aging like people

Over the years, I have struggled with quite a few apps you could call old. The apps had been written in various technologies, but I have found some problems that all of them shared, even though they were very different in their purpose and structure. In this article, I am going to point out some issues that make projects hard to maintain and propose tips on writing more maintainable apps.

There is a big hype for new, shiny and popular apps. The more beautiful and eye-catching a new app is, the better. I am a heavy Snapchat user, and I’ve been waiting for Prisma to come to Android, so I can say I am the last person to have any issues with novelty and innovation. But as it also happens I am one of the developers dealing mostly with technical debt and maintaining sustainable apps. Here, I am going to write about some of the things which we can do better.

Don’t get me wrong: I am not going to ask you to write perfect code all the time. We all have deadlines, we all start with a prototype, which we have to get up and running asap. We have to ship it! Most of us begin without tests because our primary goal is to bring business value to our clients. I hope we are all aware of that. We just can’t avoid some things.

## Developing maintainable apps — 5 mistakes
1. Using a excavator where you need a shovel<br>
This issue is very common. I mean VERY common. I have seen dozens of places where you could solve something by writing a few lines of code and introducing a new functionality suited to your needs. Instead, you pick a huge library, doing a lot more than you need, you spend the time to configure it and tie with your app, spending much more time in the end. Two years later, someone isn’t able to upgrade the dependencies in the project, or move to a newer version of the language used in the app because it’s blocked by that big library… which wasn’t necessary in the first place.
**Pro tip: use solutions suited to your needs, don’t overestimate or take the solutions that maybe might become useful someday. They usually won’t.**

2. Not taking future seriously enough<br>
A few years back I was working on a project where suddenly everyone got logged out from all our services, connected with an SSO functionality. It came out that somebody had set the cookie timeout for a hardcoded date in the future. They probably hadn’t even thought that their code would last for so many years, but it did.
**Pro tip: don’t use hardcoded values for dynamic data.** Always use some calculation. As for dates — it doesn’t usually take much time to calculate today+offset in most of the languages we use.

3. Throwing yourself into technical debt 100 steps at a time
If you ever come to an idea that doing a copy of a third party library inside your project and patching will do, please think again. You will either have to deal with upgrading it along with your patch inside the project — which will consume more time and effort in the future — or you will leave another developer with an unmaintainable piece of code.
**Pro tip: create pull requests to external libraries or patch them wisely without doing a copy of any third party code.** You will almost always regret it.

4. Waiting for the magical time of refactor<br>
There are times when I hear people saying they want to fix the project, but they want to wait until they are able to refactor it. Of course, there are times when you have to fix problems by refactoring, and there is no other way. Remember, though, that your duty as a developer is to fix things incrementally all the time. All. The. Time.
It is always easier to upgrade one version of an external library than to upgrade many more in bulk. You can make a refactor to clean the code out of old or unused bits, but it is more efficient to remove them as you write code.
**Pro tip: put some additional effort each time you touch a piece of code to update, upgrade and clean it.** You will also have less stress than when you make a massive refactoring, because instead of 100 things only one will explode.

5. Taking the easiest way<br>
This is a summary of all the points. If you take the easier path, you will end up regretting it later on. If you don’t restructure the code as soon as the project changes from cats to tigers, you will end up explaining the name and struggling with the inconsistency many months and years later. If you build code on top of a library no longer maintained instead of removing it, it will bite you in the future. If you don’t maintain code as you write, putting it off for later, you will never get to it. Later usually means never when writing code.
**Pro tip: always put the extra 10% of time and effort and take the harder way, you will save some money on a therapist later on.**

## Wrapping up
As you can see, I haven’t touched upon any particular technology, neither have I written about design patterns or tools to use for writing better software. That’s the whole point: writing maintainable code is about being responsible and doing the things that require more energy and effort. It’s about thinking about the project and its future as a whole. You are here to responsibly take care of the project, not write some piece of code disconnected from other parts of the project. If you take enough care now, you will thank yourself in the future!