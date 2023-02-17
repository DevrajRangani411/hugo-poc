---
title: "Hugo Getting Started"
date: 2023-02-01T00:43:55+05:30
draft: false
categories: ["POC"]
tags: ["Hugo", "Getting Started"]
image: "img/hugo.png"
author: "Devraj Rangani"
authorDes: "Nurdsoft"
authorUrl: "https://github.com/DevrajRangani411"
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

- When a new page is created, the front matter, also known as the title, date, and draught, are already declared and located inside the - - - section. You can then begin updating md files by adding new Lists, Categories, and Tags after the title section, and we can provide string arrays for those.
- Hugo will create pages based on tags, so every article assigned to a given tag will appear on that page.
- For add image move image to static folder and add in file `![my image](/img/art.png)`

### Theme:

- All integrated theme files are kept in the theme folder.
- We can copy the same folder structure to our primary site for theme customization.
  - For instance, if we want to modify header.html in the theme's layout/ partial folder, we must create the same folder structure on the website.

## Hugo Variables

Examples of some frequently used Page and Shortcode variables are provided here.

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

## HUGO Deploy on Netlify

Hugo site can easily deployable with auto framework detection on Netlify. We can also managing the version of the Hugo in Netlify with the environment variables.

Before deploying Hugo site to the Netlify, make sure that which ever theme is downloaded are should as github submodule.

Here are few steps to make your site live.

1. Sign Up Netlify with Github
2. Selecting GitHub will bring up an authorization modal for authentication. Select “Authorize application.”
3. Import or Give permission for your Hugo git repository
4. Click on New Site from Git and Select Hugo project
5. confirm your local Hugo version with hugo version.
6. Netlify will auto detect Build command and Public endpoint
7. Click on Show advanced and set HUGO_VERSION environment variable with same version of local HUGO.
8. Continue, and after building you will get your live site URL.

## Resources

- [HUGO Document](https://gohugo.io/documentation/)
- [Markdown Basic Syntax](https://www.markdownguide.org/basic-syntax/#overview)
- [HUGO Theme](https://themes.gohugo.io/)
