+++
date = "2017-11-29"
draft = false
title = "Read-n-share"
author = "Gao Wang"
tags = ["general"]
ghcommentid = 1
+++

In summer 2017 during one of the [Xin He lab](http://xinhelab.org) reading group session we brought up the notion of crowdsourcing the efforts of reading papers.
The gist is that we should figure out a way to not only share our literature reading notes, but also engage in discussions / debates if there are multiple people interested in the same paper. 

We were excited about the idea. But how do we go about doing it? Ideally we want a platform that:

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
Posting a reading blog essentially boils down to making `markdown` notes for papers you read, adding to it a few lines of meta info (such as author, date, tags), open a [github issue](https://github.com/xinhe-lab/journal-club/issues) to allow for discussions and embed it to the post, generate HTML pages via a 4-letter command and push it to the [github repo](https://github.com/xinhe-lab/journal-club). The outcome is this website you are looking at. 

## Taking notes

I use [`Mendeley`](https://www.mendeley.com/) to read papers directly from computer screen (reading printed paper hurts my neck :). In `Mendeley`, as demonstrated in this video below, one can annotate papers and take notes on the side panel. I write these notes in `markdown` format anyways.

<hr>
{{% youtube GRqjB7FE-M8 %}}
<hr>

## Sharing notes 
### Pre-requisites

The [`hugo` program](https://github.com/gohugoio/hugo/releases), a single executable that runs on <i class="fa fa-apple"></i>&nbsp;Mac OS&nbsp;X, <i class="fa fa-linux"></i>&nbsp;Linux, <i class="fa fa-windows"></i>&nbsp;Windows, and more! After you download the program, you can place it in one of your system's `PATH` folder so that you can run it from command line. To show your existing `PATH`:

```bash
echo $PATH
```

### Make a post

Suppose you have your note taken in a `markdown` file (either pulled from your Mendeley library or typed up after your hand-written notes) ready to share with others. You can first clone this repo:

```
git clone https://github.com/xinhe-lab/journal-club
```

Then add your note to `content/post`. Additionally please open a ticket in the [repository issue tracker](https://github.com/xinhe-lab/journal-club/issues) and record the issue ID. You can use something like "Comments on XX paper" as the ticket title.

Before you render the HTML pages and commit, please make sure you properly add in the meta information. For example:

```markdown
+++
date = "2017-11-29"
draft = false
title = "Read-n-share"
author = "Gao Wang"
tags = ["general"]
ghcommentid = 1
+++

(your text begins)
```

The `date`, `tags` and `ghcommentid` entries are the most important:

- The HTML pages will be named as `date-filename.html` from your source notes `content/post/filename.md`
- The `tags` will help organizing your notes by research field or researcher names depending on how you tag it
- The `ghcommentid` should match the issue ID you have just opened so that you can properly add comment box to the post

Now, simply type `hugo` at the root of the repository (where you can fine `config.toml`):

```bash
hugo
```

The HTML files will be generated to `docs` folder, which you can add and commit:

```bash
git add docs/*
git commit -am "Add note for K. Dey et al 2017"
git push
```

You will find your notes published at https://xinhe-lab.github.io/journal-club
