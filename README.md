# hoffline
hoffline is jquery based plugin to keep track of current status for internet connection. (This is a work in progress plugin)

The focus of this plugin is to keep track of the internet connection and its status - online or offline. The default navigator object in browsers provide connectivity statuses - 3G//4G or WiFi and so on. But if a user is connected to a internet hotspot which doesn't have internet - device is connected to WiFi but with no internet - then the navigator object is of no use.

HofflineJS is a (super) light weight plugin to check for internet conneection existence and your login can be around it. 

By default, a span tag with ID "currentInternetStatus" gets appended to the body and has either of two strings - "offline" or "online" added to it. This can be altered with the options I have added.

The plugin basically hits the server to check the "dot.png", a very tiny 30bytes image, and awaits response. If the response exists, then the connection is "online", otherwise it is "offline".

You can download the project to view the demo. 

To include the file, simply add this line in your project with correct path. Here, the path is "/js":
<br/>
<code>`<script src='js/hoffline.min.js'></script>`</code>
<br/>
Initializing it can be done with the below line of code:
<code>
var hoffline = new HOffine();
</code>
<br/>
####params
Doing this will generate the span tag with the necessary status, which gets auto updated every 5 seconds. Complete configurable Hoffline is as below:
<code>
var hoffline = new HOffine({
    imgurl: "dot.png", // the image url you want to replace, using the website favicon too seems to be logical
    selectorTag: "span", // the new tag that gets created with the status updates in it
    selectorNewId: "currentInternetStatus", // the id for the selectorTag (span tag in this case)
    getStatusOnTimeInterval: 5000, // regular interval for the status to be updated
    selectorToAppend: "body" // tag to which the selectorTag gets appended 
                            // [Note: use actual selector here, for div with id="selector", pass "#selector"
});
</code>
<br/>
####methods
Following are the methods added to the prototype object HOffline"
<code>
var hoffline = new HOffine();
hoffline.getStatus(); // gets the current internet connection status
hoffline.stopTesting(); // clears the timeout interval during which the tests are scheduled
</code>
    
You can message me anything that you feel is necessary in this plugin and I will work on it and upload as part of updates.
