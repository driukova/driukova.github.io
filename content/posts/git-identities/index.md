---
title: "Multiple Git identities on a single machine"
date: 2020-12-03T08:06:25+03:00
description: How to configure multiple Git identities on a single machine
# text on card
summary: A Git identity is a pair of username and email address associated with your commits. To keep apart commits to your personal and job projects, configure several identities.
menu:
  sidebar:
    name: Configure Git identities
    identifier: git-identity
    weight: 10
---

> This article is not complete yet. Just testing a customized template.

A Git identity is a pair of username and email address associated with your commits. To keep apart commits to your 
personal and job projects, configure several identities.

The right way to configure several Git identities on the same machine depends on where your target repos are hosted. 

### Different hosting services

If the target repos are stored on different hosting services (e.g., GitHub and GitLab), you can configure separate identities 
and use the same SSH key for both of them.

#### Git lookup order

Git allows you to configure settings on several levels: the system level, the global (user) level, and the local (repository) level.

![](/posts/git-identities/img/config-levels.png)

Git reads config files in order from the system level to the local level. The next level settings override the previous ones. 
So values in the local config file apply to the specific repo instead of global values. 

Changing the higher level settings does not affect repos with local config files.

#### Global settings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

```console
$ git config --global user.name "Zaphod Beeblebrox"
$ git config --global user.email "beeblebrox@example.com"
```

To see your current settings, and the config file location, execute the command:

```console
$ git config --list --show-origin
```

#### Single repo settings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

#### Several repos settings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

### Same hosting service

If the target repos are stored on the same hosting service (e.g., GitHub), in addition to configuring different accounts you need to 
indicate separate SSH keys for each of them.

