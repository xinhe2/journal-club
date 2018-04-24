+++
date = "2017-11-29"
draft = false
title = "Read-n-share"
author = "Gao Wang"
ghcommentid = 1
+++

In summer 2017 during one of the [Xin He lab](http://xinhelab.org) reading group session we came up with the notion of crowdsourcing the efforts of reading papers.
The gist is that we should figure out a way to not only share our literature reading notes, but also engage in discussions / debates if there are multiple people interested in the same paper.

We were excited about the idea. But how do we go about implementing it? Ideally we want a platform that:

- Renders well-formatted documents
- Well organized
  - by author of article, by research area, etc.
  - both locally and remotely
- Easy to edit, share and publish
  - written in well-accepted document format
  - from our favorite text editor
  - to nice online HTML pages 
- Has a discussion platform
- Supports LaTeX!

Keywords like `markdown`, `git`, `github.io` all came out when we brainstormed it during that reading group meeting, but no consensus was reached.

I volunteered to dig into this a bit further because I really like the idea. But it was not until today that I am resolved to make a serious effort. So here comes a preliminary solution: the Paper Reading Blog. 

## Overview
To posting a note to this blog, you 1) write up a `markdown` document for the paper you want to share, 2) adding to it a few lines of meta info (such as author, date, tags), 3) open a [github issue](https://github.com/xinhe-lab/journal-club/issues) to allow for discussions and embed it to the post, 4) render it to HTML via a 4-letter command and 5) push it to the [github repo](https://github.com/xinhe-lab/journal-club). The outcome is this website you are looking at. 

## Taking notes

I use [`Mendeley`](https://www.mendeley.com/) to organize literature and to read them (reading printed paper cause me neck pains ...). In `Mendeley`, as demonstrated in the video below, one can annotate papers and take notes on the side panel. I usually write these notes in `markdown` format anyways even inside `Mendeley`.

<hr>
{{% youtube GRqjB7FE-M8 %}}
<hr>

## Sharing notes 
### Pre-requisites

We generate static webpages via `hugo` [[download here](https://github.com/gohugoio/hugo/releases)], a single executable that runs on <i class="fa fa-apple"></i>&nbsp;Mac OS&nbsp;X, <i class="fa fa-linux"></i>&nbsp;Linux, <i class="fa fa-windows"></i>&nbsp;Windows (and more!). After you download the executable for your platform, you can place it in one of your system's `PATH` folder in order to trigger it from command line. To show your existing `PATH`:

```bash
echo $PATH
```

To make a post, here is a short video instruction. You can also read on to the remaining text of this document if this video instruction is not easy to follow.

<video class="center-block" width="80%" height="auto" autoplay="autoplay" controls>
  <source src="../media/jc-example.mp4" type="video/mp4">
  Your browser does not support HTML5 video.
</video>
<hr>

### Create a post

Suppose you have your note written in a `markdown` file (either copied from your Mendeley notes or typed up after your hand-written notes) ready to share on this blog. You can first clone this repo:

```
git clone https://github.com/xinhe-lab/journal-club
```

Then add your note to `content/post`. Additionally please open a ticket in the [repository issue tracker](https://github.com/xinhe-lab/journal-club/issues) and record the issue ID. You can use something like ''Comments on XX paper'' as the ticket title.

#### Tip: LaTeX syntax support

For example, inline math $\hat{\beta}$, displayed math, $$\hat{\beta} = 0$$ and [aligned math](https://github.com/gcushen/hugo-academic/issues/291#issuecomment-334746889)

\begin{align}
P(A|B) &= \frac{P(A)P(B|A)}{P(B)} \\\\\\
& \propto P(A)P(B|A)
\end{align}

Before you render the HTML pages and commit, please make sure you properly add in the meta information. For example:

```markdown
+++
date = "2017-11-29"
title = "Read-n-share"
author = "Gao Wang"
ghcommentid = 1
tags = ["git"]
topics = ["general"]
people = ["UCHGCompBio"]
draft = false
+++

(your text begins)
```

The `date`, `tags` and `ghcommentid` attributes are the most important:

- The HTML page generated from `content/post/filename.md` will be named as `date-filename.html`.
- The `tags` will organize your notes by keywords often indicating a specific research direction.
- The `ghcommentid` should match the issue ID you have just opened; otherwise the "comments" section will not load properly. See image below -- `ghcommentid = 1` points to Issue #1 on this repo.

<hr>
![](/201711/setup-comments.png)

(Incidentally, to add image to post, you can place the image under [`static` folder](https://github.com/xinhe-lab/journal-club/blob/master/static/201711/setup-comments.png) and load it from [the `markdown` file](https://github.com/xinhe-lab/journal-club/blob/master/content/post/uchg-compbio-jc.md#create-a-post) as demonstrated here.)
<hr>

Additionally, attribute `author` indicates on the post the name of the contributor. `topics` and `people` are optional attributes. 

- `topics` defines broader categories than `tags`. eg. topics can be "statistics", "transcriptomics", "cancer".
- `people` lists the name of scientists involved in the paper under discussion.

These attributes will not appear directly in the post itself, but will be displayed in the side bar for book-keeping.

Now, simply type `hugo` at the root of the repository (where you can find `config.toml`):

```bash
hugo
```

The HTML files will be generated to `docs` folder. Optionally you can preview the post before publishing it online:

```bash
hugo server
```

You see the website preview is published locally to `http://localhost:1313/journal-club`:

```text
Started building sites ...
Built site for language en:
0 draft content
0 future content
0 expired content
1 regular pages created
10 other pages created
0 non-page files copied
3 paginator pages created
0 topics created
1 tags created
total in 31 ms
Watching for changes in /home/gaow/GIT/wiki/journal-club/{data,content,static,themes}
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/journal-club/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

Finally, to upload the post to github:

```bash
git add docs/*
git commit -am "Add note for K. Dey et al 2017"
git push
```

Now visit https://xinhe-lab.github.io/journal-club to see your post published with comments linked to github issues of this repository!
