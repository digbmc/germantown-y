# TimelineJS
## Table of Contents
- [Getting Started](#getting-started)
- [Working with the Spreadsheet](#working-with-the-spreadsheet-additional-customization-tips)
    - [Dates](#dates)
    - [Text Styling](#text-styling)
    - [Adding Images](#adding-images)
    - [Background Color](#background-color)
    - [Understanding Groups](#understanding-groups)
- [After Working with the Spreadsheet](#after-working-with-the-spreadsheet)
    - [Changing Font](#changing-font)
- [How to Input Timeline into Site](#how-to-input-the-timeline-into-the-site)

## Getting Started
Start off by using TimelineJS to download the template spreadsheet. TimelineJS is an open-source tool that enables anyone to build visually rich, interactive timelines. To creat a timeline, you can simply use a Google Spreadsheet.

TimelineJS has a step by step guide on their homepage:
[TimelineJS homepage](https://timeline.knightlab.com/).

TimelineJS also has in-depth documentation which you can find here: [TimelineJS Documentation](https://timeline.knightlab.com/docs/using-spreadsheets.html).

## Working with the Spreadsheet: Additional Customization Tips
### Dates 
- Only use numbers. 
- To use words like 'January', input text into the Display Date column.

### Text styling 
- To change the color of the text, input html elements such as:
```html
<span style="color: blue;">Text</span>
```
This will change the text color to blue.
- To make text bold use:
`<strong>text</strong>`

### Adding Images 
- For adding images always use the image url and copy/paste it into the "Media column".
- To input background image, copy the image url into the "Background column".

### Background color 
Input the color in words (e.g. "lightblue") or use a hexcode (e.g. "#8BB1C4"). Don’t forget the pound/hashtag sign '#' when inputting a hexcode color.

In the end, here is what your timeline spreadsheet should look like with all the different elements: ![Timeline](<timeline format.png>)

**Note:** The background colors used in the timeline are from the color palette of the mural!

### Understanding Groups 
Using the group colummn, you can organize the slides by groups (tags). These tags will group events together and sort them into the same category. For example, the timeline displayed has 4 groups: Building, Damage, Redevelopment, and Pool. On the timeline, events with the same group will be put in the same row.

## After working with the spreadsheet
1. Publish your timeline under the file menu in the spreadsheet.
2. Click share and publish.
3. Copy and paste the URL into the field on the TimelineJS website.

### Changing Font 
Click on the "show" next to 'Optional Settings' ![Font](time.png) and there will display the different types of fonts.

## How to Input the Timeline into the Site
In the history HTML file, the first line of code is a container div with an embedded iframe displaying content from an external source, which in this case is the timeline. From the Step 4 on the TimelineJS site, copy and paste the URL provided under the 'Embed' title. It will look like this:
```
<div class = "container">
    <iframe src='https://cdn.knightlab.com/libs/timeline3/latest/embed/index.html?source=1cY9J-XJMjoE2zsrY107C04k1gsyULF2o-maf0OON_-w&font=Default&lang=en&initial_zoom=2&height=650' width='100%' height='650' webkitallowfullscreen mozallowfullscreen allowfullscreen frameborder='0'></iframe>
</div>
```
