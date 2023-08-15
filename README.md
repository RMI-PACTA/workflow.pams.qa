# workflow.pams.qa
This repository is meant to allow users to easily produce a `.Rmd` status report that compares two PAMS datasets.


## Configuration

Configurations are set in the `config.yml` file. 

Paths must be defined that point to two different PAMS datasets as input (for example `PATH/TO/PAMS_2021Q4` and `PATH/TO/PAMS_2022Q4`). The output will be a `html` report, assessing if various expectations are met, comparing the two datasets. 

Threshold values must also be set in the `config.yml` file. 

``` yaml
default:

    paths:
        path_pams_base: /PATH/TO/BASE_PAMS.xlsx
        path_pams_compare: /PATH/TO/COMPARE_PAMS.xlsx

    thresholds:
        company_id_threshold: 25
        sectoral_production_threshold: 25
```

## How to use the workflow

* Update the file `.config.yml` as explained above
* Knit the `.Rmd` file
* Assess the output report, and see if all expectations are met
