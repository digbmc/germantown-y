---
title: documentation
author: Fiona
--- 
# Table of Contents
- [Undestanding Markdown Files](#understanding-markdown-files)
- [Understanding the Table of Contents](#table-of-contents-1)
    - [Getting More Technical](#getting-more-technical)
- [Navigation Bar](#navigation-bar)
    - [Navigation Flow](#navigation-flow)

# Understanding Markdown Files
- title: Sets the title of the page. This will be used as the page title and can also be displayed in various parts of the site depending on the template.
- layout: Specifies that the page should use a certain layout. For example in the history file, the layout displayed is the "history" layout. This should then correspond to a layout file named history.html in the _layouts directory.
- permalink: Sets a custom URL for the page. In this case, the page will be accessible at history.html.
- toc: Enables the table of contents for the page. This is a custom variable that is handled in your layout file. 

# Table of Contents
The table of content feeds from the markdown of the history page. The bullet points are generated from heading levels. Because the table of contents lists subheadings, the highest level of header should stay at level to (h2 in html, ## in markdown). Those headers will be in a bulleted list. Lower headers will be nested as bullet points within bullet points.

## Getting more technical 
[The table of contents](https://github.com/toshimaru/jekyll-toc?tab=readme-ov-file#generated-html) is a plug in designed by Toshimaru.  It's ReadMe contains further documentation on how the table of contents work. Styling for the table of contents is in _custom.scss around line 56. 

# The Navigation Bar 
To create a nav bar to change the items listed in a nav bar, edit the config-nav.csv file 
```
display_name,stub,dropdown_parent
Home,/,
History,/history.html,
Exibits,,
Exhibit page,/exibits.html,Exibits
Example 1,/exhibit-1,Exibits
Example 2,/example-2.html,Exibits
Map,/map.html,
Building,/building.html,
Archive,/archive.html,
Data,/data.html,
Credits,,
About,/credits.html,Credits
People,/people,Credits
```
- The format shows as follws: parent,/ url, children
- Parent: Indicates the menu item or section under which the current page is nested.
- URL: The path used to access the page.
- Children: Indicates pages or sections that are nested under the current page. 
So then there is the structure of parent, url, children

## Navigation Flow 
- From the Home page (/), you can navigate to History (/history.html).
- The Credits menu item includes two subpages: About (/credits.html) and People (/people). These will appear as a dropdown menu when you click on credits in the navigation bar. 

    