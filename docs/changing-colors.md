# color changes 
This is a guide on how to change the colors of different elements on the site. It assumes you have a decent understanding of CSS, SASS, Bootstrap and HTML.

## Overall theme

Collection builder runs on Bootstrap, a CSS framework that comes with a built in color pallete. ([More information on Bootstrap's color pallete](https://getbootstrap.com/docs/5.0/customize/color/)) Those colors can be changed in config-theme-colors.csv (_data/) If you go in the file you'll see that each bootstrap color corresponds with a hex code. If you deleted those hexcodes the colors would go back to Bootstrap's original pallete. 

## Getting specific

However, the theme doesn't change everything. Sometimes you'll need specific classes. If you look in _custom.scss, the style sheet that changes the default scss, you'll notice specific classes for navbar items, colors, images etc. If you want to get more specific, you may have to add a class. 

## Accessibility

When it comes to making colors accessible, contrast is key. [WebAIM's contrast checker](https://webaim.org/resources/contrastchecker/) is a good tool to use. 