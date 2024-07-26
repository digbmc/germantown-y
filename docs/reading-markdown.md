---
title: documentation
author: Fiona
--- 
The above YAML is an example of how one would credit a page where they want to include a title and author 

# Understanding Markdown Files 
The below example is taken from the history.html YAML
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
