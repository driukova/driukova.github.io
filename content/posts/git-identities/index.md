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
    weight: 20
---

> This article is not complete yet. Just testing a customized template.

A Git identity is a pair of username and email address associated with your commits. To keep apart commits to your 
personal and job projects, configure several identities.

The right way to configure several Git identities on the same machine depends on where your target repos are stored. 

### Different repository services

If the target repos are stored in the different repository services (e.g., GitHub and GitLab), you can configure separate identities 
and use the same SSH key for both of them.

#### Git lookup order

Git allows you to configure settings on several levels: the system level, the global (user) level, and the local (repository) level.

![](/posts/git-identities/img/config-levels.png)

Git reads config files in order from the system level to the local level. The next level settings override the previous ones. 
So values in the local config file apply to the specific repo instead of global values. 

Changing the higher level settings does not affect repos with local config files.

#### Global settings

The global settings are specified for a single user during the first time Git configuration and can be changed with the same command:

```console
git config --global user.name "Zaphod Beeblebrox"
git config --global user.email "beeblebrox@example.com"
```

To see your current settings, and the config file location, execute the command:

```console
git config --list --show-origin
```

#### Single repo settings

To specify separate Git identities for a single repo, run the command in your project directory:

```console
git config  --local user.name "Zaphod Beeblebrox"
git config  --local user.email "beeblebrox@example.com"
```

The `--local` option is default and can be omitted.

#### Several repos settings

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

### Same repository service

If the target repos are stored in the same repository service (e.g., GitHub), in addition to configuring different accounts you need to 
indicate separate SSH keys for each of them.


