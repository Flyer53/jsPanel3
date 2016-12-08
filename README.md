[![Build Status](https://travis-ci.org/Flyer53/jsPanel3.svg?branch=master)](https://travis-ci.org/Flyer53/jsPanel3) [![CDNJS](https://img.shields.io/cdnjs/v/jspanel3.svg)](https://cdnjs.com/libraries/jspanel3) ![license MIT](https://img.shields.io/badge/license-MIT-blue.svg) [![npm version](https://badge.fury.io/js/jspanel3.svg)](https://badge.fury.io/js/jspanel3)
## [jsPanel 3.5.0 released 2016-12-08](#)

**A jQuery plugin to create highly configurable multifunctional floating panels.**

**jsPanels** can be used as a floating, **draggable and resizable panel**, **modal**, **tooltip** or **hint/notifier**.

### jsPanel homepage: [http://jspanel.de](http://jspanel.de/)
### API and examples: [http://jspanel.de/api](http://jspanel.de/api)

+ [Getting started](#getting-started)
+ [jsPanel options](#jspanel-options)
+ [jsPanel methods](#jspanel-methods)
+ [jsPanel properties](#jspanel-properties)
+ [jsPanel defaults](#jspanel-defaults)

###npm
    npm install jspanel3
###bower
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

#### [CDN]()
jsPanel v3.x is available via [CDNJS](https://cdnjs.com/libraries/jspanel3) as well

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

### [jsPanel options in alphabetical order:]()<a href="" id="jspanel-options"></a>
| option | description | &#x1f517; |
| --- | --- | --- |
| `autoclose` | automatically close a jsPanel after a specified time | [API](http://jspanel.de/api/#option/autoclose) |
| `border` | set border-width and border-style for a jsPanel, border-color is taken from theme | [API](http://jspanel.de/api/#option/border) |
| `callback` | a callback function or array of callback functions | [API](http://jspanel.de/api/#option/callback) |
| `config` | passes a prepared configuration object | [API](http://jspanel.de/api/#option/config) |
| `container` | the container element to append the jsPanel to | [API](http://jspanel.de/api/#option/container) |
| `content` | content to append to the jsPanel | [API](http://jspanel.de/api/#option/content) |
| `contentAjax` | content to append to the jsPanel using $.ajax(); | [API](http://jspanel.de/api/#option/contentAjax) |
| `contentIframe` | appends an iframe to the jsPanel content section and loads the url | [API](http://jspanel.de/api/#option/contentIframe) |
| `contentOverflow` | sets the overflow property for the content section | [API](http://jspanel.de/api/#option/contentOverflow) |
| `contentSize` | sets the size of the content section of the jsPanel | [API](http://jspanel.de/api/#option/contentSize) |
| `dblclicks` | configures doubleclick handlers for header, content and footer sections | [API](http://jspanel.de/api/#option/dblclicks) |
| `delayClose` | sets a delay for the actual removal of a panel upon closing it | [API](http://jspanel.de/api/#option/delayClose) |
| `dragit` | configures the buitl-in draggable interaction | [API](http://jspanel.de/api/#option/dragit) |
| `draggable` | configures the draggable interaction | [API](http://jspanel.de/api/#option/draggable) |
| `footerToolbar` | configures a toolbar for the footer section | [API](http://jspanel.de/api/#option/footerToolbar) |
| `headerControls` | configures the controls (close, minimize buttons etc.) | [API](http://jspanel.de/api/#option/headerControls) |
| `headerLogo` | adds a logo to the header bar | [API](http://jspanel.de/api/#option/headerLogo) |
| `headerTitle` | sets the title/heading of the jsPanel | [API](http://jspanel.de/api/#option/headerTitle) |
| `headerRemove` | removes the complete header section | [API](http://jspanel.de/api/#option/headerRemove) |
| `headerToolbar` | configures a toolbar for the header section | [API](http://jspanel.de/api/#option/headerToolbar) |
| `id` | sets the id attribute for the jsPanel | [API](http://jspanel.de/api/#option/id) |
| `maximizedMargin` | sets margins for a maximized jsPanel | [API](http://jspanel.de/api/#option/maximizedMargin) |
| `minimizeTo` | allows to select a container the minimnized replacement is appanded to or to skip the replacement element | [API](http://jspanel.de/api/#option/minimizeTo) |
| `onbeforeclose` | sets a hendler for the jspanelbeforeclose event | [API](http://jspanel.de/api/#option/onbeforeclose) |
| `onbeforemaximize` | sets a hendler for the jspanelbeforemaximize event | [API](http://jspanel.de/api/#option/onbeforemaximize) |
| `onbeforeminimize` | sets a hendler for the jspanelbeforeminimize event | [API](http://jspanel.de/api/#option/onbeforeminimize) |
| `onbeforenormalize` | sets a hendler for the jspanelbeforenormalize event | [API](http://jspanel.de/api/#option/onbeforenormalize) |
| `onbeforesmallify` | sets a hendler for the jspanelbeforesmallify event | [API](http://jspanel.de/api/#option/onbeforesmallify) |
| `onbeforeunsmallify` | sets a hendler for the jspanelbeforeunsmallify event | [API](http://jspanel.de/api/#option/onbeforeunsmallify) |
| `onbeforeresize` | sets a hendler to call before a panel is resized when using the method .resize() | [API](http://jspanel.de/api/#option/onbeforeresize) |
| `onclosed` | sets a hendler for the jspanelclosed event | [API](http://jspanel.de/api/#option/onclosed) |
| `onfronted` | sets a hendler for the jspanelclosed event | [API](http://jspanel.de/api/#option/onclosed) |
| `onmaximized` | sets a hendler for the jspanelmaximized event | [API](http://jspanel.de/api/#option/onmaximized) |
| `onminimized` | sets a hendler for the jspanelminimized event | [API](http://jspanel.de/api/#option/onminimized) |
| `onnormalized` | sets a hendler for the jspanelnormalized event | [API](http://jspanel.de/api/#option/onnormalized) |
| `onresized` | sets a hendler for the jspanelresized event | [API](http://jspanel.de/api/#option/onresized) |
| `onsmallified` | sets a hendler for the jspanelsmallified event | [API](http://jspanel.de/api/#option/onsmallified) |
| `onunsmallified` | sets a hendler to call after a smallified jsPanel was unsmallified | [API](http://jspanel.de/api/#option/onunsmallified) |
| `onwindowresize` | enables responsivenes to a window resize event | [API](http://jspanel.de/api/#option/onwindowresize) |
| `paneltype` | configures a jsPanel for use as **modal**, **tooltip** or **hint/notifier** | [API](http://jspanel.de/api/#option/paneltype) |
| `position` | sets the position of a jsPanel | [API](http://jspanel.de/api/#option/position) |
| `resizeit` | configures the built-in resizable interaction | [API](http://jspanel.de/api/#option/resizable) |
| `resizable` | configures the resizable interaction | [API](http://jspanel.de/api/#option/resizeit) |
| `rtl` | set RTL text direction for the complete jsPanel | [API](http://jspanel.de/api/#option/rtl) |
| `setstatus` | creates a jsPanel with a specified status (maximized, minimized etc.) | [API](http://jspanel.de/api/#option/setstatus) |
| `show` | set an entry animation for the jsPanel | [API](http://jspanel.de/api/#option/show) |
| `template` | assign a modified html template for the jsPanel | [API](http://jspanel.de/api/#option/template) |
| `theme` | assign a theme to the jsPanel **(includes support for bootstrap themes)** | [API](http://jspanel.de/api/#option/theme) |

### [jsPanel methods in alphabetical order:]()<a href="" id="jspanel-methods"></a>
| method | description | &#x1f517; |
| --- | --- | --- |
| `close()` | closes a jsPanel and removes it from the DOM | [API](http://jspanel.de/api/#method/close) |
| `closeChildpanels()` | closes jsPanels that are appended to the content section of another jsPanel and removes them from the DOM | [API](http://jspanel.de/api/#method/closeChildpanels) |
| `contentReload()` | reloads content of aa exsisting jsPanel | [API](http://jspanel.de/api/#method/contentReload) |
| `contentResize()` | resizes the content section of an exsisting jsPanel | [API](http://jspanel.de/api/#method/contentResize) |
| `headerControl()` | configures individual controls of an exsisting jsPanel | [API](http://jspanel.de/api/#method/headerControl) |
| `headerTitle()` | sets the title of an exsisting jsPanel | [API](http://jspanel.de/api/#method/headerTitle) |
| `front()` | gets a jsPanel to the front by manipulating its z-index | [API](http://jspanel.de/api/#method/front) |
| `maximize()` | maximizes an exsisting jsPanel | [API](http://jspanel.de/api/#method/maximize) |
| `minimize()` | minimizes an exsisting jsPanel | [API](http://jspanel.de/api/#method/minimize) |
| `normalize()`  |normalizes an exsisting jsPanel | [API](http://jspanel.de/api/#method/normalize) |
| `reposition()` | repositions an exsisting jsPanel | [API](http://jspanel.de/api/#method/reposition) |
| `resize()` | resizes an exsisting jsPanel | [API](http://jspanel.de/api/#method/resize) |
| `setTheme()` | switches the theme of an already existing jsPanel | [API](http://jspanel.de/api/#method/setTheme) |
| `smallify()` | smallifies/unsmallifies an exsisting jsPanel | [API](http://jspanel.de/api/#method/setTheme) |
| `toolbarAdd()` | adds a header or footer toolbar to an exsistinf jsPanel | [API](http://jspanel.de/api/#method/toolbarAdd) |

### [jsPanel properties in alphabetical order:]()<a href="" id="jspanel-properties"></a>
| propety | decription | &#x1f517; |
| --- | --- | --- |
| `content` | represents the jqueryfied div element holding all the content of the jsPanel | [API](http://jspanel.de/api/#property/content) |
| `footer` | references the jqueryfied div element holding the footer toolbar items | [API](http://jspanel.de/api/#property/footer) |
| `header` | references the header section of the jsPanel | [API](http://jspanel.de/api/#property/header) |
| `header.logo` | references the logo container | [API](http://jspanel.de/api/#property/header) |
| `header.title` | references the title element | [API](http://jspanel.de/api/#property/header) |
| `header.controls` | references the container for the controls | [API](http://jspanel.de/api/#property/header) |
| `header.toolbar` | references the header toolbar | [API](http://jspanel.de/api/#property/header) |
| `option` | stores the complete jsPanel configuration object and makes it available for later use | [API](http://jspanel.de/api/#property/option) |
| `status` | the current status of a jsPanel is stored in the data attribute `status` | [API](http://jspanel.de/api/#property/status) |


### [jsPanel events:]() | [API &#x1f517;](http://jspanel.de/api/#events)<a href="" id="jspanel-events"></a>
+ `jspanelloaded`
+ `jspanelstatuschange`
+ `jspanelbeforeclose`
+ `jspanelclosed`
+ `jspanelfronted`
+ `jspanelbeforemaximize`
+ `jspanelmaximized`
+ `jspanelbeforenormalize`
+ `jspanelnormalized`
+ `jspanelbeforeminimize`
+ `jspanelminimized`
+ `jspanelbeforesmallify`
+ `jspanelsmallified`
+ `jspanelsmallifiedmax`
+ `jspanelbeforeunsmallify`
+ `jspanelunsmallified`
+ `jspanelstatuschange`

### [jsPanel defaults:]() | [API &#x1f517;](http://jspanel.de/api/#defaults)<a href="" id="jspanel-defaults"></a>
```javascript
$.jsPanel.defaults = {
    autoclose: false,
    border: false,
    callback: false,
    container: 'body',
    content: false,
    contentAjax: false,
    contentIframe: false,
    contentOverflow: 'hidden',
    contentSize: {
        width: 400,
        height: 200
    },
    custom: false,
    dblclicks: false,
    draggable: {
        handle: 'div.jsPanel-hdr, div.jsPanel-ftr',
        opacity: 0.8
    },
    dragit: {
        axis:        false,
        containment: false,
        handles:     '.jsPanel-titlebar, .jsPanel-ftr.active',
        opacity:     0.8,
        start:       false,
        drag:        false,
        stop:        false,
        disableui:   false
    },
    footerToolbar: false,
    headerControls: {
        buttons: true,
        iconfont: 'jsglyph',
        close: false,
        maximize: false,
        minimize: false,
        normalize: false,
        smallify: false
    },
    headerLogo: false,
    headerRemove: false,
    headerTitle: 'jsPanel',
    headerToolbar: false,
    id: () => `jsPanel-${jsPanel.ID += 1}`,
    maximizedMargin: {
        top: 5,
        right: 5,
        bottom: 5,
        left: 5
    },
    minimizeTo: true,
    onbeforeclose: false,
    onbeforemaximize: false,
    onbeforeminimize: false,
    onbeforenormalize: false,
    onbeforesmallify: false,
    onbeforeunsmallify: false,
    onclosed: false,
    onmaximized: false,
    onminimized: false,
    onnormalized: false,
    onbeforeresize: false,
    onresized: false,
    onsmallified: false,
    onunsmallified: false,
    onfronted: false,
    onwindowresize: false,
    position: {
        my: 'center',
        at: 'center'
    },
    resizable: {
        handles: 'n, e, s, w, ne, se, sw, nw',
        autoHide: false,
        minWidth: 40,
        minHeight: 40
    },
    resizeit: {
        containment: false,
        handles:     'n, e, s, w, ne, se, sw, nw',
        minWidth:    40,
        minHeight:   40,
        maxWidth:    10000,
        maxHeight:   10000,
        start:       false,
        resize:      false,
        stop:        false,
        disableui:   false
    },
    rtl: false,
    setstatus: false,
    show: false,
    template: false,
    theme: 'default'
};

// deviating defaults for modal jsPanels
$.jsPanel.modaldefaults = {
    draggable: 'disabled',
    dragit: false,
    headerControls: {controls: 'closeonly'},
    position: 'center',
    resizable: 'disabled',
    resizeit: false,
    onwindowresize: true,
};

// deviating defaults for jsPanel tooltips
$.jsPanel.tooltipdefaults = {
    draggable: 'disabled',
    dragit: false,
    headerControls: {buttons: 'closeonly'},
    position: {fixed: false},
    resizable: disabled,
    resizeit: false,
};

// deviating defaults for jsPanel hints
$.jsPanel.hintdefaults = {
    autoclose: 8000,
    draggable: 'disabled',
    dragit: false,
    headerControls: {buttons: 'closeonly'},
    resizable: 'disabled',
    resizeit: false,
};
```
