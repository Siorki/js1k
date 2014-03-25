My entry "Choose your princess" to js1k 2014
 
The concept is based on [an image compression algorithm by Iñigo Quilez](http://www.iquilezles.org/www/articles/genetic/genetic.htm), altered to use thick rounded lines instead of circles.
Each image is drawn using only 60 lines (360 bytes).


List of files contained in the repository : 
 - princess_uncompressed.js : original code of the entry, before minification and packing
 - lineCompressionGray.html : automated compression tool, using genetic-algorithm to squeeze an image into 60 lines
 - manualLineEditor.html : used to list and edit the coordinates of the 60 lines
 - lineEncoder.html : tool to pack two images represented as array of lines, into an interleaved string for the final entry
 - face8_gray240_edited.png : 1st image before compression, derived from "Portrait" by Jose Carlos Fernandez
 - face8_60lines.png : 1st image, compressed to 60 lines
 - faceB_gray240_edited.png : 2nd image before compression, derived from "Lucy" by Daniel Lee
 - faceB_60lines.png : 2nd image, compressed to 60 lines
 
See LICENSE file for full original image credits.
Image references correctly read 8 and B. There were initially 15 candidates numbered 1 to F.

----

Minimal workflow and tool description :

**lineCompressionGray.html**
Edit the code to choose the image to work with.
*Play* : start the genetic algorithm optimization. Recommended run, 100K to 1M generations. Gradient descent is attempted every 20 generations.
*Pause* : pause the current run, restart with *Play*
*1 Fwd* : compute one generation only
*Export to array* : output the current best to an array in the text box
*Import from array* : import the text box to the algorithm. The current population is kept, so your entry may get discarded during future runs if its score is too low.

**manualLineEditor.html**
Edit the code to choose the image to work with.
Manually tweak the lines of the compressed image.
Used to alter only one image (score shown is for image 1) or get both to match.
*Import* : reads both descriptions and shows the matching images and coordinate sets
*Export* : export both images as separate arrays
*Gradient* : perform one step of gradient descend, on image 1 only
*1* and *2* : hide / show image 2 (for small screens)
*Normalize* : reorder coordinates for both images, without altering the appearance, so that lines are always left to right
*Morph* : preview the morphing animation between the two images
*Round* : round coordinates and line thickness (not luminances) up to a multiple of 2. Used to preview the final result as the last compression step performs this operation.
*Mirror* : horizontal mirror on both images
*Up arrow* and *Down arrow* on each line : swap lines. Use this once both images are complete to get similar features to match.

**lineEncoder.html**
Use this tool only if you aim to run the minified version.
It encodes the coordinates of both images into a string. Coordinates are halved to fit in the ASCII range, then doubled upon rendering (hence the rounding preview operation).
*Check* : attempts to offset the image by a few pixels, staying in the range [1,126], in order to minimize :
 - banned characters (10 and 13) that are not allowed in a string, they are replaced by 11 and 14, slightly altering the image
 - escaped characters (\ and " or ') that require an extra byte to store
*Encode* : offset the image by the provided *dx* and *dy* values, then encode it as an interleaved string to be used by the minified renderer.

If using the original (not minified) code with your own images, remove the leading value (the score) from each array before pasting them into the code.
 

