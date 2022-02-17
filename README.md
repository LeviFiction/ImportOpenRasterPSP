# ImportOpenRasterPSP
A simple script to import from OpenRaster format files

Corel PSP does not natively support the OpenRaster format, however the format is so simple that most of the features can be supported without much issue.  The only things PSP doesn't natively support are SVGs.  And text isn't actually defined yet.  

Anything else it might encounter are extensions and software specific.  Which can be ignored.

Two extensions that can be used if present are Edit-lock (in PSP this is alpha-lock only) and selected layer.

It should also be noted that layers are stored in viewing order, so while PSP starts its layering from the bottom OpenRaster starts the layers from the top, the list of nodes must therefore be reversed when implementing them.

Also, because we're using a series of pre-built steps in PSP this is much slower than it would be normally, especially with large images.

## Library Requirements
* zipfile
* xml.dom 
* os 
* Tkinter 
* tkFileDialog
