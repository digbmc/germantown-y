
# Advanced

If you're interested in customizing the site beyond adding content, you'll need a local repository on your computer. Working with the repository on your computer makes advanced customization easier. Github limits you to working with one file at a time. Working locally allows you to work with multiple files at once. With Jekyll installed, you can also run a live preview of your site. This is very helpful when you're working on a branch and need to see how it looks before creating a pull request. 

## Working Locally 

If you want to work with the code for the site, you'll need some additional software.

- [Github Account](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home). You need a Github account to add and edit files on the remote repository. 

- [Download VSCode](https://code.visualstudio.com/). VS code is a text editor that will allow you to edit and create files for the site. You can use another text editor, but VS Code is useful because of the active support and extensive library of add-ons. 

- [Install Git](https://collectionbuilder.github.io/cb-docs/docs/software/git/) Git is the version control that Github runs on, and you'll use it to push and pull changes to the site from your local repository, along with branch creation. (rewrite?)

- [Install Ruby](https://collectionbuilder.github.io/cb-docs/docs/software/ruby/). You need to have Ruby downloaded to run

- [Install ImageMagick and Ghostscript](https://collectionbuilder.github.io/cb-docs/docs/software/optional/). This software processes files in the archive


### Creating your local repository

To create your local repository, we're going to be using VS Code's interface. You can also do this in the terminal. Copying an existing repository to your local computer is called cloning. For more detailed instructions, check [Collection Builder's guide on cloning a repository](https://collectionbuilder.github.io/cb-docs/docs/repository/clone/)

#### Using VS Code
1. Open an empty VS Code Window 
2. Under the start menu, select "Clone Git Repository" 
3. In the bar asking for a link to the remote repository, copy and paste this link: https://github.com/digbmc/germantown-y.git
4. When prompted, decide where you want to store your repository. 

#### Using terminal
1. Open your terminal (Git Bash on Windows/Linux, Terminal for Mac) 
- if you're interested in learning more about the terminal check out this [guide to the command line](https://digbmc.github.io/command-line/)

2. Navigate to the folder you want to keep your local copy of the repository. For example, if you wanted to store the site in your documents folder you would enter in the terminal `cd Documents`. The command `cd` stands for "change directory" 
3. Once in that folder, input ``` git clone https://github.com/digbmc/germantown-y.git ``` and press enter
4. Now in documents, there will be a folder titled germantown-y. Open it in VSCode 

### Working with Git in terminal
You can either use [VS Code source control](https://code.visualstudio.com/docs/sourcecontrol/overview) or the terminal to work with Git in VS Code. While VS Code's source control can seem easier at first, terminal can sometimes be quicker and easier. This is a [cheat sheet for git commands](https://education.github.com/git-cheat-sheet-education.pdf)

### Generating the site locally
To generate the site locally, go to [Collection Builder's Guide](https://collectionbuilder.github.io/cb-docs/docs/repository/generate/)

## Site Structure 

The repository has a lot of different folders, so before you start working, it's good to have a sense of what everything does.

### How does Jekyll work? 
Jekyll is a static site generator. It takes the files in the repository and turns them into a site. Like a math or programming input, there's an input and an output. Jekyll looks for certain things - HTML files in the layouts folder, and markdown in the posts folder. The content is then nested in the layout. The reason so many folders start with an underscore is that Jekyll specifically looks for those folders to pull content. 

#### Liquid 
Jekyll also uses [liquid](https://jekyllrb.com/docs/liquid/), a templating languge. Liquid is easy to find - every line of liquid code has {} around it. You don't need to know it in detail, but it's good to recognize, and if you need to know something about it, there's a good chance it will be in the documentation.  

### Folders 
- _data: Data is where the metadata is stored, along with other CSV files that configure elements of the site. 
- _exhibits: Where exhibit posts are stored
- _includes: this is where all the [features] are stored. The subfolders are cb (information about collection builder), features, head (for including information in the `<head>` element), index (features used mostly on the homepage), and js (features that use [Javascript](https://www.w3schools.com/js/default.asp))
- _layouts: if you look in the pages folder, most of the markdown files have a layout variable in the front matter. layouts take the content in the markdown file and format them according to different files in this folder
- _sass: this folder contains the [SASS](https://sass-lang.com/documentation/) used for the site's styling
- _site: this is the folder that stores the output of pages generated by Jekyll. You'll notice that the folder is less bright than the others, that's because _site is in the [.gitignore](https://git-scm.com/docs/gitignore) file. When the site builds, it doesn't track that folder. 
- .github/workflows (look into this one...)
- .jekyll-cache (also look into this one)
- assets: various assets used to generate the site. Subfolders are css, data, img, js, lib, and pics. Aside from adding pictures that aren't in the metadata (ex. project work), there shouldn't be a reason to work in this folder.
- docs: where documentation is stored, along with a folder for the screenshots used
- objects: archive items that are stored locally 
- _pages: files for each page on the site

### Important files
- _config.yml: this is where important information about the site is stored. Jekyll looks for it to configure the site. For example, this is where the metadata spreadsheet is set, where the title is set, the ignores, the plug-ins, and the collections used. (Note: If you change the config file while Jekyll is running, you'll need to stop the build and restart it)
- .gitignored: This is where files and folders for git to ignore are listed.  It keeps version control neater and helps the site run faster.
- 404.html: This is what loads if a link isn't found. If you want to change that page, change the 404 file. 

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
    

### Guide to layouts
Layouts are HTML files that format how pages look. They're HTML files. They include divs and includes that format the content of a page. All of them have a liquid `{{ content }}` element somewhere, that takes the markdown from a page and places it in the layout.  

#### Site Layouts: 
- browse: formatting for the archive section. 
- cloud: layout for word cloud of metadata subjects. Not currently used.
- data: layout for the data page (add data page to site!!)
- default: Outer shell layout: Default serves as a layout for other layouts 
- exhibit-page: the layout for exhibit posts 
- exhibits.html: layout for the exhibits landing page
- history: layout for history page
- home-infographic: layout for the home page
- item.html: generates the item pages in the archive  
- leaflet: for pages with leaflet maps (building and map)
- map: also deletable
- page-full-width.html + page-narrow: page layouts, with varying widths (not used on the site)
- page: basic page layout
- search.html: layout for a site search bar (not featured on the site)
- timeline: layout for a timeline of the metadata. Not currently used. 
- timeline-js: layout for timeline JS feature (not used currently, the timeline is just an iframe)

## Site Styling 
To get into the style of the site, you'll need a solid understanding of [CSS](https://www.w3schools.com/Css/) and [HTML](https://www.w3schools.com/html/). Familiarity with [Bootstrap](https://getbootstrap.com/docs/4.1/getting-started/introduction/) and [SASS](https://sass-lang.com/documentation/). 

Styling files can be found in the _sass folder. _bass.scss, _custom.scss, _pages.scss, _them-colors.scss, and _theme-utilities.scss are CollectionBuilder's stylesheets. _custom.scss overrides the other stylesheets, and it's where the styling for this site is. 


### color changes 

A big component of site styling is color. 

This is a guide on how to change the colors of different elements on the site. It assumes you have a decent understanding of CSS, SASS, Bootstrap, and HTML.

## Overall theme

Collection Builder runs on Bootstrap, a CSS framework with a built-in color palette. ([More information on Bootstrap's color pallete](https://getbootstrap.com/docs/5.0/customize/color/)) Those colors can be changed in config-theme-colors.csv (_data/) If you go into the file you'll see that each bootstrap color corresponds with a hex code. If you deleted those hex codes the colors would go back to Bootstrap's original palette. 

## Getting specific

However, the theme doesn't change everything. Sometimes you'll need specific classes. If you look in _custom.scss, the style sheet that changes the default scss, you'll notice specific classes for navbar items, colors, images, etc. If you want to get more specific, you may have to add a class. 

## Accessibility

When it comes to making colors accessible, contrast is key. [WebAIM's contrast checker](https://webaim.org/resources/contrastchecker/) is a good tool to use. 

### iframes 

iFrames are used across the site for embedding leaflet maps and the timeline 

#### timeline 
The timeline on the history page is generated with an iframe. On the history layout, line 6: 

```<iframe src='https://cdn.knightlab.com/libs/timeline3/latest/embed/index.html?source=1cY9J-XJMjoE2zsrY107C04k1gsyULF2o-maf0OON_-w&font=Default&lang=en&initial_zoom=2&height=650' width='100%' height='650' webkitallowfullscreen mozallowfullscreen allowfullscreen frameborder='0'></iframe>```

To change the timeline, copy the link from [TimelineJS](https://timeline.knightlab.com/) and put it in src 

#### Maps 
From line 13 of the leaflet layout: 
``` <iframe src='{{ site.baseurl }}/{{page.title | downcase }}-js.html' width='100%' height='650' webkitallowfullscreen mozallowfullscreen allowfullscreen frameborder='0'></iframe>```

This one is a little more complicated. Because the leaflet layout is used on both the Germantown map and the building floor plans, the iframe has to work for multiple pages. The liquid `{{ site.baseurl }}/{{page.title | downcase }}-js.html` takes the page title ("Map" for example), reads it as lowercase, and looks for the -js.html at the end.

If you look at pages, you'll see there are html files (webmap-js, building-js). Those are the leaflet files embedded here. If you need to change the leaflet files for webmap or building update the -js files. 
