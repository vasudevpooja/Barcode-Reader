# Barcode-Reader
The barcode reader performs a search on selected rows of the input image, called scanlines. Once 
all pixels are transformed, the scanline sequences are analysed. Image processing toolbox for image 
processing, analysis, visualisation and algorithm development was used while designing the code.

# Detect and decode 1-D Barcode
1. Read an image containing a barcode into the workspace.
2. Detect the barcode and decode its message.
3. Display the decoded barcode message.

# Search Image for 1-D Barcode
1. Read an image containing a barcode into the workspace.
2. Search the image for a 1-D barcode, returning its message, format, and location.
3. Display the detected barcode format.
4. Annotate the image with the decoded barcode message.
5. Insert a line to show the scan row.
6. Display the image.

# Concepts
# Input Arguments
**I — Input image**

  • Input image, specified as a truecolor or grayscale image.

**roi — Region of interest**

  • Region of interest, specified as a four-element row vector of the form [x, y, width, height]. 
  The rectangular ROI must be fully contained in the input image. [x,y] specifies the starting point for 
  the ROI relative to the upper-left corner of the image.
  
  • If an image contains multiple barcodes, specifying an ROI can help the function detect a 
  particular barcode.
  
**format — Barcode format**

  • Barcode format, specified as one of these options. The table lists valid barcode formats.
  
  • 'all' — Use this option to specify all valid barcode formats. If you do not specify a format, the 
  function uses this option.
  
  • '1D' — Use this option to specify all valid 1-D barcode formats.
  
  • '2D' — Use this option to specify all valid 2-D barcode formats.
  
  • A character vector or string scalar of a valid format — Use this option to specify one barcode 
  format.
  
  • A cell array of character vectors or vector of strings of valid formats — Use this option to 
  specify multiple barcode formats. The function prioritizes its search for specific barcode formats 
  based on the order of the elements in this array.
  
  • Specifying a format can reduce the run time of the function by restricting the barcode 
  search.
  
![barcode](https://user-images.githubusercontent.com/76071184/145703769-3ac6d075-37da-42ca-957b-ca6855b5e9b8.PNG)

# Output Arguments

  • **msg — Barcode message**
  
  Barcode message, returned as a string scalar.
  
  • **detectedFormat — Detected barcode format**
  
  Detected barcode format, returned as a string scalar of one of the formats in this table.
  
# Points to remember:
1. The function detects only clearly visible barcodes.
2. Specifying a format can reduce the run time of the function by restricting the barcode search.
3. For noisy images with unclear barcodes, use image preprocessing functions, such as imsharpen.
4. The function detects only horizontally or vertically aligned barcodes.Use imrotate to correct 
poorly aligned barcodes
