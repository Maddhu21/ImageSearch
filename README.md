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

***This documentation includes how to use the various features of the Image Search library***  
This information can be found inside the ImageSearch2015.au3 file  
For more info, go here: [youtube](https://youtu.be/SFxSVksJWmo)  
  

### How to use Image Search(Search Whole Screen) and ImageSearchArea(Search part of the screen):  

  
- ImageSearch: _ImageSearch($findImage, $resultPosition, ByRef $x, ByRef $y, $tolerance, $transparency)  
- ImageSearchArea: _ImageSearchArea($findImage, $resultPosition, $x1, $y1, $right, $bottom, ByRef $x, ByRef $y, $tolerance, $transparency)  
   
 Description:      Find the position of an image on the desktop  
 Syntax:           _ImageSearchArea, _ImageSearch  
 **Parameter(s):**  
> $findImage - the image to locate on the desktop  
> $resultPosition - Set where the returned x,y location of the image is.  
                                     > 1 for centre of image, 0 for top left of image  
>  $x $y - Return the x and y location of the image  
> $tolerance - 0 for no tolerance (0-255). Needed when colors of  
> image differ from desktop. e.g GIF                   
> $transparency - TRANSBLACK, TRANSWHITE or hex value (e.g. 0xffffff) of  
>  the color to be used as transparency; can be omitted if  
>  not needed  
  				  
				  
**Parameters specific to ImageSearchArea:**  
> $x1 $y1 - top left coords of the search area  
> $right $bottom - bottom right coords of the search area. Would be the same as $x2 $y2  
				    
				     
**Return Value(s):**  
> On Success - Returns True  
> On Failure - Returns False  
  
 ###Note: Use _ImageSearch to search the entire desktop, _ImageSearchArea to specify a desktop region to search ### 
  

  

### How to use WaitForImageSearch (one image)  

  
- WaitForImageSearch: _WaitForImageSearch($findImage, $waitSecs, $resultPosition, ByRef $x, ByRef $y, $tolerance, $transparency)  
  
 Description:      Wait for a specified number of seconds for an image to appear  
  
 Syntax:           _WaitForImageSearch, _WaitForImagesSearch  
**Parameter(s):**  
>  $findImage - the image to locate on the desktop  
>  $waitSecs  - seconds to try and find the image  
>  $resultPosition - Set where the returned x,y location of the image is.  
> 1 for centre of image, 0 for top left of image  
> $x $y - Return the x and y location of the image  
>  $tolerance - 0 for no tolerance (0-255). Needed when colors of  
>  image differ from desktop. e.g GIF  
> $transparency - TRANSBLACK, TRANSWHITE or hex value (e.g. 0xffffff) of  
>  the color to be used as transparency can be omitted if  
>  not needed  
  
 **Return Value(s):**  
> On Success - Returns 1  
> On Failure - Returns 0  
  
  

### How to use WaitForImagesSearch (More than one image)  
  
- WaitForImagesSearch: _WaitForImagesSearch($findImage, $waitSecs, $resultPosition, ByRef $x, ByRef $y, $tolerance, $transparency = 0)  
  
 Description:      Wait for a specified number of seconds for any of a set of  
                   images to appear  
  
 Syntax:           _WaitForImagesSearch  
 **Parameter(s):**  
> $findImage - the ARRAY of images to locate on the desktop  
> - ARRAY[0] is set to the number of images to loop through  
>  ARRAY[1] is the first image  
> $waitSecs  - seconds to try and find the image  
> $resultPosition - Set where the returned x,y location of the image is.  
> 1 for centre of image, 0 for top left of image  
> $x $y - Return the x and y location of the image  
> $tolerance - 0 for no tolerance (0-255). Needed when colors of  
> image differ from desktop. e.g GIF  
> $transparent - TRANSBLACK, TRANSWHITE or hex value (e.g. 0xffffff) of  
> the color to be used as transparent; can be omitted if  
> not needed  
  
 **Return Value(s):**  
> On Success - Returns the index of the successful find  
> On Failure - Returns 0  
