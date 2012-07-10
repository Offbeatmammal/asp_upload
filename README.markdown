Readme for ASP_Upload
====================

What is this?
-------------
ASP_Upload is an ASP.NET script that allows you to upload and resize (multiple) images
without requiring custom controls. It is built in hybrid mode to allow for easy integration
with Classic ASP scripts

[Homepage and demo](http://blog.offbeatmammal.com/post/2005/11/19/Upload-and-resize-and-image-in-ASPNET.aspx)

This sample script was written after a fair bit of frustration searching the web for a good ASP.NET (specifically VB.NET)
 sample of an easy to use block of code that would allow a user to upload an image and have it resized
 (in this case to a thumbnail where the aspect ratio is maintained and a maximum width / height can
 be specified) and saved to the server without filesizes blowing out.

The .Net graphics function getThumbnailImage, while at first glance is very helpful, is not your
 friend. Most digital cameras, for instance, create a thumbnail that is saved as part of the original
 image - and this is what the getThumbnailImage will extract for you 
 (rather than create one from scratch). As these embedded thumbnails can be as small as 40px by 40px 
 it's often not much use when you want a 100px by 100px thumbnail!

The basic resize algorithms are well understood, and there are lots of those out there just a 
Google away (although the added restriction of maximum constraints isn't often bothered with) but 
the biggest issue I had with my original search was finding a sample where the filesize for the 
thumbnail didn't expand to greater than the original filesize! 
It turns out that in most cases the vital 'rawformat' parameter was being missed from the save... 
so my example uses that and hopefully stops people being tripped up by this in the future!

How to use
----------
The script component from the form should be placed on the receiving page, and the form itself whereever 
you want to define the content to be uploaded.

Multiple files can be supported (the form by default only handles one, but by incrementing the counter in
<code>fileFld = request.files(0)</code> you will be able to loop through multiple files on a page


Contribute
----------
This project can be forked from
[Github](https://github.com/Offbeatmammal/asp_upload). Please issue pull
requests from feature branches.
