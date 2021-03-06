shiny apps
================

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.5     ✓ dplyr   1.0.7
    ## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
    ## ✓ readr   2.0.1     ✓ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(viridis)
```

    ## Loading required package: viridisLite

``` r
library(modelr)
library(mgcv)
```

    ## Loading required package: nlme

    ## 
    ## Attaching package: 'nlme'

    ## The following object is masked from 'package:dplyr':
    ## 
    ##     collapse

    ## This is mgcv 1.8-38. For overview type 'help("mgcv-package")'.

``` r
library(patchwork)

knitr::opts_chunk$set(
  fig.width = 6,
  fig.asp = .6,
  out.width = "90%"
)

theme_set(theme_minimal() + theme(legend.position = "bottom"))

options(
  ggplot2.continuous.colour = "viridis",
  ggplot2.continuous.fill = "viridis"
)

scale_colour_discrete = scale_colour_viridis_d
scale_fill_discrete = scale_fill_viridis_d
```

Shiny allows you to create a graphical user interface so users can
interact with your code without knowing R

you write R code and then Shiny creates apps

Shiny apps have 2 components - a user interface to obtain inputs - code
that reacts to inputs and produces outputs

Getting inputs - widgets are text elements that users can interact with
(scroll bars, etc. –&gt; take in user input)

Producing outputs - functions that react to user input form widgets:
renderSomthing()

Flexdashboard + Shiny - RMD shiny document - relatively eacy to user -
adds dynamic elements to a flexdashboard (Start with flexdashboard and
add shiny to it)

Sharing shiny products - not always easy –&gt; shiny requires R to run
in the bockground - can send raw R files to someone who knits and runs
through Rstudio - hosting online - needs a server that runs R in the
backgroun (not R) –&gt; shinyapps.io is most common

OPEN SHINY TEMPLATE - instead of usual flexdashboard, you’re “running”
document rather than knitting - added sidebar column - h3 = header size
(text size) - borough\_choices = we want a vector, not a dataframe, so
that’s why we need to pull
