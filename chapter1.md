---
title: 'Econometrics: Wage gap'
description: 'This chapter deals with estimating the gender pay gap. '
---

## Analyzing the Gender Pay Gap

```yaml
type: VideoExercise
key: b1e3055583
xp: 50
```

`@projector_key`
c8de6b3084beec2c4e24041a02e08d88

---

## Ex 1.1: Introducing the data set

```yaml
type: NormalExercise
key: 42ecbeba83
lang: r
xp: 100
skills: 1
```

The goal of this exercise is to

- load the dataset and tidy it
- get an overview of the variables in the dataset

The WAGES1 file contains 3294 USA working individuals with the following information for 1987. The data are taken from the National Longitudinal Survey (from the companion website to Verbeek).




`@instructions`
- Attach the **tidyverse** packages 
- Use the `read_tsv()` function from the **readr** package. 
- Use **mutate()** to create the logarithms of wages
- Create a factor for **gender**

`@hint`
- Here is the hint for this setup problem. It should get students 50% of the way to the correct answer.

`@pre_exercise_code`
```{r}
# Load datasets and packages here.
```

`@sample_code`
```{r}
# Attach the tidyverse packages
library(tidyverse)

# Loading data with "read_tsv"
wages <- read____("___") %>% as_tibble()
wages

# Add a new variable "log_wage" by transforming wage with the log() function
wages <- wages %>% ___(log_wage = ___(___)) 
wages

# Transfrom the variable "gender" to a factor
wages <- wages %>% ___(gender = ifelse(male == 1, "male", "female")) %>% mutate(gender = ___(gender))
wages
```

`@solution`
```{r}
# Attach the tidyverse packages
library(tidyverse)

# Loading data with "read_tsv"
wages <- read_tsv("../local-data/wages1.dat") %>% as_tibble()
wages

# Add a new variable "log_wage" by transforming wage with the log() function
wages <- wages %>% mutate(log_wage = log(wage)) 
wages

# Transfrom the variable "gender" to a factor
wages <- wages %>% mutate(gender = ifelse(male == 1, "male", "female")) %>% mutate(gender = factor(gender))
wages
```

`@sct`
```{r}
# Update this to something more informative.
success_msg("Some praise! Then reinforce a learning objective from the exercise.")
```
