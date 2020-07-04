# Before you start 

## About `plater`

The R package `plater` provides helpful functions for transforming data from plate experiments into "tidy" format for analysis.  You can read more about the plater package here: (https://docs.ropensci.org/plater/).   

A pre-requisite for using the `plater` functions is getting your plate data in the correct format.  `plater` has an excellent vignette that walks through some examples of data formatting and `plater` functions step-by-step: https://cran.r-project.org/web/packages/plater/vignettes/plater-basics.html 

## Purpose of this R Markdown 

If you have many plates worth of data to process, it can take some time and effort to manually create templates for each plate.  In my experience, the process of opening multiple excel files and copy / pasting the data was tedious and easy to mess up if I wasn't paying attention to my clipboard and file names. 

**This script lends a hand by automating the process of preparing micorplate data stored in multiple excel files into the proper format for `plater` functions.**

The script was written to ingest an arbitrary number of excel files with multiple worksheets (tabs) in each file.  It will also work for files with only 1 worksheet.  

## What you need 

- Data exported from the plate reader software (this script assumes .xlsx). The name of each tab should be a plate number or identifier, and each one should be unique.  **Make sure that your "B" plate name includes the text "plate_b"**
- Your plate layouts (map of sample names, blanks, checks on each plate)
- Your lab notebook or notes with information about any known pipetting errors or plate issues that should be flagged for quality control ("Bad Wells")
- A generic plate template.  Templates are available in the `empty_templates` sub-directory for the hydrolytic and oxidative extracellular enzyme assays regularly performed in the Gutknecht lab.  If you need to create your own template, see Step 1 in this tutorial for `plater`'s formatting requirements:  https://cran.r-project.org/web/packages/plater/vignettes/plater-basics.html