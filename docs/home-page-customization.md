# Customizing the homepage 

Interested in customizing the homepage? Here are some basic changes you can make

## Changing the image banner 
To change the first image on the home page open _data/theme.yml. Under the home page section, you'll see three variables: 

```
featured-image: arc_008
home-title-y-padding: 15em
home-banner-image-position: 

```

The featured-image varible sets the home page banner. It can be an objectid from the meta data, a relative link to another image in the repository, or a link to an externimal image. 

Home-title-y-padding will set the size of the image. To make it bigger set it to be greater than 15em, to make it smaller make it less than 15 em. 

home-banner-image-position sets the position of the image. There's nothing in it right now, which means by default it will move to center.

## Changing site settings 
After the image banner, there's a description box introducing users to the site. To change it, open up _config.yml. Scroll down to the site settings section. There are 4 variables. 

```
title: Germantown YWCA

tagline: A Social History of a Building

description: The building at 5820 Germantown Avenue in Philadelphia once housed the Germantown YWCA Organization and served as a crucial community resource for nearly a century. Subsequently abandoned, it has become the site of a contentious political battle between many different interests including local residents, neighboring agencies and businesses, real estate developers and political agents. This exhibit aims to tell the histories of the building, the Germantown YWCA organization, and the community surrounding it. 

author: Bryn Mawr College Digital Scholarship
```

title sets the title for the site. If changed in site settings, those changes will be reflected in the nav bar. 

tagline sets the site tagline. It appears with the title in the nav bar. 

author: ??

description: this is where the description for the site is set. If you change it, the text box on the homepage will change. 