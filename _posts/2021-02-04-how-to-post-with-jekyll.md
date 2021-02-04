---
layout: default
title: How To Post With Jekyll
date: 2021-02-04 04:23:00 -0900
tags: jekyll
---

# {{ page.title }}
{{ page.date }}
## Introduction
Jekyll is one of the template which can be used in GitHub.io, and this tech blog is also structured with jekyll.

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
### Location of Files
Files of post need to be located in `_posts` folder.
### Naming
You should along with the following naming rule.
```
YYYY-MM-DD-Title-Of-Post.md
YYYY-MM-DD-Title-Of-Post.html
```
- YYYY: year
- MM: month
- DD: day
- Title-Of-Post: title of post

As you can see, it is not allowed to use `_` as spaces. `-` is only accepted. In addition, the post is published as `{base-link}/YYYY/MM/DD/Title-Of-Post.html`
### Head of Files
To reflect the theme of jekyll and to add some features to posts, you must write the following header in your files of post.
```
---
layout: default
title: title of post
date: YYYY-MM-DD hh:mm:ss -0000
categories: CATEGORY-1 CATEGORY-2
tags: TAG-1 TAG-2
permalink: /hoge
---
```
- layout
    - Reflecting the theme of your `_layout/default.html`
- title
    - Title of a new post
- date
    - Date of posting
- categories
    - You can set categories of the new post. 
    - If you write `categories: hoge fuga`, the new post is published as `{base-link}/hoge/huga/YYYY/MM/DD/Title-Of-Post.html`
- tags
    - You can set tags of the new post like categories, but URL of the new post is not changed.
- permalink
    - You can set any URL. If you write `permalink: /hoge`, the new post is published as `{base-link}/hoge`.

### Refering Images
### Refering the Other Posts

## Conclusion

## Reference
- [Adding a new post to your site](https://docs.github.com/en/github/working-with-github-pages/adding-content-to-your-github-pages-site-using-jekyll#adding-a-new-post-to-your-site)
- [GitHub PagesからJekyllでブログ作る時にやったこと。](https://hayateasdf.hatenablog.com/entry/2018/08/09/182327)