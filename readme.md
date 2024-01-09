# Introduction

This tool uses Web Clips and [SimpleMDM attributes](https://simplemdm.pdq.com/hc/en-us/articles/9355313240347-Attributes-Custom-Attributes) to place a shortcut to device info on the iOS or iPadOS Home Screen.

The attributes are embedded into the Web Clip as parameters.  A script in the HTML file then returns the attribute in large, monospace type.

## Serial Only

getserial.html displays only the serial number when loaded using the SimpleMDM Serial Displayer Webclip.mobileconfig on a SimpleMDM managed device.

![Serial Example](https://github.com/DD-PDX/SimpleMDM_Attribute_Displayer/blob/main/Images/serial_only_example.png)

## Default Attributes

getdefaultattributes.html displays all default attributes when loaded using the [SimpleMDM Default Attribute Displayer Webclip.mobileconfig on a SimpleMDM managed device.

![Default Example](https://github.com/DD-PDX/SimpleMDM_Attribute_Displayer/blob/main/Images/default_attributes_example.png)

The included web clips use [htmlpreview](https://github.com/htmlpreview/htmlpreview.github.com) to render this example.  The HTML files should be able to be placed on any web server and accessed directly in production.

Icons made with [Icons](https://github.com/SAP/macOS-icon-generator).