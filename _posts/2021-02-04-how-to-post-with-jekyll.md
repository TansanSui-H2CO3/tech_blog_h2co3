---
layout: default
title: How To Post With Jekyll
date: 2021-02-04 04:23:00 -0900
tags: jekyll
---

# {{ page.title }}
## Introduction
Jekyll is one of the template which can be used in GitHub.io.

## Folder Structure
```
root
┣ _data
┃ ┣ data.yaml
┃ ┣ data.json
┃ ┣ data.csv
┃ ┗ data.tsv
┣ _drafts
┃ ┣ Title-Of-Post.md
┃ ┗ Title-Of-Post.html
┣ _posts
┃ ┣ YYYY-MM-DD-Title-Of-Post.md
┃ ┗ YYYY-MM-DD-Title-Of-Post.html
┗ assets
  ┗ img
    ┣ img.png
    ┗ img.jpg
```

## Writing a New Post
### Location of files of post
Files of post need to be located in `_posts` folder.
### Name of a New Post
You should along with the following naming rule.
```
YYYY-MM-DD-Title-Of-Post.md
YYYY-MM-DD-Title-Of-Post.html
```
- YYYY: year
- MM: month
- DD: day

As you can see, it is not allowed to use `_` as spaces. `-` is only accepted.
### Markdown header
To reflect the theme of Jekyll, you must write the following header in your files of post.
```
---
layout: default
title: title of post
date: YYYY-MM-DD hh:mm:ss -0000
categories: CATEGORY-1 CATEGORY-2 (Optional)
tags: TAG-1 TAG-2 (Optional)
---
```

## Refering the Other Posts

# Conclusion
I was sooooooooo frustrated.

# Reference
- [Adding a new post to your site](https://docs.github.com/en/github/working-with-github-pages/adding-content-to-your-github-pages-site-using-jekyll#adding-a-new-post-to-your-site)
- [GitHub PagesからJekyllでブログ作る時にやったこと。](https://hayateasdf.hatenablog.com/entry/2018/08/09/182327)