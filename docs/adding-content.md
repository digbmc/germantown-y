

# Adding Content 
Most of the content being added to site will be files for the exhibit page. (link to the exhbits guide). Every md file has two parts: the front matter and the content. 

[Front matter](https://jekyllrb.com/docs/front-matter/) is a list of [YAML](https://yaml.org/)variables at the top of a page. Front matter is an essential part of Jekyll's structure. 

Front matter is indicated with a starting `---` and a closing `---`. For example, here's the front matter of the archive page
```
---
title: archive
layout: browse
permalink: browse.html
---
```

title and layout are essential variables for new pages. If you don't need any special styling, the layout should be default. Checkout the [advanced documentation](advanced.md) for more on layouts. Permalink is also important here: it's specifies the location of the page. Keep it short, and similar to the title. 

## creating pages
If you need to create a page outside of Exhibits, create a markdown file in the _posts folder. The naming convention for pages is lowercase with dashes between words. 

## working on existing pages
Exhibit files can be found in the _exhibts folder, the rest of the pages are in _posts. To edit the content of the page, work below the front matter. Everything in that section of the file will be pulled when the site generate content. 

### Text
To add content to a given page, start writing below the page's front matter. All text should be written using markdown, a simple formatting languge. 

[Guide to Markdown](https://www.markdownguide.org/basic-syntax/) 

### Features 
Features are snippits of code that can be added to pages with a single line. CollectionBuilder has several features designed to make adding content easier. They're a great tool for adding visual content, espically from the archive.

#### Images 
to add images to a page, add this line of code to your markdown file: `{% include feature/image.html objectid="demo_001" %}`

Objectid is a parameter: here you would put the image you want to use. This can either be an objectid from the meta data, a url to an external image, or a relative link to a picture in the assets folder. Replace "demo_001" with the source of your image.

Parameters allow you to customize the way the feature loads.

Other parameters include... 

- alt = alternative text describing the image, essential for screen readers
- caption = if you don't add a caption, and you use and object id, the caption below the image with be the description from the metadata. use the caption tag if you want a custom caption, or add `caption:false` to remove it
- link = if you want to change the link that the image goes to when you click on the image. If you don't include the link parameter the url will automatically be the image source
 - width = will use responsive sizing to set the % size on desktop (will be 100% on mobile), choose from "25", "50", "75", or "100" (optional)

#### PDFs 
You can include a pdf with `{% include feature/pdf.html objectid="demo_002" %}`

Like with the image feature, the objectid can be an objectid, a link to an external pdf, or a link to an internal pdf. 

Additional Parameters:
- caption
- width 
- ratio: change the size of the pdf by changing the ratio. options are "21x9", "16x9", "4x3", or "1x1". 1x1 is the default. 

#### More features
Check out CollectionBuilder's [Feature Bonanza](https://collectionbuilder.github.io/collectionbuilder-gh/feature_options.html) for more information on features.

### Footnotes: 
With the use of [Kramdown](https://kramdown.gettalong.org/) footnotes are easy to add to markdown documents. Here's the documentation on [adding footnotes](https://minicomp.github.io/ed/documentation/#footnotes)