---
title: "Adding Authentication"
date: 2024-08-05T18:22:09+08:00
draft: true
series: ["Dropbox Clone"]
series_order: 2
---

> TL;DR: I want only authenticated users to be able to use the app, so I'm building an authentication feature

## Context

So for the Dropbox clone, I want to ensure that only verified users are allowed to interact with the API. Hence, I need to build an authentication service to wrap around the APIs I'll be building.

## What needs to be done

For this feature, I need to:

- Create a database for the app
- Create a table for users
- Create a dummy endpoint to test authentication

I've decided to use OAuth, as I don't want to manage our users' credentials. Plus, if I were to go with the email/password route, I'd need to implement password reset and email verification flows. With OAuth, the responsibility of securing and validating the users' credentials falls on the third party.

## The pros and cons of OAuth

### Pros:

- It will take less time to develop a solution
- Simplifies the login and registration process
- Offloads credential security to a trusted third party
- Better user experience as they can just use an existing, verified account to access the app

### Cons:

- Reliance on a third-party provider
- No control if there are outages
- Access tokens and communication with the third party need to be managed
- If a user has no Google account, they won't be able to access the app

Now that's out of the way, let's build this thing.
