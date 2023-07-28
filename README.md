# workflow.pams.qa
This repository is meant to serve as an interactive tool that allows users to quickly generate a `.Rmd` report that displays useful comparison statistics between two deliveries of a PAMS dataset. 


It expects paths to two different PAMS datasets as input (for example `PATH/TO/PAMS_2021Q4` and `PATH/TO/PAMS_2022Q4`). The output will be a `html` report, assessing if various expectations are met, comparing the two datasets. 

## How to use the workflow

* Update the file `.config.yml` to point to your two PAMS datasets in question (Note: this file is in the `.gitignore` file, so these paths won't be updated in the actual repo)
* Execute the `.Rmd` file
* Assess the output report, and see if all expectations are met
