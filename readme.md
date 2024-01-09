# Introduction

This tool uses Web Clips and [SimpleMDM attributes](https://simplemdm.pdq.com/hc/en-us/articles/9355313240347-Attributes-Custom-Attributes) to place a shortcut to device info on the iOS or iPadOS Home Screen.

The attributes are embedded into the Web Clip as parameters.  A script in the HTML file then returns the attribute in large, monospace type.

## Serial Only

`getserial.html` displays only the serial number when loaded using the `SimpleMDM Serial Displayer Webclip.mobileconfig` on a SimpleMDM managed device.

![Serial Example](https://github.com/DD-PDX/SimpleMDM_Attribute_Displayer/blob/main/Images/serial_only_example.png)

## Default Attributes

`getdefaultattributes.html` displays all default attributes when loaded using the `SimpleMDM Default Attribute Displayer Webclip.mobileconfig` on a SimpleMDM managed device.

![Default Example](https://github.com/DD-PDX/SimpleMDM_Attribute_Displayer/blob/main/Images/default_attributes_example.png)

# Usage

## Recommended Instructions

1. Create a new Web Clip profile in Simple MDM with the appropriate URL.
2. Assign the profile to devices.

### URLs

- Serial Only: https://htmlpreview.github.io/?https://raw.githubusercontent.com/DD-PDX/SimpleMDM_Attribute_Displayer/main/getserial.html?serialnum={{serial_number}}
- Default Attributes: https://htmlpreview.github.io/?https://raw.githubusercontent.com/DD-PDX/SimpleMDM_Attribute_Displayer/main/getdefaultattributes.html?serialnum={{serial_number}}&name={{device_name}}&model={{model}}&phonenum={{phone_number}}&udid={{udid}}

## Alternate Instructions

1. Upload the included mobileconfig profile(s) to SimpleMDM as custom profiles **with attribute support enabled**.
2. Assign the profile(s) to devices.

# More Information

The included web clips use [htmlpreview](https://github.com/htmlpreview/htmlpreview.github.com) to render this example.  The HTML files should be able to be placed on any web server and accessed directly in production.

Icons made with [Icons](https://github.com/SAP/macOS-icon-generator).

The getcustomattributes.html version includes handling for the MAC address and some additional custom attributes.  A prebuilt mobileconfig is not provided here.