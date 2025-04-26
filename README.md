# MSGG - Static Gallery Generator

**msgg** is a Bash script that generates a static HTML gallery from JPG images in a specified directory. It creates thumbnails, preview images, and HTML pages with navigation (previous/next) for viewing the gallery.

## Features

Generates thumbnails (default: 150x150) and previews (default: 800x800).  
Creates an index page with a grid of thumbnails.  
Each image has a dedicated page with navigation (Previous, Next, Back to Gallery).  
Modern HTML structure with CSS styling.  
Portable: works from any directory if dependencies are met.  
Supports custom scripts via head.inc and end.inc (e.g., for Google AdSense or analytics).  

## Requirements

**Bash** (available on Linux/macOS or WSL on Windows).  
**ImageMagick** (convert command) for image processing.  
Install on Debian/Ubuntu: sudo apt-get install imagemagick  
Install on macOS: brew install imagemagick  
Install on Fedora: sudo dnf install imagemagick  

## Installation

Clone the repository:
```git clone https://github.com/masterazz/msgg.git```

Make the script executable: ```chmod +x msgg```

Ensure ImageMagick is installed (see Requirements).

## Usage  
Run the script with a directory containing JPG images:  
```./msgg <dirname>```  

Example:  
./msgg my_photos  

This will:

Create a thumb/ directory with thumbnails.  
Create a prev/ directory with preview images and HTML pages.  
Generate an index.html file with a thumbnail grid.  

The gallery can be viewed by opening index.html in a web browser.

## Output Structure
```
dirname/
├── index.html        # Main gallery page
├── thumb/            # Thumbnails (th*.jpg)
└── prev/             # Preview images (pr*.jpg) and HTML pages (*.html)
```

## Customization

Thumbnail size: Modify **THUMB_SIZE** in the script (default: 150x150>).  
Preview size: Modify **PREVIEW_SIZE** in the script (default: 800x800>).  
Custom scripts:  
Edit **head.inc** to add scripts or styles (e.g., Google AdSense) to the <head> section.  
Edit **end.inc** to add scripts or HTML to the end of the <body> section.  
Example for Google AdSense in head.inc:  
```<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-1234567890123456" crossorigin="anonymous"></script>```

## License  
This project is licensed under the MIT License - see the **LICENSE** file for details.

## Contact  
For questions or suggestions, contact: master@masteraz.ru
