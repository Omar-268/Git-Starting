# Git configuration

After git installation we need to configure some elements. Some are obligatory, some are not, some can make our work easier.

## Git Config Basics

When you first install Git, you need to configure some basic settings so Git knows who you are and what tools to use.
This is done using the `git config` command.


## Configuration Levels (Tables)

Git stores settings in three different levels:

`--system` → applies to the entire machine (all users).

`--global` → applies to the current user (all repos for this user).

`--local` (default) → applies only to the specific repository you are working in.


## Essential Configurations

These are the first things you should set up after installing Git:

1. Set your name
`git config --global user.name "yourname"`

Defines your name. This name will appear in your commits.

2. Set your email
git config --global user.email yourmail@myemail.com

Links commits to your email address.
Important when pushing code to GitHub/GitLab so commits are tied to your account.


## Viewing Configurations

- Show all configurations (system + global + local):

    `git config --list -a`

- Show only global configurations:

    `git config --list --global`

- Show a single configuration (e.g., your username):

    `git config user.name`

You can try this scenario yourself in the following lab: [Configure Git](https://killercoda.com/pawelpiwosz/course/gitFundamentals/git-02-git-config)