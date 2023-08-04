---
title: "Hello World"
date: 2023-08-03T21:56:16+08:00
draft: true
summary: I got a simple Rust web server up and running.
tags: ["rust", "webdev", "backend", "actix-web"]
series: ["Rebuilding in Rust"]
series_order: 2
---

> TL;DR: I got a simple Rust web server up and running.

## First steps
I bit the bullet and chose Actix Web to build the web server. It was pretty straight forward. I first installed the Actix Web crate and then I followed the [Getting Started](https://actix.rs/docs/getting-started/) guide on the Actix Web website. I then followed the guide to get a simple web server up and running.

At the of the guide, you should have this:

![Rust Server](rust_server.png)

Then, run `cargo run` on your terminal and go to `localhost:8080`. You should see the "Hello World" message:

![Hello World](hello_world.png)

## Next steps
Now that we got a simple hello world server running, this should be a good place to stop for now. I'll be back with more updates soon.