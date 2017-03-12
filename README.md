<!-- README.md is generated from README.Rmd. Please edit that file -->
### Overview

collapsibleTree is an R htmlwidget that allows you to create interactive collapsible Reingold–Tilford tree diagram using D3.js. Turn your data frame into a hierarchical visualization without worrying about nested lists or JSON objects!

If you're using Shiny, you can bind the most recently clicked node to a Shiny input, allowing for easier interaction with complex nested objects. The input will return a named list containing the most recently selected node, as well as all of its parents. See the Shiny example for more info.

### Installation

``` r
devtools::install_github("AdeelK93/collapsibleTree")
```

### Usage

When working with data in R, it makes sense (at least to me) to represent everything as a data frame. I'm a big fan of [tidy data](https://cran.r-project.org/web/packages/tidyr/vignettes/tidy-data.html), but this structure does not lend itself to easily designing hierarchical networks.

collapsibleTree uses [data.tree](https://cran.r-project.org/web/packages/data.tree/vignettes/data.tree.html) to handle all of that, freeing you from a lot of recursive list construction.

``` r
library(collapsibleTree)

collapsibleTree(warpbreaks, c("wool", "tension", "breaks"))
```

![Collapsible Tree](README-example-1.PNG "Collapsible Tree")

An interactive Shiny version is also included. For example, you could use the collapsibleTree htmlwidget to select a portion of a larger categorical dataset, with your filter being as deep or shallow as you'd prefer.

``` r
shiny::runApp(paste0(system.file(package="collapsibleTree"),"/examples/02shiny"))
```