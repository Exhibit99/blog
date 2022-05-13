---
layout: post
title:  "Privacy with Metadata"
date:   2022-04-30 00:00:00 -0500
categories: privacy
image: img/blog/metadata.gif
author: Operation Privacy
---

# MetaData

When you take an image, your camera stores some additional information in the file. You cannot see it unless you inspect the file on a computer.
This is information like:
- Make and model of device that took the image (Cannon, iPhone 6, Samsung Galaxy S3)
- GPS coordinates (if your GPS was on)
- Time and Date
- Author or Creator (taken from the camera settings or editing software)

## Image Metadata
This information stored inside your photo is called **metadata** or **exif data**.

You can use online tools to inspect any image on the internet by providing the image link or uploading it from your computer. Some of the popular ones include:
- [exif.regex.info/exif.cgi](http://exif.regex.info/exif.cgi)
- [exifdata.com](https://exifdata.com/)

## File Metadata
You can also extract metadata from files other than images, like word documents, pdfs, etc. These free online tools help you analyze that:
- [https://intelx.io/tools?tab=filetool](https://intelx.io/tools?tab=filetool)
- [www.metadata2go.com](https://www.metadata2go.com/)

# Metadata Retention Online

Most social media websites remove the metadata from images when you upload them, including Facebook, Instagram, WhatsApp, Signal, and many others. A few keep it to geotag photos or reveal camera information like the photo-sharing site Flickr.

But if you're sending images or documents through email or shared drives, you retain all the metadata.

# Removing Meta Data
- ### Mac

    If you're using a Mac, an easy open-source tool is [ImageOptim.com/Mac](https://imageoptim.com/mac). You can simply right-click on an image file and `Open With > ImageOptim.app`. It will stip off all the metadata.

    ![ImageOptim]({{ site.url }}{{ site.baseurl }}/img/ImageOptim-app.png "ImageOptim")

- ### Windows, Linux, Mac

    A great cross-platform and open-source offline tool is [exifCleaner.com](https://exifcleaner.com/). You simply run the application and drag and drop any files into the window. It will show you what exif data was in it and clean the rest. It will not ask you to confirm removal, it will just remove it the moment you drag it to its interface. Great if you want to save time and clean files in bulk. It will accept many file formats including pdf, images, and videos. It will not strip information from docx files though. 

    ![ImageOptim]({{ site.url }}{{ site.baseurl }}/img/exifcleaner.com.gif "ExifCleaner.com")

- ### Online

    There are a bunch of online tools that will achieve the same but always be careful uploading anything online. The website owner may be storing it for processing for longer than you think or collecting some basic data for gathering statistics.

    [coding.tools/exif-remover](https://coding.tools/exif-remover) is one such site that mentions it will delete uploaded images after 1 hour. You can view and remove exif data using their online tools.

# Modify Metadata
If you want to take this a step further, you can also spread some disinformation for anyone savvy enough to look by altering the file or image metadata.

## Altering File Metadata

Altering the properties of Word, Excel, or pdf documents is easy. In Word, you can go to `Preferences` then `User Information` and changed the displayed name, initials, and company to whatever you want. Once a new file is saved, the properties will show that info. If you export it to pdf, those same properties will carry over.

## Altering Image Metadata
### Online
You can edit the exif data in any image as well. The easiest way is to use an online editor like:
[TheXifer.net](https://www.thexifer.net/)

Once edited, save it and inspect it using the tools mentioned above. You can come up with incongruent information like:

![ImageOptim]({{ site.url }}{{ site.baseurl }}/img/spoofed-exif1.png "Spoofed Exif")

![ImageOptim]({{ site.url }}{{ site.baseurl }}/img/spoofed-exif2.png "Spoofed Exif Detailed")

> ⚠️ Remember: Don't upload any sensitive files online by using online services. You cannot trust if they are storing it or if they're being intercepted.

### Offline
The best offline tool to add, remove and edit exif data is [exiftool.org](https://exiftool.org/).
It is a command-line tool and can take a while to get used to. A good online tutorial with screenshots can be found [here](https://www.ghacks.net/2020/02/01/exiftool-is-an-open-source-and-cross-platform-metadata-editor/).


# Conclusion

Whenever sharing images online please be aware of the hidden data inside images and documents. While most chatting and social media platforms will remove it, email and file-sharing applications will not. This could lead to leaking your location, device specifics or date/time. Don't forget to strip file information from word or pdf files as well when posting them online.

This could be meaningless to most, but it could be valuable at the hands of a stalker, hacker or online OSINT investigator.

