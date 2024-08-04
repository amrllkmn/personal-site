---
title: "Building a Dropbox Clone"
date: 2024-08-04T21:32:49+08:00
draft: false
series: ["Dropbox Clone"]
series_order: 1
---

> I'm building a Dropbox clone and I'm laying down the rules of how it will be built.

Hello folks, before we get started, let's just get it out of the way: I got burnt out on writing these blogs, plus I was hit with an unexpected bill on AWS for the last project, which put a damper on the entire series. Then, I got a job, built and deployed another project (a note-taking app) but was still burnt out on writing, so no blog series on that one. However, I realized I missed out on a lot of value by not writing what I've learned from the second project.

So this is a redemption arc, a comeback one might say. I'm making a third clone project. This time, I'm building a Dropbox clone.

One might ask, "What's different this time?"

To that I say, "This time, the only guarantee that I'll make is that you'll get a heads up when I'm quitting the project."

Here are the early decisions I'm making for the Dropbox clone:

**The stack:**

- Rust as the backend
- PostgreSQL as the DB
- Svelte as the frontend

**What it should do:**

- Authentication/Authorization
- Upload file(s)
- Rename file(s)
- Create folder(s)
- Rename folder(s)
- Delete file(s)/folder(s)
- Download file(s)/folder(s)
- Scan file type(s)
- Handle filtering by type(s)
- Limit file size
- Show storage usage
- Generate shareable links

**What it won't do:**

- Have a mobile-friendly design
- File previews
- Cancelling mid-uploads
- Sync to local folder directory

It's a long list, so we'll tackle it slowly. From backend to frontend. Buckle up folks, we're so back.
