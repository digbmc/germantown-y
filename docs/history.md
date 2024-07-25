---
title: documentation
author: Fiona
--- 
# Table of Contents
- [Undestanding Markdown Files](#understanding-markdown-files)
- [Understanding the Table of Contents](#table-of-contents-1)
    - [Getting More Technical](#getting-more-technical)

# Understanding Markdown Files
YAML Front Matter 
[Front matter](https://jekyllrb.com/docs/front-matter/) is a list of [YAML](https://yaml.org/)variables at the top of a page. Front matter is an essential part of Jekyll's structure.
- title: Sets the title of the page. This will be used as the page title and can also be displayed in various parts of the site depending on the template.
- layout: Specifies that the page should use a certain layout. For example in the history file, the layout displayed is the "history" layout. This should then correspond to a layout file named history.html in the _layouts directory.
- permalink: Sets a custom URL for the page. In this case, the page will be accessible at history.html.
- toc: Enables the table of contents for the page. This is a custom variable that is handled in your layout file. 
For more information go to [Adding Content](./adding-content.md)

# Table of Contents
The table of content feeds from the markdown of the history page. The bullet points are generated from heading levels. Because the table of contents lists subheadings, the highest level of header should stay at level to (h2 in html, ## in markdown). Those headers will be in a bulleted list. Lower headers will be nested as bullet points within bullet points.

## Getting more technical 
[The table of contents](https://github.com/toshimaru/jekyll-toc?tab=readme-ov-file#generated-html) is a plug in designed by Toshimaru.  It's ReadMe contains further documentation on how the table of contents work. Styling for the table of contents is in _custom.scss around line 56. 


