---
title: "Hugo Getting Started"
date: 2023-02-01T00:43:55+05:30
draft: false
categories: ["POC"]
tags: ["Hugo", "Getting Started"]
image: "img/hugo.png"
---

This article describes Hugo Getting started.

## Overview

HUGO is a static site generator written in the Go programming language. It is designed to be fast, secure, and easy to use, and is used to create websites and blogs. HUGO is open source and free to use and includes a wide range of features and templates to help you create your own website.

HUGO provide a wide range of features such as custom themes, content management, taxonomies, and multi-language support. It can be used to build websites, blogs, and even single page applications.

## Installation

We can install HUGO in most of all popular operating systems. Here we are taking look for the Mac, windows and linux platforms.

Hugo is easy to install with just the following command.

**MacOS**

`$ brew install hugo`

**Windows**

`$ choco install hugo-extended`

**Linux**

`$ sudo snap install hugo`

## Basics HUGO commands

- Run this command to creating a new site:

  ```script
    hugo new site “site name” : For creating new site
    hugo new site “site name” -f yml : For creating new site with lml config file
  ```

- For the creating new article:

  ```script
  hugo new about.md : it will create new about file in content folder
  ```

- Start Hugo server locally for the live code preview:

  ```script
  hugo server : start dev server
  hugo server —noHTTPCache : It will clean the cache before updating
  ```

- Create the production build:

  ```script
  hugo : for creating server build
  ```

- To integrate new theme in site follow this command for root folder

  ```script
  mkdir themes
  $ cd themes
  git clone https://github.com/CaiJimmy/hugo-theme-stack/ themes/hugo-theme-stack
  ```

## File Structure:

- Archetypes: it's predefined article front matter skeleton
- Config file : it’s manages the config for the site
  - Contains site title
  - Theme name
  - Comments settings
  - Other theme related configuration
- Statics
  - It included style files
  - Images
  - JS files
- Content
  - Pages
  - Articles
- Layout
  - Single.html : it is responsible for all generated article files as single page skeleton
  - List.html : Whenever we create tags It will manage the tags list in index page
- Public
  - Once website build then all build file created into this public folder

### Content as MarkDown(.md):

- Once new page created Title, date, draft are already declared which called front matter and that are inside - - - section . After that you can start updating md files by List, categories and Tags gone after the title section and in that we can provide string array
- Hugo will create pages according to tags so, each article assign in same tag are show in that particular tag page
- For add image move image to static folder and add in file `![my image](/img/art.png)`

## Hugo Variables

Hugo has many type of variables for the every the specific purpose

- Variables Overview
- Site Variables
- Page Variables
- Shortcode Variables
- Pages Methods
- Taxonomy Variables
- File Variables
- Menu Entry Properties
- Git Variables

Here are some common used Page and Shortcodes variable with example

- {{ partial “header.html” . -}} For importing any specific component/partial to the page
- {{“.Title”}} For page title we can use
- {{.Content -}} For rest all md content we can use
- {{- range.Pages}} Content {{end .}} List down the list of content
- {{ .Summary }} : for snippet of article
- {{ .Truncated }} : return boolean based on summary of article length, if article too small then returns false else true
- {{ .WordCount }} : shows word count
- {{ .ReadingTime }} : return reading time in minutes
- {{ .Date.Format “Jan 02, 2006”}} Here, Jan 02, 2006 is special stack to format the date, so date will display accordingly
- {{ .RelPermalink }}: Relative link
- {{with .Params.tags }} Tagged with: {{ delimit . “, ”}} {{end}}Here with will check if tags are there and if yes then it will print and concat with “ , “.
