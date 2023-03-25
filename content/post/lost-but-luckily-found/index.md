---
title: Lost but luckily found
date: 2022-04-11T01:08:22.443Z
draft: false
featured: false
tags:
  - bash
image:
  filename: featured
  focal_point: Smart
  preview_only: false
---
So, the other night, I was cleaning up my disk partition to free up some of the space all those auto-generated files, created by makefiles and other confidential stuff, took up. Then I open up a new terminal tab and suddenly I see this:

```
-bash: home/laude/src/utils/oracle.utils.sh: No such file or directory
```

This is it.

I have to actually write down the full commands now. At this point, I gave up on the bug I was working on and was about to go downstairs for a cup of milk.

While I was sipping on my warm milk, trying to make a mental note of each of the aliases and functions I wrote, I realized one thing. 

The terminal I used while cleaning the disk was still open.

## [](https://github.com/ignaslaude/starter-hugo-academic/blob/main/content/post/lost-but-luckily-found/index.md#what-does-that-mean)What does that mean?

It means that my scripts are still loaded there! I just needed to find a way to get to it. A quick little google search pointed me to the declare method.

You want your functions back? Here you go:

```
declare -f
```

You erased your variables? Use this:

```
declare -x
```

You want to recover your aliases? You will need this:

```
alias
```

# What did I learn from this? 

Always back up your scripts. Always!