# Introduction

This tool uses [Web Clips](https://support.apple.com/guide/deployment/web-clips-payload-settings-depbc7c7808/web) and MDM variables to place a shortcut to device info on the iOS or iPadOS Home Screen.

## MDM Variables and Attributes:

Terminology may vary, depending on your MDM vendor.  This tool was initially intended for SimpleMDM, which uses "attributes", so that terminology is used in most places.  Consult your MDM's documentation for instructions to embed attributes or variables in mobileconfig profiles.

- [SimpleMDM attributes](https://simplemdm.pdq.com/hc/en-us/articles/9355313240347-Attributes-Custom-Attributes)
- [Jamf Pro Variables](https://learn.jamf.com/en-US/bundle/jamf-pro-documentation-current/page/Mobile_Device_Configuration_Profiles.html)

The attributes are embedded into the Web Clip URL as parameters.  A script in the HTML file then returns the attribute in large, monospace type.

## Arbitrary Attributes

`getarbitraryattributes.html` displays one or more titles and values using numbered pairs of parameters identified as title# and value#, such as:

 	`http://getarbitraryattributes.html?title1=TITLE1&value1=VALUE1&title2=TITLE2&value2=VALUE2`

This would display:

		TITLE1: VALUE1

		TITLE2: VALUE2

Title and value parameters must be in sequential order, starting from 1.  A title and a value must be included for each pair, but either value can be blank.  

## Older Versions:

These older versions are built to display specific variables.  They can be recreated using the arbitrary attributes version above.

## Serial Only

`getserial.html` displays only the serial number when loaded using the `SimpleMDM Serial Displayer Webclip.mobileconfig` on a SimpleMDM managed device.

![Serial Example](https://github.com/DD-PDX/SimpleMDM_Attribute_Displayer/blob/main/Images/serial_only_example.png)

## Default Attributes

`getdefaultattributes.html` displays additional default attributes when loaded using the `SimpleMDM Default Attribute Displayer Webclip.mobileconfig` on a SimpleMDM managed device.

![Default Example](https://github.com/DD-PDX/SimpleMDM_Attribute_Displayer/blob/main/Images/default_attributes_example.png)

# Demo Setup

## Recommended Instructions

1. Create new Web Clip profile(s) in SimpleMDM with the appropriate URL(s).
2. Assign the profile(s) to devices.

### URLs

- Several Jamf Pro Variables:
`https://htmlpreview.github.io/?https://raw.githubusercontent.com/DD-PDX/SimpleMDM_Attribute_Displayer/main/getarbitraryattributes.html?title1=Serial&value1=$SERIALNUMBER&title2=Name&value2=$DEVICENAME&title3=Asset Tag&value3=$ASSET_TAG&title4=Username&value4=$USERNAME&title5=Full Name&value5=$FULLNAME&title6=Email Address&value6=$EMAIL&title7=Phone Number&value7=$PHONE&title8=MAC Address&value8=$MACADDRESS`
- Serial Only (SimpleMDM): `https://htmlpreview.github.io/?https://raw.githubusercontent.com/DD-PDX/SimpleMDM_Attribute_Displayer/main/getserial.html?serialnum={{serial_number}}`
- Default Attributes(SimpleMDM): `https://htmlpreview.github.io/?https://raw.githubusercontent.com/DD-PDX/SimpleMDM_Attribute_Displayer/main/getdefaultattributes.html?serialnum={{serial_number}}&name={{device_name}}&model={{model}}&phonenum={{phone_number}}&udid={{udid}}&wifimac={{wifi_mac_address}}&simplemdmname={{simplemdm_device_name}}`

## Alternate Instructions

1. Upload the included example mobileconfig profile(s) to SimpleMDM as custom profiles **with attribute support enabled**.
2. Assign the profile(s) to devices.

# More Information

The included web clips use [htmlpreview](https://github.com/htmlpreview/htmlpreview.github.com) to render this example.  The HTML files should be able to be placed on any web server and accessed directly in production.

Icons made with [Icons](https://github.com/SAP/macOS-icon-generator).

The `getcustomattributes.html` version includes handling for some additional custom attributes.  A prebuilt mobileconfig is not provided here.