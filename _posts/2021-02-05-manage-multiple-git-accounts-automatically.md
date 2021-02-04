---
layout: default
title: Manage Multiple Git Accounts Automatically
date: 2021-02-04 23:22:00 -0900
tags: git
---

# {{ page.title }}
{{ page.date }}
## Introduction
I wanna manage multiple git account such as public (for individual) and private (for work). In this post, I write how to manage two (public and private) git accounts, and you can extend the number of git accounts by applying the following processes.

## Generate Public Keys
1. Move to folder where a key is saved.
```
$ cd ~/.ssh
```
2. Generate a public key named as `public_rsa.pub`
```
$ ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/(username)/.ssh/id_rsa):public_rsa
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```
3. Generate a public key named as `private_rsa.pub`
```
$ ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/(username)/.ssh/id_rsa):private_rsa
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```

## Register Each Public Key to Each Account (Public/Private)
You can copy the contents of `hoge_rsa.pub` to clipboard with the following command.
```
$ clip < ~/.ssh/hoge_rsa.pub
```
After that, registering the SSH key to GitHub account (Settings -> SSH and GPG keys -> SSH keys -> New SSH key).

## Setting Configuration of SSH
- Open your editor to edit `config` file.
```
vi ~/.ssh/config
```

- Edit as follows.
```
# public SSH configuration
Host github_public
HostName github.com
User git
IdentifierFile ~/.ssh/public_rsa
IdentitiesOnly yes
AddKeysToAgent yes
# private SSH configuration
Host github_private
HostName github.com
User git
IdentifierFile ~/.ssh/private_rsa
IdentitiesOnly yes
AddKeysToAgent yes
```

## Cloning Repositories
You cannot use `git clone git@github.com:[userName]/[repositoryName]`. You should use the following commands.
- Clone as public account...
```
$ git clone git@github_public:[userName]/[repositoryName]
```

- Clone as private account...
```
$ git clone git@github_private:[userName]/[repositoryName]
```

## Change `.gitconfig`
To manage multiple account, you should not set global user, but local user.
1. Move to repository

2. Delete global user information
```
git config --global --unset user.name
git config --global --unser user.email
```

3. Set local user's name, email, insteadOf
    - If the repository is for public account...
    ```
    git config --local user.name "Your public name"
    git config --local user.email "Your public e-mail address"
    git config --local url."github_public".insteadOf "git@github.com"
    ```

    - If the repository is for private account...
    ```
    git config --local user.name "Your private name"
    git config --local user.email "Your private e-mail address"
    git config --local url."github_private".insteadOf "git@github.com"
    ```

Since you should register the above information when cloning repositories, it is recommended to create alias in `.bash_profile`.

## Conclusion
By the above process, I can manage two git account automatically :)

## Reference
- [GitHubでssh接続する手順~公開鍵・秘密鍵の生成から~](https://qiita.com/shizuma/items/2b2f873a0034839e47ce)
- [複数のGitアカウントを手動切替不要で運用する](https://qiita.com/KeyMama/items/f9291bb125ee94b52b78)