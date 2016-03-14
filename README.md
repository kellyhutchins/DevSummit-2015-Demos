# WebAppsAndMaps
Demo scripts and code for Dev Summit 2015

# Series of code samples showing common gotchas when working with the ArcGIS API for JavaScript
To test these samples download the contents of the DevSummit2016-Gotchas and set them up to run on your web server. Index.html has details about the included code samples. 


# Tips and Tricks for Developing and Debugging Web Apps using browser based developer tools. 

Browser based tools to track down issues, inspect css, analyze performance and more. 

  - [Chrome Dev Tools]
  - [Microsoft Edge Dev Tools]
  - [Safari Web Inspector]
  - [Firefox Dev Tools]
  
 All of the browser based dev tools have similar capabilites. We'll explore how to use these options to find and fix issues in your web apps. 

Check out [Chrome Canary] or [Firefox Developer Edition] to explore the latest browser features and experiments.

### Network Tab
Run the demo app with the dev tools open and inspect the network traffic. View the request and response info. 

Demo App:  [Query Task] 

### Security
Run the demo app with the dev tools open and view the console tab. Note there is a 'mixed-content' error due to the fact the the https page reqeusted some insecure content. To see details about which content is problematic click the Security tab (available in Chrome Dev Tools). 

Demo App: [Mixed Content Demo]

### Console
Open the dev tools to the console tab and run the demo app. Using the console you can log diagnostic info and enter commands to interact with the app. In this sample map is a global variable so we can access properties via the console. 
``` javascript
// Get the current map extent 
map.geographicExtent

// Get the current map extent in JSON
JSON.stringify(map.geographicExtent)
```
Demo App: [Console Demo]

### Debugging
Use dev tools to set breakpoints and step through your code. Set a breakpoint at line 94 of index.html. Use the tools to step through and inspect the code. 

Demo App: [Debug Demo]

### CSS 
Use the Inspect Element tool to find out the css class names for widgets in the JSAPI.

Demo App: [Directions]

### Snippets
Use snippets to run longer bits of code - can be used to replace bookmarklets. 
Here are the three esri-related snippets shown in the presentation. Note that these require that map be a global variable.
Get Extent Snippet
``` javascript
(function(){require(["dojo/json"],function(j){console.log(j.stringify(function(){var e=map.extent.toJson();e.xmin=parseInt(e.xmin);e.ymin=parseInt(e.ymin);e.xmax=parseInt(e.xmax);e.ymax=parseInt(e.ymax);return e;}()));})})();
```

Get Center Snippet
``` javascript
(function(){
    var c= map.geographicExtent.getCenter();
    console.log([parseFloat(c.x.toFixed(3)), parseFloat(c.y.toFixed(3))]);
})();
```

Get Zoom Snippet
``` javascript
map.getLevel();
```

[Chrome Snippets]
[Firefox Scratchpad]
[Demo Snippets]


[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)
   [Demo Snippets]: <http://www.briangrinstead.com/blog/devtools-snippets>
   [Chrome Snippets]: <https://developers.google.com/web/tools/chrome-devtools/debug/snippets/?hl=en>
   [Firefox Scratchpad]:<https://developer.mozilla.org/en-US/docs/Tools/Scratchpad>
   [Chrome Dev Tools]: <https://developer.chrome.com/devtools>
   [Chrome Canary]: <https://www.google.com/chrome/browser/canary.html>
   [Safari Web Inspector]: <https://developer.apple.com/library/safari/documentation/AppleApplications/Conceptual/Safari_Developer_Guide/Introduction/Introduction.html>
   [Firefox Dev Tools]: <https://developer.mozilla.org/en-US/docs/Tools>
   [Firefox Developer Edition]: <https://developer.mozilla.org/en-US/docs/Tools>
   [Microsoft Edge Dev Tools]: <https://dev.windows.com/en-us/microsoft-edge/platform/documentation/f12-devtools-guide/>
   [Query Task]: <https://developers.arcgis.com/javascript/beta/sample-code/tasks-query/index.html>
   [Mixed Content Demo]: <https://www.arcgis.com/apps/Minimalist/index.html?appid=6dbf11d8c0c84e55b19b864952ec0624>
   [Console Demo]: <http://developers.arcgis.com/javascript/samples/widget_basemap/>
   [Debug Demo]: <http://developers.arcgis.com/javascript/samples/query_buffer>
   [Directions]: <http://developers.arcgis.com/javascript/samples/widget_directions_basic/>
   [@thomasfuchs]: <http://twitter.com/thomasfuchs>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [marked]: <https://github.com/chjj/marked>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [keymaster.js]: <https://github.com/madrobby/keymaster>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]:  <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
