# Data visualization competition

This repository contains data for the data visualization contest at Reed College in Fall 2020.  The `data` folder contains multiple csv files which can be used for the data visualization contest. The `example_ggplot.Rmd` file contains an example of using `ggplot2` and an extension (`ggrepel`) with the data.

To load the data into your RStudio session, you can run the following block of code:

```{r load_data, message = FALSE, warning = FALSE}
# Load the data
library(tidyverse)
diversity_school <- 
  read_csv("https://raw.githubusercontent.com/Reed-Statistics/data-viz-competition-2020/main/data/diversity_school.csv") %>%
  dplyr::select(-X1)

historical_tuition <- 
  read_csv("https://raw.githubusercontent.com/Reed-Statistics/data-viz-competition-2020/main/data/historical_tuition.csv") %>%
  dplyr::select(-X1)

salary_potential <-
  read_csv("https://raw.githubusercontent.com/Reed-Statistics/data-viz-competition-2020/main/data/salary_potential.csv") %>%
  dplyr::select(-X1)

tuition_cost <-
  read_csv("https://raw.githubusercontent.com/Reed-Statistics/data-viz-competition-2020/main/data/tuition_cost.csv") %>% 
  dplyr::select(-X1)

tuition_income <-
  read_csv("https://raw.githubusercontent.com/Reed-Statistics/data-viz-competition-2020/main/data/tuition_income.csv") %>%
  dplyr::select(-X1)
```

## Data Dictionary

### `tuition_cost.csv`

|variable             |class     |description |
|:--------------------|:---------|:-----------|
|name                 |character |School name |
|state                |character | State name |
|state_code           |character | State Abbreviation |
|type                 |character | Type: Public, private, for-profit|
|degree_length        |character | 4 year or 2 year degree |
|room_and_board       |double    | Room and board in USD |
|in_state_tuition     |double    | Tuition for in-state residents in USD |
|in_state_total       |double    | Total cost for in-state residents in USD (sum of room & board + in state tuition) |
|out_of_state_tuition |double    | Tuition for out-of-state residents in USD|
|out_of_state_total   |double    | Total cost for in-state residents in USD (sum of room & board + out of state tuition) |

### `tuition_income.csv`

|variable    |class     |description |
|:-----------|:---------|:-----------|
|name        |character | School name |
|state       |character | State Name |
|total_price |double    | Total price in USD |
|year        |double    | year |
|campus      |character | On or off-campus |
|net_cost    |double    | Net-cost - average actually paid after scholarship/award |
|income_lvl  |character | Income bracket |

### `salary_potential.csv`

|variable                  |class     |description |
|:-------------------------|:---------|:-----------|
|rank                      |double    | Potential salary rank within state |
|name                      |character | Name of school |
|state_name                |character | state name |
|early_career_pay          |double    | Estimated early career pay in USD |
|mid_career_pay            |double    | Estimated mid career pay in USD |
|make_world_better_percent |double    | Percent of alumni who think they are making the world a better place |
|stem_percent              |double    | Percent of student body in STEM |

### `historical_tuition.csv`

|variable     |class     |description |
|:------------|:---------|:-----------|
|type         |character | Type of school (All, Public, Private) |
|year         |character | Academic year |
|tuition_type |character | Tuition Type All Constant (dollar inflation adjusted), 4 year degree constant, 2 year constant, Current to year, 4 year current, 2 year current |
|tuition_cost |double    | Tuition cost in USD |

### `diversity_school.csv`
|variable         |class     |description |
|:----------------|:---------|:-----------|
|name             |character | School name |
|total_enrollment |double    | Total enrollment of students |
|state            |character | State name |
|category         |character | Group/Racial/Gender category |
|enrollment       |double    | enrollment by category |

## Sources
The orignal data source is [Tuition Tracker](https://www.tuitiontracker.org/). The data cleaning was done by Jesse Mostipak and Thomas Mock for a Tidy Tuesday event in March 2020.
