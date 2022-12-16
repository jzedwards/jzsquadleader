# Squad Leader Counter Rework
- *Version* 1.0 release
- *Date Created* 19-NOV-22
- *Last Updated* 20-NOV-22
- *Filename* `jzsquadleader-counters-readme-v10.md`
***

## Introduction to jzsquadleader
This content is a new version of counter sheets for Squad Leader, available in 3 formats
- individual counters in SVG
- sheets of counters, in the original layout (SVG and PNG)
- new layout for print and die cutting (SVG and PNG)

If you want to jump to get the files go [here](#getting-the-files)

Squad Leader (SL) is a classic wargame released by the *Avalon Hill Game Company* (AH) in 1977. It simulates tactical, squad level combat in WW2. The original series has 4 games (or expansion *gamettes*)
- Squad Leader https://boardgamegeek.com/boardgame/1035/squad-leader 
- Cross of Iron (German and Soviet war in the East) https://boardgamegeek.com/boardgame/2587/cross-iron-squad-leader-gamette
- Crescendo of Doom (British, French and German early war in the West) https://boardgamegeek.com/boardgame/3609/crescendo-doom-squad-leader-gamette
- GI Anvil of Victory (US, British and German late war in the West) https://boardgamegeek.com/boardgame/5293/gi-anvil-victory-squad-leader-gamette

Squad Leader became a confusing morass of rules, and was *rationalised* into Advanced Squad Leader, now available from (the brilliant) MMP Games https://mmpgamers.com/advanced-squad-leader-c-2
***

## Individual Counters
Individual counters are created in [Adobe Illustrator](#adobe-illustrator). The original counters have 2 sizes, 1/2" (squads, leaders, markers, small equipment) and 5/8" (vehicles, large equipment and markers).

Illustrator is a *vector* format, which saves to SVG, and does not lose quality zooming in (unlike image scans, see [Image Formats](#appendix-image-formats). The Illustrator files have multiple *artboards* which can save each graphic to a named file. We use 800x800 pixels (px) for 1/2" counters and 1000x1000 for 5/8".

The SVG files are in a sub-folder `svg` in the Github/GoogleDrive [share](#getting-the-files)

Files:  
`jzsquadleader-counters-a-b-individual-v10.ai` - 1/2" counters   
`jzsquadleader-counters-c-individual-v10.ai` - 5/8" counters

Examples:  
`c_art` : artillery  
`c_broke` : broken squads/leaders  
`c_eq` : equipment  
`c_mkr` : markers  
`c_veh` : vehicles  

`c_art_50.svg` - 50mm artillery  
`c_broke_ldr_ge_8.svg` - Broken German leader, morale 8

*Note:* if you open the SVG files in an editor (Illustrator or Inkscape) they will **not** be 1/2" or 5/8". This is because AI uses 72ppi (pixels per inch) for the size - so an 800x800 counter is 11.11" in Illustrator (!) and Inkscape uses 96ppi (8.33"). If you want a 1/2" counter for priting, create a 1/2" grid and drop the image in and snap to grid. See [Resolution](#resolution) below.

### SVG Compression
We use [svgo](#svgo) to compress SVGs. This reduces text info and typically halves the file sizes. You can try it with *nano* https://vecta.io/nano or if you are tech capable install node.js and svgo from GitHub https://github.com/svg/svgo

### Fonts and Graphics
The counters are typically a combination of text and graphics.

**Fonts**: Squad Leader fonts do not appear consistent. They vary from game to game, and seem to use some variations within games (eg the number 4 on Cross of Iron). For the original, I have used **Acumin Variable Concept** which is an Adobe font. It is available from 'free' font downloads eg https://www.cufonfonts.com/font/acumin-pro 

**Graphics**: Some graphics are new, some are scanned from original counters, edited and converted to SVG (these are therefore new assets). Finally, some (vehicle) graphics are scanned from AFV line drawings and converted to SVG. I use [NAPS2](#naps2) or VueScan for scanning, and [Photoshop](#adobe-photoshop) or [GIMP](#gimp)  
All of the conversion effort is time consuming, usually taking out print artefacts, converting to black and white and editing the SVG objects created. Objects are also simplified to reduce size, so there are some compromises in the look and feel from the originals.

### Colours
The Illustrator files have few colours - they are mostly black and transparent, with some white, except for a few markers.
The counter sheets are coloured using the Inkscape extension (see below) and/or background layers.

Colo(u)r matching is a pig. Please don't message and say 'the color doesn't match my counters when I print out'. The colour of your printer, and how it looks on screen, and original counters, depends on paper, quality, and the time of day (well, not really...). True colour matching requires pro swatches, and calibrated scanner/screen/printer/paper outputs (or a pro printer).

Accepting these compromises, I (try to) use SVG standard colours. These are orginally designed to be 'web safe' (ie repeatable across web sites on different devices), but for me they give a reasonable, defined colour palette. They are also 'standard' in Inkscape (though not in Illustrator, annoyingly). In summary, SVG colors are just defined RGB values with a name eg *goldenrod* https://www.colorxs.com/color/goldenrod is #DAA520 or RGB 218,165,32 - which, for me, is a good Soviet colour. I use *skyblue* https://color-hex.org/color/87ceeb for Germans.

For the SVG palette see the file `SVG1.1_Color_Swatch.svg` in the share or at https://commons.wikimedia.org/wiki/File:SVG1.1_Color_Swatch.svg 

There is no good match for the (horrid!) US colour for original Squad Leader. For many wargames *olivedrab* https://www.colorxs.com/color/olive-drab works well, and I tempted to do a rework with this colour for the US. I use #d5d22f RGB 213,210,47 https://color-hex.org/color/d5d22f as a close match for my scan/print setup, based on the Photoshop color picker from scans.

*goldenrod*  <img src=".\colour-goldenrod.svg" width="50px"> 
*skyblue* <img src=".\colour-skyblue.svg" width="50px"> 
*olivedrab* <img src=".\colour-olivedrab.svg" width="50px"> 
*Squad Leader US* <img src=".\colour-us.svg" width="50px">

***
## Counter Sheets
There are two styles of counter sheets, *facsimile* originals and versions for (our) die cutter.  
The sheets are created with the [Countersheets Extension for Inkscape](#countersheets-extension-for-inkscape) in [Inkscape](#inkscape). Instructions for the Extension are not in the scope of this readme, but simply, a *Comma Separated Variable* (CSV) file stores the list of counters, and the extension fits them on a set of pages.  
We use [Excel](#excel) to create the csv file content, and save it with [Visual Studio Code](#visual-studio-code) 

`jzsquadleader-counters-a-b-c-img-v10.xlsx`  
`jzsquadleader-counters-a-b-img-v10.csv`  
`jzsquadleader-counters-c-img-v10.csv`  

We will do a YouTube at https://www.youtube.com/jzedward of counter creation, some day...

### Facsimile Sheets
These are intended as reference copies of the original SL sheets. There are 2x 1/2" sheets (A and B) and 1x 5/8" sheet (C, top and bottom).
Original SL 1/2" sheets (Sheets A&B) have 250 counters; 6 blocks of 20 counters, plus one block of 10, left and right.
The 5/8" sheets varied a little; the original SL sheet (Sheet C) has 192 counters; 4 blocks of 3/2/3 rows of 6 counters.
These facsimile versions have cut lines in light grey (this is an option for the Inkscape extension). We will make available versions without cut lines, but they are useful if you are planning print'n'play or counter remakes

Files:  
`jzsquadleader-counters-a-b-img-v10.svg`  
`jzsquadleader-counters-c-img-v10.svg`

Image Files:  
`jzsquadleader-counters-a-img-v10-front.png`  
`jzsquadleader-counters-a-img-v10-rear.png`  
`jzsquadleader-counters-b-img-v10-front.png`  
`jzsquadleader-counters-b-img-v10-rear.png`  
`jzsquadleader-counters-c-img-v10-front.png`  
`jzsquadleader-counters-c-img-v10-rear.png`  

### Die Cut Sheets
At simpubs we have an Ellison die cutter and 1/2" and 5/8" dies (we **are** lucky people). However, we can fit only 240 counters (4x3x20) on a 1/2" sheet and 160 (4x5x8) on a 5/8" sheet. This means that the CSV files are (slightly) different, and that we need an *appendix* counter sheet. There are 5 sheets in this format, numbered 1-5.

Files:  
`pending file links`
***
## Getting the Files
Files are at 2 locations, Github and Google Drive

### Github
https://github.com/jzedwards/jzsquadleader

Github is for saving and sharing (programming) code. It it really designed for text (source code) files and handles changes and revisions. However, it also previews SVG, so is quite nice for sharing the counters. It also saves versions, so I can revise and update any errors. However, GitHub is not good for *binary* files (eg excel, images) so those are shared on GDrive

### Google Drive
https://drive.google.com/drive/folders/1G_IVxTAU05fC2RKiroFnKJYoDbTvbfu8?usp=share_link  
The share is named `jzsquadleader`  
GDrive is a public place to store files; as it has spreadsheet editing and viewing with Google Sheets, it's a good place for the images and spreadsheets for reference.

***
## Software
### NAPS2
https://www.naps2.com/

### Adobe Illustrator
https://www.adobe.com/products/illustrator
File extension .ai

### Adobe Photoshop
https://www.adobe.com/products/photoshop
File extension .psb .psd

### GIMP
https://www.gimp.org/

### Inkscape
https://inkscape.org/
File extension .svg

### Countersheets Extension for Inkscape
https://github.com/lifelike/countersheetsextension 

### svgo
https://github.com/svg/svgo

### ImageMagick
https://imagemagick.org/


### Excel
https://www.microsoft.com/excel

### Visual Studio Code
https://code.visualstudio.com/

### Github
https://github.com/

### Google Drive
https://drive.google.com/

### Vassal
https://vassalengine.org/
My end goal for much of my graphics work is *Vassal*, which is a boardgame simulator in software. Usually, Vassal relies on low quality scans, but using SVG graphics makes for really good display. There is a 'special' Vassal for Squad Leader, *VASL* at https://vasl.info/

### Web Browser
You can view any of the svg files just by dropping into a browser of your choice. I prefer Chrome for personal use, Edge for business (which is based on Chrome). You can use developer tools to see the SVG files too.

### Markdown (.md files)
This file is created in *markdown* https://www.markdownguide.org/getting-started/ which is a text only file, designed to permit (simple) formatting, a bit like HTML (markup), for documentation and note taking. It is not reliant on a specific word processor, and I use it in conjunction with **Obsidian** https://obsidian.md/ 

***

## Contact
We don't publish our email on web sites. That way madness (and spam) lies.  
You can visit https://www.simpubs.org and comment there (a wordpress site) or email jzedward at hotmail dot com. This email is not regularly used and might not guarantee a response. Alternatively, post on the Classic Squad Leader group on Facebook
***
## Appendix: Image Formats
If you don't know the differences between image formats, you can end up with poor quality without knowing why. This is intended as a (very) brief outline of why the formats you use matter.

### SVG Format
SVG is a *vector* format. The key to SVG is they are **not** scans - they are math(s). They describe the image with a formula of *strokes* and *fills* from XY coordinates and curves/lines, so you can zoom up and stay the same (though some images look odd at really big zooms). You can just drop an SVG into your [browser](#web-browser) to see it.

### Resolution
SVG files don't have a resolution; they are *internally* saved in units of pixels (or picas, inches, or mm, but that's another story) but there is no rule of px to inches. We use 800x800 px for 1/2" counters. SVG does NOT have a default ppi setting, though Adobe assumes 72ppi, and Inkscape (and the rest of the internet) assumes 96ppi.

Image files are just a bunch of pixels (usually rectangular) - and have a pixels per inch (ppi) setting (eg 150, 300, 600) which means the number of pixels of the image **is** an exact size. Our preferred image size is US letter 11" x 8.5" @ 600ppi, or 6600 x 5100 pixels. NB changing the PPI without resizing leaves the pixels unchanged (good) but just changes the dimensions (in inches/cm etc).

### Image (Raster) Formats 
Images are just a collection of pixels each with a stored colour value (usually red/blue/green RGB). This is called a *raster* format. The more pixels, the higher the resolution (for a fixed size). This means that making images bigger means guessing (interpolating) how to add pixels to the larger image. It also means compressing and throwing away pixels in smaller images. How images are stored, and compressed, depends on the image type.

### PNG Format
PNG is our *standard* reference format for saving archive images in quality. We use 600ppi PNG as our preferred. PNG is a single layer (see TIF and PSD below), and efficiently compresses without loss of information. However, PNG can be slow to open and save because of this compression (particularly in Photoshop).

### JPG Format
Just don't... unless you understand what you want. JPEG (joint photographic experts group) is (usually) a *lossy* format ie it compresses and throws away information. Whn you save a JPG it will usually save based on a quality settting (maybe 1-10, maybe 1-12, maybe %age, it varies) and that will determine how it compresses the image. It will take blocks of pixels and approximate them to save space. A nice big 600ppi JPG at high quality is fine, but every time you edit, it can change, and lose quality. JPG is great for sharing low quality (eg 150ppi) small reference copies, but it's not an archive format

### TIF Format
TIF (or TIFF) is great; it is lossless, but also supports compression. The compression *inside* a TIF can be LZW or ZIP (or even JPG). TIF files can also save multiple layers. TIF files can therefore be pretty big (compared to PNG or JPG). However, these big files can load quickly. TIF is a good reference format, but it is easy to mistakenly save with layers, or different compression, so PNG is a good, uncomplicated baseline.

### PSD or PSB Format
These are Adobe Photoshop files (which you can open with the free GIMP editor). They save lots of layer and edit information, but are really for editing, not archiving.

***
## Copyleft
This content is shared under a *Creative Commons* CC BY-NC-SA 4.0 International license (Attribution NonCommercial ShareAlike)

> “Creative Commons is a nonprofit organization that helps overcome legal obstacles to the sharing of knowledge and creativity to address the world’s pressing challenges” *(extract from web site)*

You are free to:

- Share — copy and redistribute the material in any medium or format
- Adapt — remix, transform, and build upon the material for any purpose, even commercially.

Under the following terms:
- Attribution — You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that
suggests the licensor endorses you or your use. 
- NonCommercial — You may not use the material for commercial purposes.
- ShareAlike — If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.

For full details see https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode  
https://www.simpubs.org

## Copying and Distribution
Sharing is a positive, natural human instinct. I am happy for these great games to be celebrated and to inform discussion. Any feedback on quality or organisation of content is encouraged. If you share the content, please reference your source and credit the original authors. Thanks are not obligatory, but are welcome.  
Seeking personal gain from others’ efforts is also a human instinct; do not use this material for personal or corporate gain, or seek to claim credit for the work done in collating, cataloguing by presenting this output as your own. That would be so rank that the vile odour wafts all the way to heaven, a fine quote of my very own…
***
## Version History
- 1.0 this release
- 0.2 update
- 0.1 Initial edit

## Changes in this version
- public release

## Corrections in this version
- n/a

## Open Items/Issues
- add die cut file references
