---
title: "Using XCode with CI/CD"
date: 2022-05-23
draft: true
description: "How you can use an XCode installation with a local Gitlab Installation"
tags: ["ci/cd", "automation", "xcode", "gitlab, "gitlab-runner"]
author: "UniversumGames"
lang: "en"
---

- [Introduction](#introduction)
  - [Warnings for this tutorial](#warnings-for-this-tutorial)
- [Prerequisites](#prerequisites)

# Introduction

This extract will be a simple introduction for setting up an CI/CD Pipeline for XCode with Gitlab and Gitlab-Runner. Of course it's really easy to just cut out Gitlab and use your own CI/CD Tool. When using a different Toolchain it's important that this Tool can run shell scripts on the Mac Machine you want to use.

## Warnings for this tutorial

This introduction and explanation for setting up a CI/CD Toolchain for XCode is using the main development machine by running local shell scripts as the user starting the gitlab runner (probably your main user) which is a huge security concern and is not recommended for 24/7 use on a large GitLab server with many Admins. This way other parties can gain access to your machine.

# Prerequisites

-   you already know what CI/CD is (for German readers there is an article about this from us [An Introduction to CI/CD (German)](/posts/cicd))
-   legit MacOS installation which you use for development
-   an iOS or similar App you compile and own the App Store signatures (when uploading your App yourself the keys are on your device)
-   XCode and XCode Commandline Tools installed (`xcode-select --install`)

When using Gitlab and Gitlab Runner:

-   Gitlab installation with admin access
-   Native installation of the Gitlab Runner on your Mac ([GitLab Doc for installation on macOS](https://docs.gitlab.com/runner/install/osx.html) or the easy brew installation: `brew install gitlab-runner; brew services start gitlab-runner`)
-   the runner is ready for use and is installed not as docker runner but as shell executor (see [Setting up Gitlab Runner on MacOS](https://docs.gitlab.com/runner/configuration/macos_setup.html))

Only important when uploading to App Store Connect:

-   you have successfully uploaded a version of the App manually to AppStore Connect
