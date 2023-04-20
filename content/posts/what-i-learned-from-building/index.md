---
title: "What I Learned From Building"
date: 2023-04-20T14:58:35+08:00
draft: false
tags: ["app", "building", "problem-solving", "deploying","project management"]
summary: Why you should try building an app. It's cool. Really.
---

> TL;DR: Building your own apps help you learn how to manage projects, pick up new skills, and even sharpen your problem solving skills.

You can learn a lot from building and deploying an app. I just finished building a URL shortener web application with Rails and Next.js (it's currently [live](https://url-shortener-ui.vercel.app/)). Looking back, I realised that I came out of the project with a few key takeaways that are very valuable to a software engineer. I'd like to share them with you guys:

## Project management
When you're building a project on your own, you're going to be planning a lot. You're the lead, the senior, the product manager, and your own junior. This means you'll be deciding the MVP, the stack, the architecture, the design, and the user experience. Throughout the project, you'll learn whether what you planned out initially works, or do you need to readjust the goal. From my experience in this project, I ended up having to add more columns in my backend service because I realised having the app show the title of the target URL is important for users to have. So I had to go back and quickly add migrations to resolve this issue. I could've shipped it out faster if I took the time earlier to think about the UI design and how the API should integrate with it. This would've saved me time in developing the app. Nonetheless, project management is a great skill and it translates well into your work as you can better estimate your timelines for your tasks or your side projects based on your experiences.

## New skills
When building your own app, you will find resources that you incorporate into the app. This means either a new library, a new method, or best practices to approach your project. For example, on this project, I learned 2 things in my Rails backend service:

```ruby
# app/models/url.rb
class Url < ApplicationRecord
    before_validation :generate_slug
    validates_uniqueness_of :slug
  
    def generate_slug
        self.slug = SecureRandom.uuid[0..5] if self.slug.nil? || self.slug.empty?
        true
    end
```

I learned that Rails has a uniqueness validator and that I can run functions like `generate_slug` right before the validation. This was so cool, it allows me to write simpler code knowing that Rails will handle the validation on saving a record.

Besides that, I learned about stubbing and mocking. Stubbing is when you return a canned response in place of calling an external service. Mocking is when you _mock_ that external service and perform assertions as to how the service was called.

These things are extremely valuable to learn and would serve me well in my next project. Hence, building on your own closes the technical gap between you and the next level in your career.

## Problem-solving
In our projects, there will always be some roadblocks. Eventually, we will find a way to resolve it. And problem solving is the key skill that will benefit from building your own apps. Also, it feeds back onto the first two takeaways as you will find solutions that require new techniques or just work around it till you can resolve it at a later date (without compromising user experience or security). Both are valid options to achieve your goals. I've never deployed an app before, so I wanted to ship the app as fast as possible so I went for a platform that had minimal configurations to deploy. Obviously, problem-solving is a great skill to cultivate that will pay off dividends throughout your time as a software engineer.

## Conclusion
I think the tech influencers out there might have a point when they talk about building your own projects. In an industry where frameworks get out of date really fast, it's important to stay on top of things. You get to keep your skills sharp and might even add some new ones to your toolbox.