# Education Brain Drain

These charts and analysis track the flow of students toward a small group of countries using data from the [UNESCO Institute of Statistics](http://data.uis.unesco.org) and [Our World in Data](https://ourworldindata.org/human-development-index).

![Alluvial chart of the average flow of students between economies rated Low, Medium and High on the Human Development Index between 2008 and 2017.](https://github.com/360-info/report-global-education/blob/main/out/student-flows-hdigroups.png?raw=true)

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

### Note on accessibility

The interactive charts in the [`/out`](out) folder use a newer version of the [Observable Plot](https://github.com/observablehq/plot) library than the one currently bundled with Quarto. In particular, Observable Plot 0.4.1 [supports enhanced accessibility features](https://github.com/observablehq/plot/blob/main/CHANGELOG.md#041) for users using screen readers.

If you rebuild the charts using the current Quarto release, these accessibility features will not be present (although the chart will otherwise render). To build using the newer version of Observable Plot:

* [install the development version of Quarto](https://github.com/quarto-dev/quarto-cli#development-version), and
* [modify Quarto's OJS bundle to use Observable Plot 0.4.1 or higher](https://github.com/quarto-dev/quarto-cli/issues/435#issuecomment-1076942406).

These steps aren't required if you're simply serving the version of these charts in the [`/out`](out) folder!

## ❓ Help

If you find any problems with our analysis or charts, please feel free to [create an issue](https://github.com/360-info/report-global-education/issues/new)!
