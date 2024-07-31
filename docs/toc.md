# Table of Contents

The History page has a table of contents that builds automatically from the Markdown on that page. The bullet points are generated from heading levels. Because the table of contents lists subheadings, the highest level of header in the text content of each page should be level two (h2 in HTML, ## in Markdown). Those headers will be in a bulleted list. Lower headers will be nested as bullet points within bullet points.

## Getting More Technical 
The site uses [jekyll-toc](https://github.com/toshimaru/jekyll-toc?tab=readme-ov-file#generated-html), a plugin designed by Toshimaru, to generate the table of contents on each page. Its README contains further documentation on how the table of contents works. Styling for the table of contents is in _custom.scss around line 56. 

<!-- consider adding the option of adding a TOC to exhibit pages / content added by Praxis students (e.g. "toc: true" in front matter on exhibit pages) in case they write longer articles that would benefit from a TOC -->