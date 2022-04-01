# Education Brain Drain

These charts and analysis track the flow of students toward a small group of countries using data from the [UNESCO Institute of Statistics](http://data.uis.unesco.org) and [Our World in Data](https://ourworldindata.org/human-development-index).

## ♻️ Use + Remix rights

![[Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0)](https://mirrors.creativecommons.org/presskit/buttons/80x15/png/by.png)

These charts, as well as the analyses that underpin them, are available under a Creative Commons Attribution 4.0 licence. This includes commercial reuse and derivates.

Data in these charts comes from:

* [UNESCO Institute of Statistics](http://data.uis.unesco.org)
* [Our World in Data](https://ourworldindata.org/human-development-index)

**Please attribute 360info and the data sources when you use and remix these visualisations.**

## 📊 Ready-to-use graphics and interactives

Graphics and embeddable interactives are in the [`out`](./out) folder. These can be re-rendered by rendering `index.qmd` (see below).

## 🗂 Get the source data

Derived data is already in the [`docs`](./docs) folder. If you're looking for tidy spreadsheet 


## 💻 Reproduce the analysis

Our graphics are built with Quarto [R](https://quarto.org) and can be found in the`*.qmd` files. Quarto allows reproducible analysis and visualisation to be done in [R](https://r-project,.org), [Python](https://python.org) or [Observable JS](https://observablehq.com/@observablehq/observables-not-javascript).

You'll need to:
- [Download and install Quarto](https://quarto.org/docs/get-started)
- [Download the install R](https://www.r-project.org)
- Satisfy the R package dependencies. In R:
  * Install the [`renv`](https://rstudio.github.io/renv) package with `install.packages("renv")`,
  * Then run `renv::restore()` to install the R package dependencies.
  * (For problems satisfying R package dependencies, refer to [Quarto's documentation on virtual environments](https://quarto.org/docs/projects/virtual-environments.html).)

Now, render the `.qmd` files to the `/out` directory with:

```sh
quarto render
```

## ❓ Help

If you find any problems with our analysis or charts, please feel free to [create an issue](https://github.com/360-info/report-global-education/issues/new)!
