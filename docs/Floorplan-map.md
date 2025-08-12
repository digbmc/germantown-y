## Table of Contents

- [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
- [Adding Rooms](#adding-rooms)
- [Room Coordinates](#room-coordinates)
  - [Understanding Coordinates in Leaflet](#understanding-coordinates-in-leaflet)
  - [Finding Room Coordinates](#finding-room-coordinates)
- [Adding Pictures](#adding-pictures)
- [Editing Floor Descriptions](#editing-floor-descriptions)
- [Advanced](#advanced)
  - [Changing the Base Map](#changing-the-base-map)
    - [Step 1: Replace Base Map Images](#step-1-replace-base-map-images)
    - [Step 2: Adjust Map Bounds](#step-2-adjust-map-bounds)

## Introduction

This documentation explains how to add content to the floorplan map on the Germantown YWCA site. The map uses Leaflet to help users interact with the floor plans and find information about significant rooms. When you hover over rooms on the floor plans, highlighted rooms become clickable. Clicking on a highlighted room opens a sidebar with images and information about the room.

To work with the floorplan map, you will interact with three files:

- `germantown-y/_data/floorplans.csv`
    - Edit and add rooms.
- `germantown-y/_data/germantown-y-metadata.csv`
    - Add images and detailed information about them.
- `germantown-y/pages/building-js.html`
    - Contains the HTML, CSS, and JavaScript code for the Leaflet map.
    - Use this file if editing something in the advanced section of this documentation.

## Adding Rooms

To add or edit rooms on the floorplan map, use the `floorplans.csv` file located in the `_data` folder of the project's repository. Each row in the CSV file represents a room on the floor plans. Fill in the following information for each room: <!-- Where is this file? I can't find floorplans.csv, I would maybe recommend linking to the file to make it easier for people to find. -->

- **objectid**: The assigned ID in the metadata for the displayed image. This must match the object ID in the metadata.
- **title**: Title of the room. This appears in the info sidebar's header.
- **coordinates**: Coordinates of the room. See [Finding Room Coordinates](#finding-the-coordinates-for-a-room) for detailed instructions.
- **description**: Information about the room.
- **floor**: The floor where the room is located. Use `L0` for the basement, `L1` for the first floor, `L2` for the second floor, and so on.

## Room Coordinates

To add more clickable rooms to your map, each room must be defined as a polygon. A polygon is a shape made up of multiple points, and in Leaflet, you need to provide the exact coordinates of these points.

### Understanding Coordinates in Leaflet

In Leaflet, coordinates are given in `[y, x]` format, not the typical `[x, y]`. This means the first value represents the vertical (y-axis) position, and the second value represents the horizontal (x-axis) position. Additionally, the origin point `[0,0]` is located at the bottom-left corner of the map, unlike other coordinate systems where the origin point might be located elsewhere.

### Finding Room Coordinates

To get the coordinates of a specific room, use an image mapping tool like [Image Map Generator](https://www.image-map.net/). Follow these steps to find the coordinates:

1. **Get the Same Image**: Use the same image as the one in the floor plan map. Ensure the image is identical in size to the one currently used. The images are located in the `objects` folder and named `basement.png`, `floor1.png`, `floor2.png`, `floor3.png`, and `floor4.png`.
2. **Download and Prepare the Image**: Download the image. If using the Image Map Generator, its origin point is at the top-right corner. You will need to flip the image horizontally.
3. **Upload the Image**: Upload the prepared image to the Image Map Generator.
4. **Draw the Polygon**: Select 'Poly' under the 'shape' tab to draw a polygon. Click to create each point around your room. To add more polygons, click 'Add New Area' and draw additional shapes.
5. **Show Coordinates**: Once you have drawn the polygons, click 'Show me the code'.
6. **Extract Coordinates**: The code box will display `coords` properties with x and y coordinates for each point. Convert these to `[y, x]` pairs.
    - For example, if the coordinates are `coords="15,82,190,13,220,87,222,221,14,221"`, convert them to `[82,15], [13,190], [87,220], [221,222], [221,14]`.

## Adding Pictures

To add pictures to the sidebar, you need to document every image you add to the site. Follow these steps:

1. **Add Image to Metadata**: Navigate to the metadata documentation and follow the steps there to add your image and information about it to the metadata CSV.
2. **Match objectid**: Ensure you input the exact same `objectid` for the image in the metadata CSV as you use in the `floorplans.csv`.

## Editing Floor Descriptions

To edit the description of each floor, follow these steps:

1. Navigate to the `floorplans.csv` file located in the `_data` folder.
2. Find the floor description tab and update the title and description for each floor.

## Advanced

### Changing the Base Map

This section guides you through the process of changing the base map images and adjusting the bounds so they fit perfectly in your Leaflet map.

Please note: Although the current floorplans are oriented vertically, the vision is for the digitized floor plans to be placed horizontally for clearer viewing.

#### Step 1: Replace Base Map Images

- **Upload New Images**

    - Upload your new floor plan images to the `objects` folder within the GitHub repository.
- **Update Image URLs**

    - Find the section in your JavaScript code where the `footprints` object is defined. Replace the current paths with the new paths to your images.

```
// Define image URLs for each floor
    var footprints = {
        'L0': '{{site.baseurl}}/objects/plans/basement.png',
        'L1': '{{site.baseurl}}/objects/plans/floor1.png',
        'L2': '{{site.baseurl}}/objects/plans/floor2.png',
        'L3': '{{site.baseurl}}/objects/plans/floor3.png',
        'L4': '{{site.baseurl}}/objects/plans/floor4.png'
    };
```

#### Step 2: Adjust Map Bounds

- **Determine Image Dimensions**

    - Find out the dimensions of your new images (width and height).
        - On Windows: Right-click the image in File Explorer, choose 'Properties', and under the 'Details' tab, find the dimensions. For instance, your new image could have dimensions of 800x600 pixels.
- **Update Bounds in the Code**

    - Locate the `bounds` variable in your code. Update the bounds to match the dimensions of your new images.

`var bounds = [[0, 0], [800, 600]]; // Adjust bounds as per your new image size`

- **Update Map Center and Zoom Levels**
    - If necessary, adjust the initial center and zoom levels of the map to ensure the new images fit well. This might involve tweaking the `center` and `zoom` properties in the map initialization code.

```
var map = L.map('map', {
        center: [380, 118],
        zoom: -1,
        crs: L.CRS.Simple,
        fullscreenControl: true,
        layers: [L0Group], // Set the initial layer to basement floor
        maxBounds: bounds,
        maxBoundsViscosity: 1.0,
        zoomSnap: 0.1,
        zoomDelta: 0.1,
        minZoom: -3,
        maxZoom: 2
    });
```

- **Ensure the Map Starts with the Entire View Visible**
    - Call the `fitBounds` method with your updated bounds to make sure the map is correctly positioned and scaled to show the entire image initially.

    `map.fitBounds(bounds);`
