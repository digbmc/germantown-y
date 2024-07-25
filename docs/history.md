---
title: documentation
author: Fiona
--- 
# Table of Contents
- [Undestanding Markdown Files](#understanding-markdown-files)
- [Understanding the Table of Contents](#table-of-contents-1)
    - [Getting More Technical](#getting-more-technical)

# Understanding Markdown Files
```
---
title: history
layout: history
permalink: history.html
toc: true
description:  This timeline showcases significant events associated with the building, but also the social, political, and institutional events. It is an example timeline so Praxis course and community members have an idea on how it should look and can add their own content. The timeline features the Pool, The Young Women's Christian Association (YWCA) established to provide safe housing and support for young women, and multiple events held at the building.
---
```
- title: Sets the title of the page. This will be used as the page title and can also be displayed in various parts of the site depending on the template.
- layout: Specifies that the page should use a certain layout. For example in the history file, the layout displayed is the "history" layout. This should then correspond to a layout file named history.html in the _layouts directory.
- permalink: Sets a custom URL for the page. In this case, the page will be accessible at history.html.
- toc: Enables the table of contents for the page. This is a custom variable that is handled in your layout file. 
- description: allows for a description box to add content to describe the timeline. 

For more information about YAML Front Matter you can go to [Adding Content](./adding-content.md)

# Table of Contents
The table of content feeds from the markdown of the history page. The bullet points are generated from heading levels. Because the table of contents lists subheadings, the highest level of header should stay at level to (h2 in html, ## in markdown). Those headers will be in a bulleted list. Lower headers will be nested as bullet points within bullet points.

## Getting more technical 
[The table of contents](https://github.com/toshimaru/jekyll-toc?tab=readme-ov-file#generated-html) is a plug in designed by Toshimaru.  It's ReadMe contains further documentation on how the table of contents work. Styling for the table of contents is in _custom.scss around line 56. 
