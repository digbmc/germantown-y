# Floorplan Map Documentation

## Table of Contents

- [Introduction](#introduction)
- [The CSV](#the-csv)
- [Adding More Rooms](#adding-more-rooms)
    - [Finding the Coordinates for a Room](#finding-the-coordinates-for-a-room)

## Introduction

This documentation explains how to add content to the floorplan map on the Germantown YWCA site. The map uses Leaflet to help users interact with the floor plans and find information about significant rooms. When you hover over rooms on the floor plans, highlighted rooms become clickable. Clicking on a highlighted room opens a sidebar with images and information about the room.

## The CSV

To add or edit rooms on the floorplan map, use the `floorplans.csv` file located in the `_data` folder of the project's repository. Each row in the CSV file represents a room on the floor plans. Fill in the following information for each room:

- **name**: Title of the room. This appears in the info sidebar's header.
- **coordinates**: Coordinates of the room. See [Finding Room Coordinates](#Finding-Room-Coordinates) for detailed instructions.
- **floor**: The floor where the room is located. Use L0 for the basement, L1 for the first floor, L2 for the second floor, etc.
- **description**: Information about the room.
- **imageurl**: URL for the image in the sidebar.
- **imagetitle**: Title of the image.
- **imagealt**: Alternate text for the image if it fails to load.

## Adding More Rooms

To add more clickable rooms to your map, each room must be defined as a polygon. A polygon is a shape made up of multiple points, and in Leaflet, you need to provide the exact coordinates of these points.

### Understanding Coordinates in Leaflet

In Leaflet, coordinates are given in [y, x] format, not the typical [x, y]. This means that the first value represents the vertical (y-axis) position, and the second value represents the horizontal (x-axis) position. Additionally, the origin point [0,0] is located at the bottom-left corner of the map, unlike other coordinate systems where the origin point could be located elsewhere.

### Finding Room Coordinates

To get the coordinates of a specific room, use an image mapping tool like [Image Map Generator](https://www.image-map.net/). Follow these steps to find the coordinates:

1. **Get the Same Image**: Use the same image as the one in the floor plan map. Ensure the image is identical in size to the one currently used. The images are located in the `objects` folder and named `basement.png`, `floor1.png`, `floor2.png`, `floor3.png`, and `floor4.png`.
2. **Download and Prepare the Image**: Download the image. If using the Image Map Generator, its origin point is on the top right. you would need to flip the image horizontally.
3. **Upload the Image**: Upload the prepared image to the Image Map Generator.
4. **Draw the Polygon**: Select 'Poly' under the 'shape' tab to draw a polygon. Click to create each point around your room. To add more polygons, click 'Add New Area' and draw additional shapes.
5. **Show Coordinates**: Once you have drawn the polygons, click 'Show me the code'.
6. **Extract Coordinates**: The code box will display `coords` properties with x and y coordinates for each point. Convert these to [y, x] pairs.
    - For example, if the coordinates are `coords= "15, 82, 190, 13, 220, 87, 222, 221, 14, 221"`, convert them to `[82, 15], [13, 190], [87, 220], [221, 222], [221, 14]`.
