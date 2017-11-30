+++
date = "2017-11-29"
draft = false
title = "Crowd-source paper reading"
author = "Gao Wang"
+++

In summer 2017 during one of the [Xin He lab](http://xinhelab.org) reading group session we brought up the notion of *crowd-source* paper reading. 
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

I volunteered to dig into this a bit further because I really like the idea. But it was not until today that I am resolved to make a serious effort. So here comes a preliminary solution: the **Paper Reading Blog**. 

## Overview
Posting a reading blog essentially boils down to making `markdown` notes for papers you read, adding to it a few lines of meta info (such as author, date, keywords), open a [github issue](https://github.com/xinhe-lab/journal-club/issues) to allow for discussions and embed it to the post, generate HTML pages via a 4-letter command and push it to the [github repo](https://github.com/xinhe-lab/journal-club). The outcome is this website you are looking at. 

## Taking notes

I use [`Mendeley`](https://www.mendeley.com/) to read papers directly from computer screen (reading printed paper hurts my neck :). In `Mendeley`, as demonstrated in this video below, one can annotate papers and take notes on the side panel. I used to write those notes in `markdown` format anyways due to force of habit. 

{{% youtube GRqjB7FE-M8 %}}

## Sharing notes 
### Pre-requisites

The [`hugo` program](https://github.com/gohugoio/hugo/releases), a single executable that runs on <i class="fa fa-apple"></i>&nbsp;Mac OS&nbsp;X, <i class="fa fa-linux"></i>&nbsp;Linux, <i class="fa fa-windows"></i>&nbsp;Windows, and more!
