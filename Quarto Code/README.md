---
mainfont: Palatino, Palatino Linotype, serif
author: aRubes
date: 22/-02/2024
title: Updating the tables using rToot
---

# Updating the tables
Date: 22/02/2024

## Intro
 This folder of [Quarto](https://quarto.org/docs/reference/) code is used to re-create the lists from time to time. Files are then manually transfered to other folder in the main and wiki repositories.
 There is more than one way to re-produce them, but either way the process can be summarised by

``` *.qmd file -> Quarto -> knitr -> R -> Pandoc -> final document```
.

everything is handled by Quarto automatically. 
 To update the lists you would need to
 - install [R](https://www.r-project.org/) and either of
   - [Rstudio Desktop](https://posit.co/download/rstudio-desktop/), an IDE for R which comes bundeled with everything (except for the packages described below). In that case only need to install (once) the extra packages, then open the `qmd` and hit `render`. Rstudio will prompt you (once) to install any missing components (`knitr`, `Quarto` or `Pandoc`) if there are any.
   
   - Quarto CLI, a command line utility
   
### Quarto CLI
#### Prereqisites
1. [R](https://www.r-project.org/), a programming language
2. R packages :
```r
linrary(knitr)
library(reactable)
library(rtoot)
library(dplyr)
```
you can install them via `install.packages()`
##### Packages Purpose 
`rtoot` queries the Mastodon API from the instance of interest

`dplyr` dplyr is used for some data wrangling

`reactable` is used to produce a searchable, sortable table

3. Quarto

Pandoc note: To run you'd need Quarto installed, but as Quarto uses its own bundled Pandoc library, you don't need to also have Pandoc pre-installed. If you do have Pandoc installed already and want to use it, it's possible via some command line parameter. 
#### Usage
Example:

```
quarto render `Toootim emoji report GFM.qmd`
```
Quarto will then use`Rscript.exe` (comes with R) to run the R code within, then send it off to Pandoc which will then convert the Markdown document to a HTML/GFM document