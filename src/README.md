--
# Welcome to Atlas Vanilla
A Mendix UI Styling Theme optimzed for custom edits


--
# Getting Started with SASS and Atlas Vanilla

## Koala, SASS Compiler
Before you get started, we advise you install and run Koala (free) while 
editing your SASS files. Koala provides you with an easy way to compile 
SASS input into CSS output and helps you check for and locate errors. 
In order to start working with SASS files you simply add your Mendix 
project directory into Koala: 

[Setup Mendix UI Framework with Koala](https://docs.mendix.com/howto50/setup-mendix-ui-framework-with-koala#SetupMendixUIFrameworkwithKoala-3.ConfigureKoala)

[Download Koala](http://koala-app.com/)

## Brackets, Text Editor
For writing your code edits, we suggest you used a code editor like Brackets (free). 
Brackets is a lightweight, yet powerful, modern text editor. We blend visual tools 
into the editor so you get the right amount of help when you want it without getting 
in the way of your creative process:

[Download Brackets](http://brackets.io/)

## Chrome Inspector/Firebug, Modern Broswer Inspector
We use the browser to try out and troubleshoot our code. Chrome’s inspector is 
included but for Firefox you need to download the Firebug extension.

[Download Firebug](http://getfirebug.com/)


--
# Introduction to SASS
SASS is an extension of CSS3, adding nested rules, variables, mixins, 
selector inheritance, and more. It’s translated to well-formatted, 
standard CSS using the command line tool or a web-framework plugin.

SASS has two syntaxes. The new main syntax (as of SASS 3) is known as “SCSS”
(for “Sassy CSS”), and is a superset of CSS3’s syntax. This means that every
valid CSS3 stylesheet is valid SCSS as well. SCSS files use the extension .scss.

The second, older syntax is known as the indented syntax (or just “Sass”).
Inspired by Haml’s terseness, it’s intended for people who prefer conciseness
over similarity to CSS. Instead of brackets and semicolons, it uses the
indentation of lines to specify blocks. Although no longer the primary syntax,
the indented syntax will continue to be supported. Files in the indented syntax
use the extension .sass.

[Refer to SASS documentation for syntax info](http://sass-lang.com/docs.html) 


--
# The UI Framework

## Expedited styling
With the release of 5.18 styling applications in Mendix became a lot easier 
and quicker all thanks to the implementation of the UI Framework. The framework 
is a great baseline to start any application, however do to its size it can be 
daunting to any one new to css. The framework uses a css preprocessor called SASS 
(Syntacticly Awesome Style Sheets). Sass allows the css to be broken into smaller 
easier to edit pieces. These pieces are then combined to create one CSS file.

## Vanilla Theme Framework
If you are interested in having complete control of your styling it is recommended 
to install the Vanilla theme on every new project. Below are the steps to make 
this theme your default style-sheet:

• In your new project click the App Store link in the top right of the Modeler.
• Type vanilla in the search bar, click Vanilla Theme link, and click the 
  download button to import it.
• In Windows Explorer navigate to the theme folder within your project’s folder.
• Click into the Vanilla.zip  le and copy all the contents.
• Paste the copied files into the theme directory, you will want to overwrite
  the existing files.
• In the modeler open up the Project Settings dialog box > Runtime tab. 
  Change the theme drop down from Vanilla to (Default).


--
# Styling and the Modeler

## Connecting the Modeler to style sheets
You need to attach your CSS to a variety of hooks like html tags, classes, 
ID's or directly inline. Those hooks are added within the modeler. You can target 
and style general elements like a form element or data grid or you can create 
a class on a specific item.

## Create Reusable Layouts
The other side of styling an application is creating and managing pages 
and layouts. It is important to have consistency from page to page. 
This is accomplished with the use of page layouts:

• The layouts should be the skeleton frame for your pages.
• Try to limit the number of layouts, for consistency
• Consistency aids the end user with navigation and decreases development time 
  Should not include tables
• Only have elements you want to see on all pages

## Understanding Layout Widgets
There are 3 primary widgets that you can use to organize elements on the page, 
tables, layout grids and container widget. Each have their pros and cons:

### Table
• Not Responsive 
• Avoid using
• Default padding

### Layout Grid
• Responsive
• Left and right padding 
• Try not to nest them

### Container
• Responsive
• No default padding


--
# Where to Develop
There are 2 locations where you can add css:

## In the modeler 
Although this is possible it is highly discouraged. Adding css in the modeler 
is counter productive and you’re limited to what you can style.

## Theme folder 
From your projects root folder you can find a theme > styles folder. 
In order to see changes made in the css files here the project must be 
recompiled in the modeler.


--
# Mendix SASS File Structure

## Barebones Sass Structure
The barebones CSS structure provided in this starterkit uses many of the 
ideas discussed in Jonathan [Snook's SMACSS](http://smacss.com) and is 
intended to provide a starting point for building modular, scalable CSS 
using Sass and Drupal.

Multiple Sass partials are used to help organize the styles, these are combined
by including them in styles.scss which is compiled into styles.css in the css/
directory.

All styles are included in order of specificity, this means that as you go down
the document each section builds upon and inherits sensibly from the previous
ones. This results in less undoing of styles, less specificity problems and
all-round better architected and lighter stylesheets.

## Theme folder structure
The theme folder contains the default HTML pages, Sass, CSS and resources 
needed to style your application. If you want to work purely with SASS, 
there’s no need to pay attention to the css folder.

The custom folder contains a duplication of the folders and files present in 
the lib folder, but without the settings given from the lib folder files.

Everything from the sass\custom folder is imported into the SASS compiler 
at a later stage (i.e. @import statements for the files are added below/after 
the ones from the sass\lib folder), so that your changes will overrule the 
properties as initially set by the Mendix theme you downloaded.

## Workflow
In the Sass folder you will notice two main folders, custom and lib. The lib folder 
houses the complete Mendix UI Framework. The custom folder is where we recommend 
doing *all customizations*. This will making updating to the new framework easier.

## Structure
Mendix is capable of creating beautiful and user-friendly UI. Here you will find 
a basic overview of our framework:

```
theme/
├── styles/
|   ├── css/
|   │   ├── * all output files
|   └── sass/
|       ├── custom/
|       |   ├── _custom-variable.scss
|       |   ├── custom.scss
|       ├── lib/
|           ├── base/
|           ├── buildinblocks/
|           ├── components/
|           ├── customwidgets/
|           ├── layouts/
|           ├── _variable.scss
|           ├── lib.scss
|
├── * index files
├── * assets
```

### Base
The base folder contains the *architecture* for our framework. Here you will 
find our *mixins* and *resets*.

### Components
This directory contains the styling of all kinds of basic components like the 
datagrid, buttons, label, form, listview, and anything along those lines. 
They have distinct properties and can't be broken down further without losing 
their meaning.

### Custom Widgets
This directory contains any extra styling that might be needed for custom 
widgets downloaded from the Mendix App Store.

### Building Blocks
Building blocks are made up of components and widgets. For example *cards* 
or *headers* are building blocks. A building block could be an image, a title, 
and a button, assembled together into one UI block.

### Layouts
The layout directory contains some styles for the main sections of the layout 
(topbar, sidebar, footer and so on).

### Variable.scss
This file contains the style settings that are used across the project, 
allowing for consistent typography, color schemes, etc.

### custom-variables.scss
For basic design changes, go to: _custom-variables.scss 

_custom-variables.scss contains the default variables you can use 
to easily change the basic colors of the app (think of variables as a way to 
store information that you want to reuse throughout your stylesheet).

[Read more on using _custom-variables with the Mendix UI Framework](https://docs.mendix.com/howto/ux/create-a-custom-theme-with-the-mendix-ui-framework)


--
# Custom Styling, Files, and Folders
When it comes to the addition of any custom styling components and styles, 
there are a couple ways you can approach it:

• Add your custom classes within the existing folder and file structure 
  by inserting them into one of the files
• Create your own SCSS file and import it into the SASS compiler
• Create your own folder which resides at the same level as the custom and lib folders

Re-using the existing structure of buttons, datagrid, templategrid, etc. ensures 
anyone working on the project in the future can backtrace the changes made. 

If you have many changes across Mendix components, it could be beneficial 
to create a new file bundling all styling. If you do add files/folders of your own, 
remember the following:

• Files must comply to the established naming format (_filename.scss); 
  it has to start with an underscore and should have the .scss file extension.
• Make sure you @import the created files into the custom.scss file found in the sass\custom.

[For more details on this, make sure you read the SASS quick guide on imports](https://www.mxblog.nl/2016/03/using-sass-with-mendix/)

You can also create your own folder at the same level as the custom and lib folders. 
With this approach, you’ll be able to develop a package (or: theme) of components that is 
implemented on top of the base framework provided. This can be useful when wanting to 
extend the base framework with additions. Or when developing a standard look for a 
multitude of applications belonging to the same company, to better align the look and 
feel with the company’s identity standards. Once you have the developed package, you can
add the folder is added to each application.

Be mindful which method you choose. Each approach has its own pros and cons.
Keep in mind the long-term maintainability of whichever approach you choose.


--
# Tips for Developing
Typically to develop css you would follow this general progression:
• Open the application in the browser.
• Right-Click on the item you want to style
• Navigate with the browser inspector to the correct element
• Look to the right side inspector panel to the styles tab
• Try out your change in the inspector
• Copy html hook and css updates into css/sass file open in brackets.
• Save css/sass  file
• Re-deploy application, the app will auto-refresh in the browser
• Check to ensure changes are made
• If changes are not displaying in your browser, try clearing your cache and restarting.


--
# Further Info
For further information and support, check out the Mendix Developer Community
and our Documentation support:

[Mendix Developer Community](https://developers.mendix.com/)

[Mendix Documentation](https://docs.mendix.com/community/)

[Mendix Model Share](http://modelshare.mendix.com/)

[Mendix Blogs](https://www.mendix.com/blogs/)

[Mendix Academy and Certification](https://gettingstarted.mendixcloud.com/index3.html)


--
# Capabilitiy Specific Information
The following sections have information specific to included assets that let you
further customize your theme.

--
# SassFlexbox
Manage Flexbox in Sass easily. SassFlexbox comes with a bunch of placeholders 
and mixins to helps you using Flexbox, without carrying of vendor prefixes. 
Mixins attempt to use placeholders as soon as possible, to avoid extra compiled code. 

### Display

• `%display-flex`
• `%display-flex-inline`
• **`display-flex()`**
• **`display-flex-inline()`**

### Flex direction

• `%flex-direction-row`
• `%flex-direction-row-reverse`
• `%flex-direction-column`
• `%flex-direction-column-reverse`
• `%flex-direction-inherit`
• **`flex-direction($direction)`** 

### Flex wrap

• `%flex-wrap-nowrap`
• `%flex-wrap-wrap`
• `%flex-wrap-wrap-reverse`
• `%flex-wrap-inherit`
• **`flex-wrap($wrap)`**

### Flex flow

• **`flex-flow($direction, $wrap)`**

### Order

• **`order($order)`**

### Flex grow

• **`flex-grow($grow)`**

### Flex shrink

• **`flex-shrink($shrink)`**

### Flex basis

• **`flex-basis($basis)`**

### Flex

• **`flex($grow, $shrink, $basis)`**

### Justify content

• `%justify-content-flex-start`
• `%justify-content-flex-end`
• `%justify-content-center`
• `%justify-content-space-between`
• `%justify-content-space-around`
• `%justify-content-inherit`
• **`justify-content($justify)`**

### Align items

• `%align-items-flex-start`
• `%align-items-flex-end`
• `%align-items-center`
• `%align-items-baseline`
• `%align-items-stretch`
• `%align-items-inherit`
• **`align-items($align)`**

### Align self

• `%align-self-auto`
• `%align-self-flex-start`
• `%align-self-flex-end`
• `%align-self-center`
• `%align-self-baseline`
• `%align-self-stretch`
• `%align-self-inherit`
• **`align-self($align)`**

### Align content

• `%align-content-flex-start`
• `%align-content-flex-end`
• `%align-content-center`
• `%align-content-space-between`
• `%align-content-space-around`
• `%align-content-stretch`
• `%align-content-inherit`
• **`align-content($align)`**


--
# mx-hover-css
[hover.css file converted for use in Mendix](http://ianlunn.github.io/Hover/)

The Hover classes are best used when you want to call attention to a button or 
element on a page when you mouse over it. Below are some quick instructions on 
how to use them on your project.   

•  Add the class that corresponds to the effect you want your element to show 
   such as `hvr-pulse-grow` 


[For more details on how to use the classes included](http://ianlunn.co.uk/articles/hover-css-tutorial-introduction/)


--
# mx-data-fadein
Sass function/mixin that allows you to sequentially animate in listview items

To use this sass mixin add this line within a listview starting brackets
```
.mx-listview {
    @include fade-in($number: 50, $anime-time: .5s, $delay-time: .3s);
}
```
Change $number value to match the page size of the listview,
       $anime-time value to be the time it takes for an item to fade in,
       $delay-time value to be the time between each items fade in.



--
# mx-animate-css
[Animate.css file converted for use in Mendix](https://daneden.github.io/animate.css/)

The Animate classes are best used when you want to animate elements in or out 
from the screen. Below are some quick instructions on how to use them on your project.   

• Add the class `animated` to the element you want to animate. You may also want 
  to include the class `infinite` for an infinite loop.  
  
• You will also need to add one a class like `bounce` to define how ypu want the 
  element to animate

[For more details on how to use the classes](https://github.com/daneden/animate.css)


--
# License
MIT