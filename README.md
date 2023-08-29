# workflow.pams.qa
This repository is meant to allow users to easily produce `.Rmd` status reports that compares two PAMS datasets or validate the consistency between a PAMS data set and a related data set.


## Configuration

Configurations are set in the `config.yml` file. 

For a comparison of two PAMS datasets over time, paths must be defined that point to two different PAMS datasets as input (for example `PATH/TO/PAMS_2021Q4` and `PATH/TO/PAMS_2022Q4`).

For a consistency check between a PAMS dataset and a Banks Equity Ownership dataset, paths must be defined that point to the relevant datasets as input (for example `PATH/TO/PAMS_2023Q2` and `PATH/TO/BANKS_EO_2023Q2`).

For a consistency check between a PAMS dataset and a Banks Financial Control dataset, paths must be defined that point to the relevant datasets as input (for example `PATH/TO/PAMS_2023Q2` and `PATH/TO/BANKS_FC_2023Q2`).


The output will be a `html` report, assessing if various expectations are met, comparing the two datasets. 

Threshold values must also be set in the `config.yml` file. 

``` yaml
default:

    compare_pams:
        paths:
            path_pams_base: /PATH/TO/BASE_PAMS.xlsx
            path_pams_compare: /PATH/TO/COMPARE_PAMS.xlsx

        thresholds:
            company_id_threshold: 25
            sectoral_production_threshold: 25
            
    compare_pams_banks_eo:
        paths:
            path_pams: /PATH/TO/PAMS.xlsx
            path_banks_eo: /PATH/TO/BANKS_EO.xlsx

        thresholds:
            share_rows_replicated: 0.99
            relative_tolerance_production: 0.01
            relative_tolerance_emission_factor: 0.01
            
    compare_pams_banks_fc:
        paths:
            path_pams: /PATH/TO/PAMS.xlsx
            path_banks_fc: /PATH/TO/BANKS_EO.xlsx

        thresholds:
            share_rows_replicated: 0.99
            relative_tolerance_production: 0.01
            relative_tolerance_emission_factor: 0.01

```

## How to use the workflow

* Update the file `.config.yml` as explained above
* Knit the `.Rmd` file
* Assess the output report, and see if all expectations are met
