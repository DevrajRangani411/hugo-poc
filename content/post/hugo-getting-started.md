---
title: "Hugo Getting Started"
date: 2023-02-01T00:43:55+05:30
draft: false
categories: ["POC"]
tags: ["Hugo", "Getting Started"]
image: "img/hugo.png"
---

Hugo Scripts:

- `hugo new site “site name”` : For creating new site
- `hugo new site “site name” -f yml` : For creating new site with lml config file
- `hugo server` : start dev server
- `hugo server —noHTTPCache` : It will clean the cache before updating
- `hugo` : for creating server build
- `hugo new about.md` : it will create new about file in content folder

Index Page:

- Vim \_index.md or create \_index.md file in content folder

MarkDown(.md) File:

- Once new page created Title, date, draft are already declared which called front matter and that are inside - - - section . After that you can start updating md files by List, Discovery andTags gone after the title section and in that we can provide string array
- Hugo will create pages according to tags so, each article assign in same tag are show in that particular tag page
- For adding links put title in [about page](/about)
- For add image move image to static folder and add in file `![my image](/img/art.png)`

File Structure:

- Config file : it’s manages the config
  - Contains title
  - Theme name
- Statics
  - It included style files
  - Images
- Content
  - It include markdown file
- Public
  - Once website build then all build file created into this public folder
- Layout
  - Single.html : it is responsible for all generated article files as single page skeleton
  - List.html : Whenever we create tags It will manage the tags list in index page

Hugo Variables

- For importing any file, like in them layout \_default file we import header file {{ partial “header.html” . -}}
- Same way footer {{ partial “footer.html” . -}}
- For page title we can use {{“.Title”}}
- For rest all md content we can use {{.Content -}}
- Looping or listing part we can take for loop using <ul> {{- range.Pages}}<li><a href=“{{ .RelPermalink }}”>{{ .Title}}</a></li>{{end .}} </ul>
- {{ .Summary }} : for snippet of article
- {{ .Truncated }} : return boolean based on summary of article length
- {{ .WordCount }} : shows word count
- {{ .ReadingTime }} : return reading time in minutes
- {{ .Date.Format “Jan 02, 2006”}} here Jan 02, 2006 is special stack to formate the date, so date will format accordingly
- {{ .RelPermalink }}: Relative link
- {{with .Params.tags }} Tagged with: {{ delimit . “, ”}} {{end}}Here with will check if tags are there and if yes then it will print and concat with “ , “.
