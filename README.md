![license MIT](https://img.shields.io/badge/license-MIT-blue.svg)
## [jsPanel 3.0.0-rc1 released 2016-05-16](#)

**A jQuery plugin to create highly configurable multifunctional floating panels.**

**jsPanels** can be used as a floating, **draggable and resizable panel**, **modal**, **tooltip** or **hint/notifier**.

### jsPanel homepage: [http://jspanel.de](http://jspanel.de/)
### API and examples: [http://jspanel.de/api.html](http://jspanel.de/api.html)

+ [Getting started](#getting-started)
+ [jsPanel options](#jspanel-options)
+ [jsPanel methods](#jspanel-methods)
+ [jsPanel properties](#jspanel-properties)
+ [jsPanel defaults](#jspanel-defaults)


#### A few standard example jsPanels
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462269301/collection_standard_panels_mdou5n.jpg">

#### modal jsPanel
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462269129/jspanel-modal-1_sbr7ku.jpg">

#### stacked modal jsPanels
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462269136/jspanel-modal-stacked-1_nkik7t.jpg">

#### jsPanels as hints/notifiers
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462269115/jspanel-hints-1_l3yflv.jpg">

<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462269123/jspanel-hints-2_vaxwt6.jpg">

#### jsPanels as tooltip
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462269142/jspanel-tooltips-1_wd0sm3.jpg">

#### some more toolbar examples
<img src="http://res.cloudinary.com/stefanstraesser-eu/image/upload/v1462806302/jspanel-toolbars-1_donnw7.jpg">

## [Getting started]()<a href="" id="getting-started"></a>

**If you used jsPanel 2.x already please check the API docs for the migration infos on each jsPanel 3.x option/method/property since a few things changed significantly in jsPanel 3.x.**

### [Dependencies]()
+ **jQuery v2.x**
+ **jQuery UI >= v1.9.2 (js and css)** with at least core, widget, mouse, resizable and draggable
+ **jQuery UI Touch Punch** needed only to enable touch events
+ **HTML5/CSS3 compatible browser**

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
        <!-- loading jQuery UI css (which theme doesn't matter regarding jsPanel) -->
        <link rel="stylesheet" href="vendor/jquery-ui-1.11.4.complete/jquery-ui.min.css">
        <!-- loading jsPanel css -->
        <link rel="stylesheet" href="source/jquery.jspanel.css">
    </head>
    <body>

        <!-- Your HTML goes here -->

        <!-- loading jQuery, jQuery UI and jQuery UI Touch Punch -->
        <script src="vendor/jquery-2.2.3.min.js"></script>
        <script src="vendor/jquery-ui-1.11.4.complete/jquery-ui.min.js"></script>
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
        done: function (data, textStatus, jqXHR, jsPanel) {
        	// the keyword "this" inside the function refers to the jsPanel
        },
        fail: function (jqXHR, textStatus, errorThrown, jsPanel) {
        	//the keyword "this" inside the function refers to the jsPanel
        }
    },
    headerTitle: "my example jsPanel",
    theme:       "rebeccapurple",
    callback: function (jsPanel) {
    	// do whatever you like
        // the keyword "this" inside the callback function refers to the jsPanel
    }
});
```

### [jsPanel options in alphabetical order:]()<a href="" id="jspanel-options"></a>
| option | description | &#x1f517; |
| --- | --- | --- |
| `autoclose` | automatically close a jsPanel after a specified time | [API](http://jspanel.de/api/#option/autoclose) |
| `callback` | a callback function or array of callback functions | [API](http://jspanel.de/api/#option/callback) |
| `config` | passes a prepared configuration object | [API](http://jspanel.de/api/#option/config) |
| `container` | the container element to append the jsPanel to | [API](http://jspanel.de/api/#option/container) |
| `content` | content to append to the jsPanel | [API](http://jspanel.de/api/#option/content) |
| `contentAjax` | content to append to the jsPanel using $.ajax(); | [API](http://jspanel.de/api/#option/contentAjax) |
| `contentIframe` | appends an iframe to the jsPanel content section and loads the url | [API](http://jspanel.de/api/#option/contentIframe) |
| `contentOverflow` | sets the overflow property for the content section | [API](http://jspanel.de/api/#option/contentOverflow) |
| `contentSize` | sets the size of the content section of the jsPanel | [API](http://jspanel.de/api/#option/contentSize) |
| `dblclicks` | configures doubleclick handlers for header, content and footer sections | [API](http://jspanel.de/api/#option/dblclicks) |
| `draggable` | configures the draggable interaction | [API](http://jspanel.de/api/#option/draggable) |
| `footerToolbar` | configures a toolbar for the footer section | [API](http://jspanel.de/api/#option/footerToolbar) |
| `headerControls` | configures the controls (close, minimize buttons etc.) | [API](http://jspanel.de/api/#option/headerControls) |
| `headerTitle` |sets the title/heading of the jsPanel | [API](http://jspanel.de/api/#option/headerTitle) |
| `headerRemove` |removes the complete header section | [API](http://jspanel.de/api/#option/headerRemove) |
| `headerToolbar` |configures a toolbar for the header section | [API](http://jspanel.de/api/#option/headerToolbar) |
| `id` |sets the id attribute for the jsPanel | [API](http://jspanel.de/api/#option/id) |
| `maximizedMargin` |sets margins for a maximized jsPanel | [API](http://jspanel.de/api/#option/maximizedMargin) |
| `onbeforeclose` |sets a hendler for the onbeforeclose event | [API](http://jspanel.de/api/#option/onbeforeclose) |
| `onbeforemaximize` |sets a hendler for the onbeforemaximize event | [API](http://jspanel.de/api/#option/onbeforemaximize) |
| `onbeforeminimize` |sets a hendler for the onbeforeminimize event | [API](http://jspanel.de/api/#option/onbeforeminimize) |
| `onbeforenormalize` |sets a hendler for the onbeforenormalize event | [API](http://jspanel.de/api/#option/onbeforenormalize) |
| `onbeforeresize` |sets a hendler for the onbeforeresize event | [API](http://jspanel.de/api/#option/onbeforeresize) |
| `onclosed` |sets a hendler for the onclosed event | [API](http://jspanel.de/api/#option/onclosed) |
| `onmaximized` |sets a hendler for the onmaximized event | [API](http://jspanel.de/api/#option/onmaximized) |
| `onminimized` |sets a hendler for the onminimized event | [API](http://jspanel.de/api/#option/onminimized) |
| `onnormalized` |sets a hendler for the onnormalized event | [API](http://jspanel.de/api/#option/onnormalized) |
| `onresized` |sets a hendler for the onresized event | [API](http://jspanel.de/api/#option/onresized) |
| `onsmallified` | sets a hendler for the onsmallified event | [API](http://jspanel.de/api/#option/onsmallified) |
| `onunsmallified` |sets a hendler for the onunsmallified event | [API](http://jspanel.de/api/#option/onunsmallified) |
| `paneltype` |configures a jsPanel for use as **modal**, **tooltip** or **hint/notifier** | [API](http://jspanel.de/api/#option/paneltype) |
| `position` |sets the position of a jsPanel | [API](http://jspanel.de/api/#option/position) |
| `resizable` |configures the resizable interaction | [API](http://jspanel.de/api/#option/resizable) |
| `rtl` |set RTL text direction for the complete jsPanel | [API](http://jspanel.de/api/#option/rtl) |
| `setstatus` |creates a jsPanel with a specified status (maximized, minimized etc.) | [API](http://jspanel.de/api/#option/setstatus) |
| `show` |set an entry animation for the jsPanel | [API](http://jspanel.de/api/#option/show) |
| `template` |assign a modified html template for the jsPanel | [API](http://jspanel.de/api/#option/template) |
| `theme` |assign a theme to the jsPanel **(includes support for bootstrap themes)** | [API](http://jspanel.de/api/#option/theme) |

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
| `smallify()` | smallifies/unsmallifies an exsisting jsPanel | [API](http://jspanel.de/api/#method/smallify) |
| `toolbarAdd()` | adds a header or footer toolbar to an exsistinf jsPanel | [API](http://jspanel.de/api/#method/toolbarAdd) |

### [jsPanel properties in alphabetical order:]()<a href="" id="jspanel-properties"></a>
| propety | decription | &#x1f517; |
| --- | --- | --- |
| `content` | represents the jqueryfied div element holding all the content of the jsPanel | [API](http://jspanel.de/api/#property/content) |
| `footer` | references the jqueryfied div element holding the footer toolbar items | [API](http://jspanel.de/api/#property/footer) |
| `header` | references the header section of the jsPanel | [API](http://jspanel.de/api/#property/header) |
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
+ `jspanelbeforemaximize`
+ `jspanelmaximized`
+ `jspanelbeforenormalize`
+ `jspanelnormalized`
+ `jspanelbeforeminimize`
+ `jspanelminimized`
+ `jspanelsmallified`
+ `jspanelsmallifiedmax`

### [jsPanel defaults:]() | [API &#x1f517;](http://jspanel.de/api/#defaults)<a href="" id="jspanel-defaults"></a>
```javascript
$.jsPanel.defaults = {
    "autoclose": false,
    "callback": false,
    "container": 'body',
    "content": false,
    "contentAjax": false,
    "contentIframe": false,
    "contentOverflow": 'hidden',
    "contentSize": {
        width: 400,
        height: 200
    },
    "custom": false,
    "dblclicks": false,
    "draggable": {
        handle: 'div.jsPanel-hdr, div.jsPanel-ftr',
        opacity: 0.8
    },
    "footerToolbar": false
    "headerControls": {
        buttons: true,
        iconfont: 'jsglyph',
        close: false,
        maximize: false,
        minimize: false,
        normalize: false,
        smallify: false
    },
    "headerRemove": false,
    "headerTitle": 'jsPanel',
    "headerToolbar": false,
    "id": () => `jsPanel-${jsPanel.ID += 1}`,
    "maximizedMargin": {
        top: 5,
        right: 5,
        bottom: 5,
        left: 5
    },
    "onbeforeclose": false,
    "onbeforemaximize": false,
    "onbeforeminimize": false,
    "onbeforenormalize": false,
    "onclosed": false,
    "onmaximized": false,
    "onminimized": false,
    "onnormalized": false,
    "paneltype": false,
    "position": {
        elmt: jsP,
        my: 'center',
        at: 'center'
    },
    "resizable": {
        handles: 'n, e, s, w, ne, se, sw, nw',
        autoHide: false,
        minWidth: 40,
        minHeight: 40
    },
    "rtl": false,
    "setstatus": false,
    "show": false,
    "template": false,
    "theme": 'bluegrey'
};

// deviating defaults for modal jsPanels
$.jsPanel.modaldefaults = {
    "draggable": "disabled",
    "headerControls": {buttons: "closeonly"},
    "position": {
        my: 'center',
        at: 'center'
    },
    "resizable": "disabled"
};

// deviating defaults for jsPanel tooltips
$.jsPanel.tooltipdefaults = {
    "draggable": "disabled"
    "headerControls": {buttons: "closeonly"},
    "position": {fixed: false},
    "resizable": "disabled"
};

// deviating defaults for jsPanel hints
$.jsPanel.hintdefaults = {
    "autoclose": 8000,
    "draggable": "disabled",
    "headerControls": {buttons: "closeonly"},
    "resizable": "disabled"
};
```