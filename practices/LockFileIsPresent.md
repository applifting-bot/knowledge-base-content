---
slug: lockfileispresent
stages:
  - development
short_description: A practice in our DX Scanner called LockFileIsPresent verifies if your source repository contains a lock file. You should always commit the lock file to your source repository.
tags:
  - lockfileispresent
  - lockfile
  - lock file
  - package management
  - git flow
  - linting
  - dockerizing
keywords:
  - lockfile
  - lock file
  - metadata
  - repository
  - semver
  - automating installing
  - automatic configuring
---

# LockFileIsPresent

**TL;DR**

A practice in our DX Scanner called LockFileIsPresent verifies if your source repository contains a lock file. Why you should always commit the lock files to your repository? Read more!

## What Is a LockFileIsPresent

LockFileIsPresent is our DX Scanner practice that tells you if your source repository contains a lock file. Many people decide to ignore the lock files and they do not commit it to Git. What is a lock file and why should your repository contain one?

A lock file contains important information about installed packages and it should always be committed into your [Package Manager](/practices/package_management) source repositories. Not committing the lock file to your source control results in installing two different modules from the same dependency definition.

**A lock file:**

- is generated automatically for any operation
- is used for describing the dependency tree and its changes, so the coworkers are guaranteed to install exactly the same dependencies
- describes the dependency tree at any given time
- lets you "travel back in time" and check any former dependency tree
- allows your Package Manager to skip repeated metadata resolutions for previously-installed packages and, therefore, makes the installation much faster

## Why You Might Want the lock file

The package managers need more than just the configuration information - they need the exact version of each dependency installed. Remember to always commit your lock files to your source repositories!

- The lock file guarantees a consistent install across machines.
- Your Package Manager will use the lock file to resolve and install modules.
- The lock file locks the specific version, location, and integrity hash for every package
- The lock file ensures that the install creates the same version every time, no matter what device

## Issues the lockfileIsPresent Solves

- [Increased cost](/problems/increased-cost)
- [Poor code quality](/problems/poor-code-quality)
- [Meaningless work](/problems/meaningless-work)
- [Demotivated team](/problems/demotivated-team)

## How to Implement the lock file

We cannot emphasize it more - **always commit the lock file to your source repository!** And then let it do its magic.

## Common Pitfalls of the lock file

- The lock file is being ignored
- The lock file is not committed in the source repository
- The lock file is rewritten by hand and it can lose its functions

## Resources for the lock file

- npm: [npm-package-lock.json](https://docs.npmjs.com/files/package-lock.json)
- yarn: [yarn.lock](https://yarnpkg.com/lang/en/docs/yarn-lock/)
- medium: [Everything You Wanted To Know About package-lock.json But Were Too Afraid To Ask](https://medium.com/coinmonks/everything-you-wanted-to-know-about-package-lock-json-b81911aa8ab8)
- snyk: [Do you really know how a lockfile works for yarn and npm packages?](https://snyk.io/blog/making-sense-of-package-lock-files-in-the-npm-ecosystem/)