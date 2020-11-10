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
