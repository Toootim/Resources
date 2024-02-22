# Further Processing

the Quarto code for the **GFM file** will create a subdirectory called `DIR` that goes along with that file to the Wiki. since the images' dimensions/resolutions are not equal the result doesn't look good on Github. therefore, an additional step for equalizing dimensions is required.
I used [Image Magick](https://imagemagick.org/Usage/) for this

examples: 
```
magick.exe mogrify -format webp *.webp[128x128]
magick.exe mogrify -format png *.png[128x128]
```
The result is not perfect but good enough