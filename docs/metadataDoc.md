---
author: Anna Nguyen
title: Metadata Documentation
---

## Table of Contents
- Setting up the Metadata for Editing
- How to Add Items to the Archive
  - Adding Metadata
  - Uploading the Content Files
- Metadata of the Archive

## Prerequisites
This tutorial assumes you have cloned the germantown-y repository (the repository is where all website files are located) onto a code editor such as Visual Studio Code or have access to edit files on the repository.

## Setting up the Metadata for Editing
On our repository, there should be a CSV file located in the _data folder called **germantown-y-metadata.csv** This file contains all the metadata for each item on our website. The first line of the CSV file lists the metadata fields in the order** the values are presented in the file.

Here is an example:
```
Objectid,filename,title,creator,date
arc_001,arc_001.jpg,Germantown YWCA Upwards View From Entrance Photo,Cameron L Boucher,06/18/2024
```

As we can see here the fields are Objectid,filename,title,creator,date and their respective values are Objectid = arc_001, filename=arc_001.jpg, title=Germantown YWCA Upwards View From Entrance Photo, creator=Cameron L Boucher, date=06/18/2024. Note: Values are usually all on the same line, but due to the size of this document some info may have been folded onto a second line with the rest of the values following.

Now, to make changes download the csv file onto your device and head over to a spreadsheet application for editing.

For this example, I will be using Google Sheets. First, create a blank spreadsheet. Once the spreadsheet is created, navigate to the File button on the upper left and click on the Open option. A pop-up should appear. In the pop-up, select the 'Upload' option. Now, either browse for or drag the germantown-y-metadata.csv file from your folder into Google Sheets. Once uploaded, the cells should be filled with the metadata.

## How to Add Items to the Archive

Before we begin, it is important to note that these instructions are based on the [CollectionBuilder's GitHub walkthrough](https://collectionbuilder.github.io/cb-docs/docs/walkthroughs/gh-walkthrough/). You may refer to the CollectionBuilder Github website for additional information.

There are two components to the archive:
- Metadata (which is a CSV file created from a spreadsheet application)
- Content (e.g images, videos, audios)

You will need to add the Metadata and upload the content files inorder to add to the archive.

### Adding Metadata

First, follow steps on **Setting up the Metadata for Editing above**. After following those instructions, you are now ready to edit the spreadsheet to add the metadata.

Refer to [CollectionBuilder-GH and SHEETS Metadata](https://collectionbuilder.github.io/cb-docs/docs/metadata/gh_metadata/), [CollectionBuilder-CSV Metadata](https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/), and [Formatting Your Metadata](https://collectionbuilder.github.io/cb-docs/docs/metadata/formatting/) for more information on each field and how to format the entry of a specific field. Also, see **Metadata of the Archive** for more info on the metadata of the archive. Here, I will provide brief information about formatting and the fields of the metadata.

Note: Avoid adding commas in specific fields, as CSV files use commas to track data. Additional commas may disrupt how the data appears.

**Objectid:** In the CSV file, the object ID should follow this format: arc_001. It is advised to continue with that format for data consistency.

More information: about this field. Object Identifiers are used for identifying each object on the website and will be used to create each item’s URL. Therefore, the object ID must be a unique string consisting of only lowercase characters and containing no spaces or special characters. However, dashes ( - ) and underscores ( _ ) are fine.

**Filename:** In the CSV file, the filename should follow this format: arc_001.jpg it is advised to continue with that format for data consistency. Make sure the filename is the same as the name of the file/content you will be uploading (this will be in a later step).  The filename can also be an image address. Image addresses are URLs that direct a web browser to an image file on the internet. You can usually obtain an image address by right-clicking on an image online and selecting the 'Copy image address' option. It is best practice to use the image address URL if the image came from an online collection.

More information: about this field. Like the Object ID, the filename should be a unique string with no special characters (dashes and underscores are fine). This field helps the Collection builder find the file you want to associate with the metadata in the row.

**Title**: The title will be used to name the content/object you are adding to the archive on the website.

**Creator**: Insert the author of the file here in this format LastName, FirstName. Then, use semicolons to separate multiple authors.

If commas are messing with the formatting, you will need to wait until you upload the CSV file onto GitHub or your local repository (which is a later step). There you can replace the semicolons in the uplaoded CSV file with commas. Then you must add quotation marks to the beginning of the value and end so that the whole value gets read in as one string. The input should look something ```like this: “WHYY photographer, Bob, John, Sugar, Cain”.```

**Date:** the date should be formatted like this: YYYY-DD-MM. An example would look ```like this: 2012-21-06.``` 
If the month and day are not known it is okay to just put the year.

**Description**: This field is used to talk about the file you specified in filename. Insert context about the file in this field.


**Subject**: This field is for categorizing items in the archive. Users will be able to click on the subjects listed to see other content that have the same subject/tag. Tags must be separated by semicolons ```like this: Philadelphia (Pa.)--Maps; United States--Pennsylvania.```
Additionally subjects must be from the Library of Congress. It might be helpful to look around on one of the versions of the LC Authorities site ([old version](https://authorities.loc.gov/)  or [new version](https://id.loc.gov/authorities/subjects.html)) and find some of the headings there. 
Lastly, keep the headings simple and have no more than three.

**Location:** Insert an address for this field if the file is associated with a location.

**Latitude and Longitude:** If there is an address to the file add the coordinates as well.

**Source:** Input where the file came from in this field.

**Identifier:** If the file/object you are adding to the archive has an identifier (usually items from collection have identifiers) insert it in this field.

**Type:** The type specifies what kind of file the object is. This field can be a one or two value input and should follow the [DCMI Type Vocabulary](https://www.dublincore.org/specifications/dublin-core/dcmi-type-vocabulary/2003-02-12/). 
If a second value is going to be inputted the second value should further specify the file type and should be separated by a semicolon ( ; ). ```Like so: Image;StillImage.```

**Format:** This field indicates the item’s media type. The format for common items should follow the [MIME type standard](https://www.iana.org/assignments/media-types/media-types.xhtml) where a type is followed by a subtype and the subtype is concatenated by a slash ( / ). Here are some common MIME type values:

- Image: image/jpeg, image/png
- Document: application/pdf
- Audio: audio/mp3
- Video: video/mp4

**Language:** Indicate the language the file uses in this field.

**Rights:** This field is for describing the rights over the file in a free-text style.

**Rights Statement:** Input the URL of the rights statement of the file in this field. The URL can be from [creativecommons.org](https://creativecommons.org/) or  [rightsstatements.org](https://rightsstatements.org/en/).

**Display_template:** The display_template field sets the template type for the item in the archive and helps identify the representation of the item on other pages. If this field is not filled out, a default setting will be applied. Default supported options include image, pdf, video, audio, record, item, panorama, compound_object, and multiple. Templates can be viewed and created in the layout folder.

**Image_alt_text:** Insert alt text for the image here. Alt text provides a description of the image for screen readers to use, which helps increase accessibility.

Here is an example input:

**Objectid:** arc_007

**Filename:** http://hiddencityphila.org/wp-content/uploads/2015/01/gtownywca_pastorius.jpg

**Title:** Germantown YWCA and the Pastorius Monument viewed from Vernon Park

**Creator:** Maule, Bradley

**Date:** 2015

**Description:** A photo of the Germantown YWCA building and the Pastorius Monument taken from the viewpoint in Vernon Park.

**Subjects:** Young Women's Christian Association--Buildings; Community Centers; Historic Buildings

**Location:** 5820 Germantown Ave, Philadelphia, PA 19144

**Latitude:** 40.036836

**Longitude:** -75.176593

**Source:** Hidden City Philadelphia

**Identifier:**

**Type:** Image;StillImage

**Format:** image/jpeg

**Language:** eng

**Rights:** Non Exclusive perpetual use

**Rights Statement:** https://rightsstatements.org/page/InC/1.0/?language=en

**Display_template:** image

**object_location:** http://hiddencityphila.org/wp-content/uploads/2015/01/gtownywca_pastorius.jpg

**Image_alt_text:** Image of the Germantown YWCA building and the Pastorius Monument taken from the viewpoint in Vernon Park. The building is in poor condition.

**Object_transcript:**

After finishing adding metadata, download the spreadsheet as a CSV by going to the File menu in the upper left, selecting the Download option, and choosing to download it as a CSV. Then navigate to the website repository (on GitHub or your code editor), locate the _data folder, delete the old germantown-y-metadata.csv file, and upload the new metadata CSV file with the same name as the one deleted.


Now that we have successfully added the metadata to the archive, go to the _config.yml file and check that the metadata is set to the CSV file we added by making sure the filename is the same as the one set there (without the .csv). If the filename of the CSV were ever to change it must be changed here as well.

```
##########
# COLLECTION SETTINGS
#
# Set the metadata for your collection (the name of the csv file in your _data directory that describes the objects in your collection)
# Use the filename of your CSV **without** the ".csv" extension! E.g. _data/demo-metadata.csv --> "demo-metadata"
metadata: germantown-y-metadata
```

### Uploading the Content Files

Before uploading the content files, try to compress the files to reduce space usage, since there is a limited amount of storage. For really big files such as a video or audio, it may be better to upload them onto another platform, such as Youtube, and then add the link of the large file in the filename and location section of the metadata spreadsheet. A useful resource for compressing images is [Squoosh](https://squoosh.app/). Text files usually take up low space, so compressing them is not a concern. 

Additionally, ensure that the filenames in the spreadsheet match the filenames of the files you are uploading. (e.g arc_001.jpg)

Now that the files are ready we can upload them!

In the website repository, navigate to the objects folder. Once there, upload the files to that folder. The archive should now have the added metadata and content! If it is not shown, review the steps and recommended resources to ensure inputs are correct and correspond to their fields.

## Metadata of the Archive

