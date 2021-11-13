# Git Quick Manual

## Git Config

> How do I configure the user name and email only for current repository?

There are two ways to do this: 1) using `git config` to modify one attribute a time 2) modifying the config file in editor directly.

For example, executing the following two commands will modify the `user.name` and `user.email`.

```bash
git config --local user.name "Jiaming Meng"
git config --local user.email "jiamingm1990@outlook.com"
```

To modify the config file in editor, type command `git config --local -e` which will open your default editor, or just open the config file via `vim .git/config` if you are at the root of current repository. If I preview my config file, it looks like this.

```vim
[core]
    repositoryformatversion = 0
    filemode = true
    bare = false
    logallrefupdates = true
    ignorecase = true
    precomposeunicode = true
[remote "origin"]
    url = https://github.com/jiamingm1990/Technologies.git
    fetch = +refs/heads/*:refs/remotes/origin/*
[branch "main"]
    remote = origin
    merge = refs/heads/main
[user]
    email = jiamingm1990@outlook.com
    name = Jiaming Meng
```
