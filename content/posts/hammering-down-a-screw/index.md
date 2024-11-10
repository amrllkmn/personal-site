---
title: "Hammering Down a Screw"
date: 2024-11-10T10:55:16+08:00
draft: true
---

Lately, I've been struggling with my side projects. I've made several, and I'm proud to have built something. But after some time, I'm starting to wonder this question: "Am I just trying to hammer down a screw?"

The reason why I came to this question is because, flashback to two years ago, all I knew was Ruby and Javascript. I thought I knew enough about it, or at the very least good enough for the job. But there was this nagging feeling that I was missing out on what other technologies could teach me. So I thought, maybe I should try something out. Take a challenge.

I chose Rust. And I stuck with it. Like _really_ stuck with it.

At first, it was going great. I built a URL shortener. Then a note-taking application. Each project taught me something new about ownership, borrowing, and thinking in Rust. Sure, they were mainly Rust backends with Javascript frontends, but I was learning. I was growing.

Then I hit a wall.

I wanted to build something with authentication – a _seemingly_ reasonable next step in my Rust journey. But here's where it gets messy: the auth solutions I trust (Clerk, Auth0) don't have Rust SDKs. The Rust auth libraries that do exist don't give me the confidence I want. And building auth from scratch? That's a whole different kind of project that I'm not ready to tackle.

So now I'm stuck in this weird limbo: Do I compromise on my goal of building more things in Rust? Do I compromise on using the auth solutions I trust? Do I compromise on what I want to build?

Hence, the question comes back: Am I just hammering down a screw?

The idea was to get better at Rust, but that itself became the problem. I was forcing every solution to use Rust, even if it didn't need to be. It's the classic "Golden Hammer" anti-pattern, but with a twist – I _know_ it's not always the right tool, but I want to use it anyway because I want to get better at it.

I reached out to someone who I consider a great engineer about this dilemma. Their advice was pragmatic:

> I wouldn't use the same language for all of them. For example the full stack projects might suit JavaScript, whereas implementing Docker better suits Go or Rust. It depends why you're doing them - if it's to learn Rust, cherry pick the projects that suit it. If you want to learn how to do a specific project, then pick a suitable language you know and learn how that project/tech works.

It's good advice. Logical advice. But it doesn't quite scratch the itch of wanting to push through these limitations specifically to get better at Rust. It's the tension between pragmatic learning ("learn the right tool for the job") and determined mastery ("get really good at this one thing"). Or in a different analogy: "painting with a brush in your hands" vs. "painting with a brush between your toes". You'd be impressed if someone painted something with their toes right?

After some reflection, I realized what's really going on here. There are people that I look up to – people who, in their spare time, build cool stuff. I wanted to be like them. I wanted to be better. And I thought being better meant having more tools under my belt. Or doing something the hard way.

But maybe this frustration – this tension between what I want to build and what I can practically build with my chosen technology – is itself part of the learning process. It's teaching me something about ecosystem maturity, about the trade-offs of choosing less mainstream technologies, and about the difference between learning a language and building with it.

I'm still not sure what the right answer is, to be honest. But I do know one thing:

I'm going to start learning Golang 🤡
