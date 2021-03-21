---
title: "How to store git credentials in Linux"
date: 2021-03-20
draft: false
description: "Easy explanation for an unsafe way of storing git credentials and avoid password prompt"
tags: ["git", "credentials", "linux"]
author: "UniversumGames"
---

# Edit your ~/.gitconfig

Presupposing you have git already installed and setup, here is an easy way to avoid the password prompt every time you want to push a commit to a remote repository.

First things first we have to edit the `~/.gitconfig` file, the file will be mostly empty and only containing, if setup with global username and email, those information. Your config file will look similar to this

```
[user]
	name = UniversumGames
	email = programming@universegame.de
```

To setup the "credential manager" you have to copy those lines into the config

```
[credential]
	helper = store --file ~/.git-credentials
```

with these lines git will try to look for a password in the `~/.git-credentials` file. Now you are ready to add some passwords.

# Adding passwords

First you have to edit your `~/.gitconfig` file and add those lines for each username-password combination you want to add.

```
[credential "the-server-address"]
	username = your-username
```

Now we have to edit our `~/.git-credentials` file (or what you've called it in the previous step(s)), if the file does not exist, just create a new file. In the credentials files we only have to add one line for a new password

```
https://your-username:the-password@the-server-address
```

save all files and you're ready for a password-prompt free programming experience.

# Conclusion

This way of storing your git credentials is very insecure and should only be used on a private computer with decent security. All changes we've made will improve your commit experience, but can be reversed easily at any time by just returning the files to their original state. We could've done the same result with some terminal git commands, but those are rather complex, so we've just skipped the command interface entirely.
