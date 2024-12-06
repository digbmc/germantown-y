---
author: Anna Nguyen
title: Metadata Documentation
---

## Table of Contents
- [How to Add Items to the Archive](#how-to-add-items-to-the-archive)
  - [Uploading the Metadata](#uploading-the-metadata)
  - [Uploading the Media Files](#uploading-the-media-files)
  - [Troubleshooting](#troubleshooting)
- [Setting up the Metadata for Editing](#setting-up-the-metadata-for-editing)
- [Formatting the metadata](#formatting-the-metadata)
- [Metadata of the Archive](#metadata-of-the-archive)
  - [Missing Data](#missing-data)
  - [Display of the Metadata](#display-of-the-metadata)
  - [Additional Resources](#additional-resources)
- [Editing the metadata](#editing-the-metadata)
  - [About config-metadata.csv](#about-config-metadatacsv)
    - [Adding More Fields to the Metadata](#adding-more-fields-to-the-metadata)
    - [How to Insert Links into the Metadata](#how-to-insert-links-into-the-metadata)
    - [How to Change Metadata Order](#how-to-change-metadata-order)
  - [About config-browsecsv](#about-config-browsecsv)
    - [How to Add a Sort Category](#how-to-add-a-sort-category)
    - [Making a Field Searchable](#making-a-field-searchable)
    - [Rearranging the Order of the Elements in the Preview](#rearranging-the-order-of-the-elements-in-the-preview)

## Useful Vacabulary
Repository: This is where code and files are stored. Our website repository is hosted on GitHub!

Metadata: Information about data such as title, creator, date. Basically, data about data.

CSV file: CSV stands for comma separated values. These files makes it easier for code to read in and parse data due to the file's formatting.

## How to Add Items to the Archive
Before we begin, it is important to note that these instructions are based on the [CollectionBuilder's GitHub walkthrough](https://collectionbuilder.github.io/cb-docs/docs/walkthroughs/gh-walkthrough/). You may refer to the CollectionBuilder Github website for additional information.

There are two components to the archive:
- Metadata (which is a CSV file created from a spreadsheet application)
- Content/media (e.g images, videos, audios)

You will need to upload the Metadata spreadsheet and the media files in order to add to the archive.

### Uploading the Metadata
After adding metadata to the spreadsheet based on the instructions from [*Formatting the Metadata*](#formatting-the-metadata), download the spreadsheet as a CSV by going to the File menu in the upper left, selecting the Download option, and choosing to download it as a CSV. Then navigate to the website repository (on GitHub or your code editor), locate the _data folder, delete the old **germantown-y-metadata.csv** file, and upload the new metadata CSV file with the same name as the one deleted.

### Uploading the Media Files
Before uploading the media files, try to compress the files to reduce space usage, since there is a limited amount of storage. Files should be around 200-500 KB. For really big files such as a video or audio, it may be better to upload them onto another platform, such as Youtube, and then add the link of the large file in the filename and location section of the metadata spreadsheet. A useful resource for compressing images is [Squoosh](https://squoosh.app/). Text files usually take up low space, so compressing them is not a concern. See more size guidlines [here](https://www.shopify.com/blog/image-sizes#1) (Feel free to look for other sources!).

Additionally, ensure that the filenames in the spreadsheet match the filenames of the files you are uploading. (e.g arc_001.jpg)

Now that the files are ready we can upload them!

In the website repository, navigate to the objects folder. Once there, upload the files to that folder. The archive should now have the added metadata and content! 

### Troubleshooting
If the archive items are not showing up, go to the _config.yml file and check that the metadata is set to the CSV file we added by making sure the filename is the same as the one set there (without the .csv). If the filename of the CSV were ever to change it must be changed here as well.
```
##########
# COLLECTION SETTINGS
#
# Set the metadata for your collection (the name of the csv file in your _data directory that describes the objects in your collection)
# Use the filename of your CSV **without** the ".csv" extension! E.g. _data/demo-metadata.csv --> "demo-metadata"
metadata: germantown-y-metadata
```
If issues still persist, review the steps and recommended resources to ensure inputs are correct and correspond to their fields.

## Setting up the Metadata for Editing
If there is already a metadata spreadsheet set up where everyone is working, continue use of that one. This ensures the flow of adding items to the spreadsheet isn't interrupted and that object IDs remain unique. If there isn't an existing spreadsheet, you can create one by following these steps.

On our repository, there should be a CSV file located in the _data folder called **germantown-y-metadata.csv** This file contains all the metadata for each item on our website. The first line of the CSV file lists the metadata fields in the order** the values are presented in the file.

Here is an example:
```
Objectid,filename,title,creator,date
arc_001,arc_001.jpg,Germantown YWCA Upwards View From Entrance Photo,Cameron L Boucher,06/18/2024
```

As we can see here the fields are ```Objectid,filename,title,creator,date``` and their respective values are Objectid = arc_001, filename=arc_001.jpg, title=Germantown YWCA Upwards View From Entrance Photo, creator=Cameron L Boucher, date=06/18/2024. Note: Values are usually all on the same line, but due to the size of this document some info may have been folded onto a second line with the rest of the values following.

Now, to make changes download the CSV file onto your device. If you have a spreadsheet application downloaded on your device you can click on the file within your folder and start editing from there. 

If you do not have a spreadsheet application downloaded, head over to a browser spreadsheet application for editing. For this example, I will be using Google Sheets. First, open the file picker. It's a button shaped like a folder near the grid view button (which looks like a grid) and the sort option button (which has an A and Z on it) on the right side of the screen. A pop-up should appear. In the pop-up, select the Upload option. Now, either browse for or drag the **germantown-y-metadata.csv** file from your folder into Google Sheets. Once uploaded, the cells should be filled with the metadata.

## Formatting the Metadata
First, follow steps on [*Setting up the Metadata for Editing*](#setting-up-the-metadata-for-editing) if you do not already have a metadata spreadsheet. After obtaining a metadata spreadsheet, you are now ready to edit the metadata.

Refer to [CollectionBuilder-GH and SHEETS Metadata](https://collectionbuilder.github.io/cb-docs/docs/metadata/gh_metadata/), [CollectionBuilder-CSV Metadata](https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/), and [Formatting Your Metadata](https://collectionbuilder.github.io/cb-docs/docs/metadata/formatting/) for more information on each field and how to format the entry of a specific field. Also, see [*Metadata of the Archive*](#metadata-of-the-archive) for more info on the metadata of the archive. Here, I will provide brief information about formatting and the fields of the metadata.

Note: Avoid adding commas in specific fields, as CSV files use commas to track data. Additional commas may disrupt how the data appears.

**Objectid:** In the CSV file, the object ID should follow this format: arc_001. The numerical part should be incremented by one for each new entry, starting from the newest file in the collection. Continue with that format for data consistency.

More information: about this field. Object Identifiers are used for identifying each object on the website and will be used to create each item’s URL. Therefore, the object ID must be a unique string consisting of only lowercase characters and containing no spaces or special characters. However, dashes ( - ) and underscores ( _ ) are fine.

**Filename:** In the CSV file, the filename should follow this format: arc_001.jpg. The numerical part should be incremented by one for each new entry, starting from the oldest file in the collection. Continue with that format for data consistency. Make sure the filename is the same as the name of the file/content you will be uploading (this will be in a later step).  The filename can also be an image address. Image addresses are URLs that direct a web browser to an image file on the internet. You can usually obtain an image address by right-clicking on an image online and selecting the Copy image address option. It is best practice to use the image address URL if the image came from an online collection.

More information: about this field. Like the Object ID, the filename should be a unique string with no special characters (dashes and underscores are fine). This field helps the Collection builder find the file you want to associate with the metadata in the row.

**Title**: The title will be used to name the content/object you are adding to the archive on the website.

**Creator**: Insert the author of the file here in this format LastName, FirstName. Then, use semicolons to separate multiple authors.

If commas are messing with the formatting, you will need to wait until you upload the CSV file onto the repository (which is a later step). There you can replace the semicolons in the uploaded CSV file with commas. Then you must add quotation marks to the beginning of the value and end so that the whole value gets read in as one string.

The input should look something like this:
>“WHYY photographer, Bob, John, Sugar, Cain”

**Date:** the date should be formatted like this: YYYY-DD-MM. 

An example would look like this: 
>2012-21-06 or 2000

If the month and day are not known it is okay to just put the year.

**Description**: This field is used to talk about the file you specified in filename. Insert context about the file in this field.


**Subject**: This field is for categorizing items in the archive. Users will be able to click on the subjects listed to see other content that have the same subject/tag. Tags must be separated by semicolons. 

Like this: 
>Philadelphia (Pa.)--Maps; United States--Pennsylvania

Additionally subjects must be from the Library of Congress. It might be helpful to look around on one of the versions of the LC Authorities site ([old version](https://authorities.loc.gov/)  or [new version](https://id.loc.gov/authorities/subjects.html)) and find some of the headings there. 
Lastly, keep the headings simple and have no more than three.

**Location:** Insert an address for this field if the file is associated with a location.

**Latitude and Longitude:** If there is an address to the file add the coordinates as well.

**Source:** Input where the file came from in this field.

**Identifier:** If the file/object you are adding to the archive has an identifier (usually items from collection have identifiers) insert it in this field.

**Type:** The type specifies what kind of file the object is. This field can be a one or two value input and should follow the [DCMI Type Vocabulary](https://www.dublincore.org/specifications/dublin-core/dcmi-type-vocabulary/2003-02-12/). 
If a second value is going to be inputted the second value should further specify the file type and should be separated by a semicolon ( ; ).

Like so: 
>Image;StillImage

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
> Objectid: arc_007
>
>Filename: http://hiddencityphila.org/wp-content/uploads/2015/01/gtownywca_pastorius.jpg
>
>Title: Germantown YWCA and the Pastorius Monument viewed from Vernon Park
>
>Creator: Maule, Bradley
>
>Date: 2015
>
>Description: A photo of the Germantown YWCA building and the Pastorius Monument taken from the viewpoint in Vernon Park.
>
>Subjects: Young Women's Christian Association--Buildings; Community Centers; Historic Buildings
>
>Location: 5820 Germantown Ave, Philadelphia, PA 19144
>
>Latitude: 40.036836
>
>Longitude: -75.176593
>
>Source: Hidden City Philadelphia
>
>Identifier:
>
>Type: Image;StillImage
>
>Format: image/jpeg
>
>Language: eng
>
>Rights: Non Exclusive perpetual use
>
>Rights Statement: https://rightsstatements.org/page/InC/1.0/?language=en
>
>Display_template: image
>
>object_location: http://hiddencityphila.org/wp-content/uploads/2015/01/gtownywca_pastorius.jpg
>
>Image_alt_text: Image of the Germantown YWCA building and the Pastorius Monument taken from the viewpoint in Vernon Park. The building is in poor condition.
>
>Object_transcript:
### Metadata of the Archive
The metadata schema we are using is [Dublin Core](https://www.dublincore.org/resources/metadata-basics/). It includes, but is not limited to, [15 main elements](https://www.dublincore.org/specifications/dublin-core/dces/): Creator, Contributor, Publisher, Title, Date, Language, Format, Subject, Description, Identifier, Relation, Source, Type, Coverage, and Rights.

### Missing Data
Generally, the title, description, identifier, and rights information (if available) for each item are crucial. However, some content may be difficult to find information on and might need to be left blank. If unsure whether a specific field can be left blank, ask a specialist, as elements such as rights information need to be known and approved before making it publicly available online. Though some elements are not mandatory, providing more information, such as date, creator, and subject, is beneficial.

### Display of the Metadata
The order of the metadata and metadata in the preview of an item can be arranged in any way. However, for consistency with other sites, our website follows the order mentioned in this [LibGuide](https://libguides.csudh.edu/DigitalCollectionProjectBestPractices/metadata). The guide shows the order that most sites follow for metadata. For the metadata in the preview, we chose to include the title, creator, date, and source identifier. The preview and order of the metadata may be changed in the future if deemed useful.

### Additional Resources
Additional resources can be found at the following links.

More information on the principles of creating metadata:
- ["Introduction to Metadata" by Murtha Baca](https://www.getty.edu/publications/intrometadata/introduction/)

- [UC Santa Cruz’s LibGuide](https://guides.library.ucsc.edu/c.php?g=618773&p=4306387)

- [North Dakota State Library LibGuide](https://library-nd.libguides.com/digitalprojectstoolkit/metadata)

Example collections for inspiration:
- [Tripod](https://tripod.brynmawr.edu/discovery/search?vid=01TRI_INST:BMC)
- [TriCollege Libraries Digital Collections](https://digitalcollections.tricolib.brynmawr.edu/)

## Editing the metadata

### About Config-metadata.csv
Config-metadata.csv is a CSV file that holds the formatting and settings for the display of the metadata. The file is located in the repository inside the _data folder. The file looks like this:
```
field,display_name,browse_link,external_link
title,Title,
creator,Creator,
description,Description,
date,Date Created,
location,Location
latitude,Latitude
longitude,Longitude
subject,Subjects,true
identifier,Source Identifier,,
type,Type,
format,Format,
source,Source,
rights,Rights,
rightsstatement,Rights Statement,,true
```

Just like germantown-y-metadata.csv, the first line indicates the order and corresponding field values are put in. 

config-metadata.csv is used in these tutorials:
  - [Adding More Fields to the Metadata](#adding-more-fields-to-the-metadata)
  - [How to Insert Links into the Metadata](#how-to-insert-links-into-the-metadata)
  - [How to Change Metadata Order](#how-to-change-metadata-order)

#### Adding more fields to the metadata
To add another field to the metadata, open the metadata spreadsheet and click on a field next to where you want your new field to be. Then either right-click or go to the menu bar, select Insert, then Column, and choose to insert the column either to the right or left. At the top of the new column, enter the name of the field you want to add. You may then enter data for that field.

After you are done entering the data, [*upload the metadata*](#uploading-the-metadata). If you check the CSV file in the repository now, your new field should be there in the top line and all the values of the field should be in the spot indicated by the top line within each row. 

Next, go to the _data folder and locate [**config-metadata.csv**](#about-config-metadatacsv). You must also add your new field there in the row where you want it to be presented. If you are just adding a field without any specific configuration, you can fill out the field and display_name columns in config-metadata.csv. The field should be the name of the new field you added in the CSV, and the display_name is what you want it to be called on the website when it is displayed.

Here is an example:
>date,Date Created

#### How to Insert Links into the Metadata

Each element of the metadata can have links. There are three different ways to add links.

For links that redirect to a search on the website’s archive (such as subjects), set the browse_link value to true in the [**config-metadata.csv**](#about-config-metadatacsv)
file for the field you want this link format for. 

Should look something like this:
>subject,Subjects,true

The field should now be a browse link!

If the field will always be a clickable link to another website (such as the copyright statement field), set the external link value to true in the [**config-metadata.csv**](#about-config-metadatacsv) file. Leave the browse_link value blank and external link value to true.

like so:
>rightsstatement,Rights Statement,,true

Lastly, to create a hyperlink in the metadata, enter the following format in the chosen field of the spreadsheet:

```<a href=”**link**”> **display text**</a>```

#### How to Change Metadata Order
The metadata can be rearranged by simply moving the rows to the desired order for display in the [**config-metadata.csv**](#about-config-metadatacsv) file.

For example, if the initial order was this:
```
title,Title,
creator,Creator,
description,Description,
```
And it was changed to this:
```
title,Title,
description,Description,
creator,Creator,
```
Now, the description will appear before the creator in the metadata.

### About config-browse.csv
**Config-browse.csv** is a CSV file that holds the formatting and settings for the display of the metadata in the preview. The file is located in the repository inside the _data folder. 

The file looks like this:
```
field,display_name,btn,hidden,sort_name
creator,Creator,,,Creator
date,Date,,,Date
description,Description,,true,
subject,Subject,,true,Subject
location,Location,,true,Location
source,Source,,true,Source
identifier,Source Identifier,,
type,Type,,true,Type
format,Format,,true,Format
```
Just like germantown-y-metadata.csv, the first line indicates the order and corresponding field values are put in.

config-browse.csv is used in these tutorials:
  - [How to Add a Sort Category](#how-to-add-a-sort-category)
  - [Making a Field Searchable](#making-a-field-searchable)
  - [Rearranging the Order of the Elements in the Preview](#rearranging-the-order-of-the-elements-in-the-preview)

#### How to Add a Sort Category
In the [**config-browse.csv**](#about-config-browsecsv) file, a sort category can be added by entering a value for field, hidden, and sort_name. The field value is the name of the field in the metadata CSV and the sort name will be the sort category appearing on the site. To hide the field so that it won't appear on the preview of each item in the archive the hidden value should be set to true.

Here is an example:
```
field,display_name,btn,hidden,sort_name
creator,Creator,,,Creator
date,Date,,,Date
description,Description,,true,
subject,,,true,Subject
```
In this example, creator, date, and description will appear on the preview box and have a sort category, while the subject will only appear as a sort category.

#### Making a Field Searchable
Any Field put in the  [**config-browse.csv**](#about-config-browsecsv) will become searchable!

#### Rearranging the order of the Elements in the Preview
This process is similar to [*How to Change Metadata Order*](#how-to-change-metadata-order). Follow the directions there for rearranging the preview elements.
