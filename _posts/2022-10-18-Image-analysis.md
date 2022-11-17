---
layout: post
title: "Image analysis using ExifTool"
subtitle: "Cyber basics #2"
background: '/img/posts/cyber_basics/head_image.jpg'
---

## The ExifTool
If a smartphone or any other camera takes a photo it embeds quite a lot of metadata into the image. Metadata like information about the camera that has been used, the exposure time, the shutter speed. But also information like where the photo was taken or the name of the smartphone might be stored as metadata. If you upload your data to a public domain this information can be seen by anyone who knows how to extract it. A common tool for reading, writing and editing meta information is the so called *ExifTool*.  

![picture-ExifTool](/img/posts/cyber_basics/exiftool.jpg)


## Installation

ExifTool is platform-independent. You can use it on Linux, Windows and Mac. The installation is simple: just download the tool from [the official website](https://exiftool.org/) or install it from your Linux distro repository and execute it. As always here we use Linux:  
        
        sudo apt install exiftool

The ExifTool supports a [huge number of different file formats](https://exiftool.org/#supported).

### How to show stored metadata
With ExifTool showing the metadata stored in an image is easy. On Linux open a terminal and type:

        exiftool your_image.jpg

The output looks something like in the image above. Well, probably in quite a different color...
It is very interesting to see what information is embedded into an image.  

### How to delete all metadata
If you want to uplad an image to a public domain it might be a good idea to delete the image metadata before the upload. Platforms like Instagram or Twitter delete some of the information themselves. But if you upload images to an own website or share it on other platforms the meta information becomes public. In order to delete all the metadata on Linux type:

        exiftool all= your_image.jpg

### How to read out the serial number
In order to read out the cameras serial number embedded into an image type:

        exiftool -SerialNumber your_image.jpg

This might help you to find your camera if it gets stolen. However, not every camera embeds its serial number into the images.

### Much more to explore...
ExifTool is amazing. You can do so much more with it. Change date and time, read out all the information into a csv-file, etc... Have a look at the mentioned websites and discover it yourselfe.


## Further information
- [exiftool.org](https://exiftool.org/)
- [List of the supported file formats](https://exiftool.org/#supported)