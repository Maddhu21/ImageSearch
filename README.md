# FAQ
1. What is this Image Search for?
   - It is an AutoIT script made to detect images on screen and return x and y coordinates

2. How does it work?
    - It's a script that find part of screen which you before defined with given image.
  
4. When should I use this?
    - You should use it whenever it's not possible or unlikely that pixelsearch will give what you need.
   
5. How to start using this Image Search?
    - Download the package included and you should place both "ImageSearch.au3" and "ImageSearch.dll" in the same folder as the script you're writing.


### Disclaimer
This script was not created by me and I had no part in building or manipulating it. I post this script here in case the topic is gone. You can find the original topic [Here](https://www.autoitscript.com/forum/topic/148005-imagesearch-usage-explanation/)

# How to use Image Search

- Step 1: 
  Take a screenshot of what you want to be searched and pasted it into paint and then save it as ".bmp"
- Step 2: 
  Save the picture into the same folder/directory of your script
- Step 3: 
  Include "ImageSearch.au3" in your script

***Notes: "ImageSearch.au3" has two functions, _ImageSearch and _ImageSearchArea. Use _ImageSearch to search the entire desktop, _ImageSearchArea to specify a desktop region to search.***

**Parameters for _ImageSearch function (entire screen search)**
> ($findImage,$resultPosition,ByRef $x, ByRef $y,$tolerance, $HBMP=0)

**Parameters for _ImageSearchArea function (you declare part of screen to be searched)**
> ($findImage,$resultPosition,$x1,$y1,$right,$bottom,ByRef $x, ByRef $y, $tolerance,$HBMP=0)

**Description of parameters in ImageSearch.au3 :**
> ; Description:   Find the position of an image on the desktop  
> ; Syntax:        _ImageSearchArea, _ImageSearch  
> ; Parameter(s):  
> ;                $findImage - the image to locate on the desktop  
> ;                $tolerance - 0 for no tolerance (0-255). Needed when colors of  
> ;                            image differ from desktop. e.g GIF  
> ;                $resultPosition - Set where the returned x,y location of the image is.  
> ;                                    1 for centre of image, 0 for top left of image  
> ;                $x $y - Return the x and y location of the image  
> ;  
> ; Return Value(s): On Success - Returns 1  
> ;                On Failure - Returns 0  

# Example
**Using _ImageSearch**  
`#include <ImageSearch.au3>`  
`HotKeySet("p", "checkForImage")`  
`global $y = 0, $x = 0`  
`Func checkForImage() `  
`Local $search = _ImageSearch('checkImage.bmp', 0, $x, $y, 0)`  
`If $search = 1 Then`  
`MouseMove($x, $y, 10)`  
`EndIf`  
`EndFunc`  
`while 1`  
`sleep(200)`  
`WEnd`  
  
**Using _ImageSearchArea**  
`#include <ImageSearch.au3>`  
`HotKeySet("p", "checkForImage")`  
`global $y = 0, $x = 0`  
`Func checkForImage()`  
`local $search = _ImageSearchArea('check5.bmp', 1, 800, 40, 900, 80, $x, $y, 0)`  
`If $search = 1 Then`  
`MouseMove($x, $y, 10)`  
`EndIf`  
`EndFunc`  
`while 1`  
`sleep(200)`  
`WEnd`  
