# TMSColor v2.2.1
*(c) Copyright 2009-2024 Óscar Toledo Gutiérrez*
*https://nanochess.org/*

Converts a BMP image to TMS9928 bitmap/color format.

    tmscolor.c              TMSColor C language source code.
    vdp_colors.bmp          A reference of VDP colors to use in your images.
    LICENSE                 Source code license.
    README.md               This file.


### Usage guide

    tmscolor [options] image.bmp image.asm [label]
    
    -b     Generates CVBasic source code.
    -n     Removes CVBasic stub code for displaying.
    -s     Process tiles in chunks of 16 pixels high (sprites).
    -sb    Same as above but generates readable bitmap statements (CVBasic mode)
    -t     Generates minimum of tiles required.
    -t1    Same but starting at tile 1 (0-255).
    -e45d2 Replaces color 4 with 5 and d with 2 before processing.
    -fx    Flip image along the X-coordinate (mirror)
    -fy    Flip image along the Y-coordinate
    -m     Generates magic sprites for areas with more than 2 colors
    -p1    Searchs best color combination for photo (slow)
    -p2    Searchs best color combination for photo (2x2 dither) (slow)
    -o result.bmp
           Outputs the final image, plus highlight of errors (if any).

By default it converts the image to assembler code (use option -b for CVBasic code). The *label* argument is for the label name used in the code.

Best photo conversion is generated by this command line:

    tmscolor -p2 photo.bmp photo.asm
    
Or for CVBasic:
    
    tmscolor -b -p2 photo.bmp photo.bas
    
Photos will look better if the contrast is good. Magic sprites will work only with an image of 256x192 pixels.


### Notes

The current official version is v2.2.1.

CVBasic is available from https://github.com/nanochess/CVBasic


### Supporting the developer

If you find TMSColor useful, please show your appreciation making a donation via Paypal ($9 USD suggested) to b-i+y-u+b-i (at) gmail.com

If you find a bug, please report to same email and I'll try to look into it. Because lack of time I cannot guarantee it will be corrected.
