[![Build Status](https://travis-ci.org/Flyer53/jsPanel3.svg?branch=master)](https://travis-ci.org/Flyer53/jsPanel3) [![CDNJS](https://img.shields.io/cdnjs/v/jspanel3.svg)](https://cdnjs.com/libraries/jspanel3) ![license MIT](https://img.shields.io/badge/license-MIT-blue.svg) [![npm version](https://badge.fury.io/js/jspanel3.svg)](https://badge.fury.io/js/jspanel3) [![npm](https://img.shields.io/npm/dt/express.svg)](https://www.npmjs.com/package/jspanel3) [![Gitter](https://img.shields.io/gitter/room/nwjs/nw.js.svg)](https://gitter.im/jsPanel/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)

## [jsPanel 3.11.3 released 2019-11-26](#)


**A jQuery plugin to create highly configurable multifunctional floating panels.**

**jsPanels** can be used as a floating, **draggable and resizable panel**, **modal**, **tooltip** or **hint/notifier**.

---
## Don't miss jsPanel version 4
+ [GitHub](https://github.com/Flyer53/jsPanel4)
+ [npm](https://www.npmjs.com/package/jspanel4)
---

### jsPanel homepage: [http://jspanel.de](http://jspanel.de/)
### API and examples: [http://jspanel.de/api](http://jspanel.de/api)

+ [Getting started](#getting-started)
+ [jsPanel options](#jspanel-options)
+ [jsPanel methods](#jspanel-methods)
+ [jsPanel properties](#jspanel-properties)
+ [jsPanel defaults](#jspanel-defaults)

### npm
    npm install jspanel3
### bower
    bower install jspanel3

#### A few standard example jsPanels
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1473692768/collection_standard_panels_ulffys.jpg">

#### modal jsPanel
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462269129/jspanel-modal-1_sbr7ku.jpg">

#### stacked modal jsPanels - [short demo video on youtube](https://youtu.be/cLZ7akOrm_U)
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462269136/jspanel-modal-stacked-1_nkik7t.jpg">

#### jsPanels as hints/notifiers - [short demo video on youtube](https://youtu.be/iUZkVJrq2ys)
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462269115/jspanel-hints-1_l3yflv.jpg">

<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462269123/jspanel-hints-2_vaxwt6.jpg">

#### jsPanels as tooltip - [short demo video on youtube](https://youtu.be/q4ekm8k2W5o)
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462269142/jspanel-tooltips-1_wd0sm3.jpg">

#### some more toolbar examples
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462806302/jspanel-toolbars-1_donnw7.jpg">

## [Getting started]()<a href="" id="getting-started"></a>

**If you used jsPanel 2.x already please check the API docs for the migration infos on each jsPanel 3.x option/method/property since a few things changed significantly in jsPanel 3.x.**

### [Dependencies]()
+ **jQuery 2.x** or **3.x**
+ **HTML5/CSS3 compatible browser** like FF, Chrome, EDGE, Brave and IE11. IE10 and other older browsers are not supported by jsPanel 3.
+ As of version 3.5.0 jQuery ui and jQuery ui touch punch are only required if you still want to use the jQuery ui draggable/resizable interactions

### [Get the files]()
Download and extract the jsPanel package to a folder of your choice. You find at least the two folders **source** and **vendor**.

The **source** folder contains all the necessary jsPanel specific files (.js, .css and font). Copy this folder to your project and rename it as you like if necessary.

The **vendor** folder contains the dependencies jsPanel relies on. Whether you use these files, load them from a CDN or download the desired versions yourself doesn't matter.

### [Include the files]()
The following example shows a complete html file with the minimium setup:

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>jsPanel - a jQuery Plugin</title>
        <!--  optional: loading jQuery UI css (which theme doesn't matter regarding jsPanel) -->
        <link rel="stylesheet" href="vendor/jquery-ui-1.12.1.complete/jquery-ui.min.css">
        <!-- loading jsPanel css -->
        <link rel="stylesheet" href="source/jquery.jspanel.css">
    </head>
    <body>

        <!-- Your HTML goes here -->

        <!-- loading jQuery -->
        <script src="vendor/jquery-3.1.1.min.js"></script>
        <!-- optional: loading jQuery UI and jQuery UI Touch Punch -->
        <script src="vendor/jquery-ui-1.12.1.complete/jquery-ui.min.js"></script>
        <script src="vendor/jquery.ui.touch-punch.min.js"></script>
        <!-- loading jsPanel javascript -->
        <script src="source/jquery.jspanel-compiled.js"></script>
    </body>
</html>
```

### [And then ...]()
After including all the necessary files in your project you can create a jsPanel like ...

```javascript
$.jsPanel( options );

// or
var myPanel = $.jsPanel( options );
```
... where **options** is an object passing the configuration options to the function.

##### Example:

```javascript
$.jsPanel({
	position: {
    	my: "left-top",
        at: "left-top"
    },
    contentSize: {
    	width:  600,
        height: 350
    },
    contentAjax: {
    	url:  // some url,
        done: function (data, textStatus, jqXHR, panel) {
        	// the keyword "this" inside the function refers to the panel
        },
        fail: function (jqXHR, textStatus, errorThrown, panel) {
        	//the keyword "this" inside the function refers to the panel
        }
    },
    headerTitle: "my example jsPanel",
    theme:       "rebeccapurple",
    callback: function (panel) {
    	// do whatever you like
        // the keyword "this" inside the callback function refers to the panel
    }
});
```
