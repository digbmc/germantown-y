
<!-- ToDo:
- Add images!! with instructions
- Write instructions on how to edit the csv and reupload once modified
- Elaborate advanced customization
- Add code snippets-->
# Webmap Documentation

## Table of Contents
- [Prerequisites](#prerequisites)
- [Useful Vocab](#useful-vocab)
- [Adding Items to Map](#adding-items-to-the-map)
- [Troubleshooting](#troubleshooting)
- [Advanced Customization](#advanced-customization)

## Prerequisites
This tutorial assumes that you have already cloned the repository and you are working on your own branch. If you have not done so, go to the [Getting Started](https://github.com/digbmc/germantown-y/docs/background-info.md) page and follow the instructions before beginning this tutorial.

You will also need a Google account to add more content to the map:
-   [Create a Google Account](https://support.google.com/accounts/answer/27441?hl=en). You will need to use Google Sheets to edit a file.
## Useful Vocab:
- CSV: Comma separated file, this can also be viewed as a table.
- Markers: The exact point of a location on the map
- Pop-ups: The dialogue boxes that appear when you click on a marker
## Adding Items to the Map:
The web map pulls data from the file: building-info.csv located in the _data folder. You can modify, remove or add items to the map by modifying this file. This tutorial will demonstrate how to achieve this:

### Using GitHub Web Interface:
Log in to GitHub and go to the [Germantown-Y github repository](https://github.com/digbmc/germantown-y). Switch to your branch from the dropdown:
![Branches Dropdown](screenshots/webmap-docs-2.png)

Once you are in your branch, navigate to _data/building-info.csv.
![Branches Dropdown](screenshots/webmap-docs-3.png)


Open the file and download it using the download button:
![Download Button](screenshots/webmap-docs-5.png)

Go to [Google Sheets](https://docs.google.com/spreadsheets/u/0/).
Import the file in Google Sheets by going to File > Import your file.


![Import Button](screenshots/webmap-docs-4.png)
In the popup that appears, go to the upload tab. Click on Browse, go to your downloads folders, or where the file is saved and upload it. Alternatively you can also drag and drop it in the upload tab. 
![]()

Select comma as the separator type and uncheck the convert text to numbers, dates and formulas box. Click on import data.
![Import file dialogue box](screenshots/webmap-docs-6.png)
The sheet has the following columns: id, title, creator, date, description, subject, location, latitude, longitude, source, object_location, image_alt_text.
- **ID:** The unique id associated with each item in the map. It is good practice to add them if you add a new location.
- **Title:** The title or name of the location. If you want a pop-up to show on the marker, this field is necessary.
- **Creater:** The name of the person who created the item in the csv
- **Date:** The date or year the building or location was established. Currently, most of these locations have the established year associated with them in the csv, this is so the user has an idea of what time period that location or building was founded in. If you want a pop-up to show on the marker, this field is necessary.
- **Description:** A description of what the location is, how it is significant to the Germantown YWCA and any additional information that the user may be interested in. If you modify these, we suggest you also add the source of where you got that information from and put it under sources in the CSV. This field is necessary for the pop-up.
- **Subject:** How the locations are grouped together in the map. The subjects appear in the sidebar on the top right and are color coded. For an object to appear on the map, this must not be left blank. You can choose to assign ex an existing subject to the object, or add a new subject. If a new subject is assigned to a building it will show up in the sidebar, and the color of the icon for that subject will be blue. To change the color, advanced customization is required.
- **Location:** The address of the location. If you want a pop-up to show on the marker, this field is necessary.
- **Latitude:** The latitude coordinate of the item. For a marker to show up on the map, this is necessary.
- **Longitude:** The longitude coordinate of the item. For a marker to show up on the map, this is necessary.
- **Source:** The source of the information in the description field
- **Object Location:** If an image is used from within the repository, then the relative url of the image. Complete url if image is not already present within the repository.
- **Image:** The path to the image file you want to display on the pop-up.
- **Image Alt Text:** Alternative text for the image should be put here. Alt text is used by screen readers to describe the image and is helpful for making the website more accessible.


Make your edits. To ensure the item displays on the map it must contain a latitude, a longitude and a subject. The pop ups will only appear in the map if there is a title, description and the date associated with the item. The item will be categorised according to subject and displayed on the map with the icon color according to the subject it is assigned.

Adding an image to pop-up:
- If already present in the collection:
- If uploading a new image: Ensure you have permissions to use the image you are uploading

### Adding changes to the repository:
Save as a CSV.
![Saving file as csv](screenshots/webmap-docs-8.png)
Open in a text editor, select all, copy. Go to the repository. In your branch go to: _data/building-info.csv. Click edit. Select all, and paste. Save the file. Open a pull request for your edits to show on the website.

## Troubleshooting:
If an item in the CSV is not showing up on the map, make sure the required fields contain some data and are not empty. You can also right click on the webpage, and click on inspect. Go to the console tab to see any errors. An error message stating:
```
Feature missing required fields: (subject, latitude, or longitude)
```
will show up in the console indicating which required field was left blank.

![Console warning inspect Page](screenshots/webmap-docs-7.png)

## Advanced Customization:
The map was created using LeafletJS. You will need some knowledge of HTML, CSS and functional programming in JavaScript to make additional changes. If you are not sure how this works, it might be helpful to fork the repository and make changes separately.

Here are some resources to get you started:

HTML: https://developer.mozilla.org/en-US/docs/Web/HTML

CSS: https://developer.mozilla.org/en-US/docs/Web/CSS

LeafletJS: https://leafletjs.com/reference.html

JavaScript: https://developer.mozilla.org/en-US/docs/Web/JavaScript

Go to pages/webmap-js.html in the repository to make additional changes to the map.

### Modify Icon Colors:
Within the style tags, each category has its own color for marker icon. Change the value in hue rotate to change these colors. This applies styling to the default icon image in the leaflet library. Since this is an image, image styling CSS can be applied to modify how these icons appear.

### Modify Layers Displayed Upon Page Load
If a layer has .addTo(map), it will be displayed on page load. The page loads top down, so the last thing in the code will appear on top on your webpage.
### Add Additional Base Layers
Free base layers: (link)
WMS layers vs WMTS layers and how to add them. Leaflet only allows image tiles.

### Modify Pop Ups
Edit the function createLayer

### Modify Categories
Edit the conditional statement in the function addDataToLayer
