# ImportOpenRasterPSP
A simple script to import from OpenRaster format files

Corel PSP does not natively support the OpenRaster format, however the format is so simple that most of the features can be supported without much issue.  The only things PSP doesn't natively support are SVGs.  And text isn't actually defined yet.  

Anything else it might encounter are extensions and software specific.  Which can be ignored.

Two extensions that can be used if present are Edit-lock (in PSP this is alpha-lock only) and selected layer.

It should also be noted that layers are stored in viewing order, so while PSP starts its layering from the bottom OpenRaster starts the layers from the top, the list of nodes must therefore be reversed when implementing them.

Also, because we're using a series of pre-built steps in PSP this is much slower than it would be normally, especially with large images.

## Current Issues
1 - When using "Open As Layer" in PSP it will open the PNG but upon seeing that it's mostly empty will just center the resulting image.  So if a program like GIMP saves out a PNG that is the full size of the image we're working on it'll give a position of 0,0 and either my script will move the visible area to the corner or it'll be centered in canvas with no way of determining where it's supposed to be.

2 - When using "Open As Layer" it always creates the layer at the top of the layer's palette.  If I'm using groups I need a good way to determine how to put it into the appropriate group afterward.


## Library Requirements
* zipfile
* xml.dom 
* os 
* Tkinter 
* tkFileDialog
