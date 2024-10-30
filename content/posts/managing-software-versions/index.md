---
title: "Managing Software Versions"
date: 2024-10-30T18:05:07+08:00
draft: false
---

### Why do we need to manage versions?

This is so that it can be easily communicated to the users that:

- There are new changes that improve the software or address feedback given by the users.
- There are new changes will impact the way the users interact with the software.
- The users can test the new changes in the upcoming version of the software.

### How can we manage versions?

By combining tools and processes, it can improve the experience of releasing new versions of the software.

1. Use semver (semantic versioning). That means:

   **Major** (**x**.0.0): Indicates there are breaking changes (non-backward compatible), e.g: Changing a parameter of an existing function

   **Minor** (0.**x**.0): Indicates there are new functionality with backward compatibility introduced to the software.

   **Patch** (0.0.**x**): Indicates there are backward compatible bug fixes introduced.

2. Use changelogs to highlight what is introduced from version to version.

3. Use CI/CD tools and workflows to automate processes where available. One example is changesets, where it helps people declare how changes will be released from versioning to publishing the software.

### Conclusion

When it comes to releasing software, it's important to have a transparent process that keeps users informed of what is coming. Hence, ensuring that this process runs properly becomes an even more critical task for software developers. Leveraging tools to accomplish this goal is a worthwhile endeavor while the software is still in its early stages.
