# Data files in this analysis

## Downloaded files

* [`hdi-owid.csv`](hdi-owid.csv): a data frame from [Our World in Data](https://ourworldindata.org/human-development-index) of countries' rated Human Development Index over time.


## Files derived from `index.qmd`

[This analysis](../index.qmd) tidies [UIS student flow data](http://data.uis.unesco.org) and [OWID/UNDP human development data](https://ourworldindata.org/human-development-index) into several forms:

* [`country-list.csv`](country-list.csv) a single-column list of country names that appear in the data. Used for country selection in the interactives.
* [`country-names.csv`](country-names.csv): a data frame mapping country names and codes to UN data indicator numbers. Includes some manual modifications to country names on our part, as country names do not always align across datasets.
* [`netflows-hdi-groups.csv`](netflows-hdi-groups.csv): groups countries into Low (HDI < 0.7), Medium (HDI 0.7 to 0.85) and High (HDI > 0.85) development groups and lists the number of students moving _to_ and _from_ each group each year from 1998 to 2007. Columns are:
  - `year`
  - `origin_hdi_bin`: the group (Low, Medium or High) of the country that students _left_
  - `dest_hdi_bin`: the group (Low, Medium or High) of the country that students _visited_ to study
  - `students`: the number of students that visited that year.
* [`netflow-ratios.csv`](netflow-ratios.csv): a data frame of each country's Net Flow Ratio (that is, the difference of students arriving and leaving as a percentage of all students in the country) and Human Development Index in a given year.
* [`popular-destinations-by-origin.csv`](popular-destinations-by-origin.csv): a data frame of the 10 most popular countries that students from any given country visit each year. Includes:
  - `year`
  - `origin_country_name`: the name of the country students are leaving from
  - `dest_country_lumped`: the name of the country students are visiting. Countries outside the top 10 are aggregated together as "Other countries"
  - `value_lumped`: the number of students visiting.
  - `cond_all`: encodes notes and qualifications on the UIS data as a string in the form `a b c d`, where:
    * `a` if the estimate is marked as "INCLUDES" or `-` if not;
    * `b` if the estimate is marked as "INCLUDED" or `-` if not;
    * `c` if the estimate is marked as "NAT_EST" or `-` if not;
    * `d` if the estimate is marked as "UIS_EST" or `-` if not;
  - The README in the [UIS data download](https://apimgmtstzgjpfeq2u763lag.blob.core.windows.net/content/MediaLibrary/bdds/OPRI.zip), which is downloaded to `.cache` by `index.qmd`, describes these qualifications in more detail.
* [`popular-origins-by-destination.csv`](popular-origins-by-destination.csv): a data frame of the 10 most common origin countries for any given destination country in a given year. Includes:
  - `year`
  - `dest_country_name`: the name of the country students are visiting.
  - `origin_country_lumped`: the name of the country students are leaving from. Countries outside the top 10 are aggregated together as "Other countries"
  - `value_lumped`: the number of students visiting.
  - `cond_all`: encodes notes and qualifications on the UIS data as a string in the form `a b c d`, as described above.
* [`student-flows-tidy.csv`](student-flows-tidy.csv): a large data frame of the flows of students between all combinations of countries before lumping the smaller estimates. Includes:
  - `origin_continent`: the continent of the country sending students
  - `origin_country_name`: the name of the country sending students
  - `origin_country_code`: the three-letter [ISO 3166 code](https://www.iso.org/iso-3166-country-codes.html) of the sending country
  - `dest_country_code`: the three-letter [ISO 3166 code](https://www.iso.org/iso-3166-country-codes.html) of the receiving country
  - `dest_continent`: the continent of the country receiving students
  - `dest_country_name`: the name of the country receiving students
  - `year`
  - `value`: the number of students
  - `magnitude`, `qualifier`: columns with additional qualifications on estimates. The README in the [UIS data download](https://apimgmtstzgjpfeq2u763lag.blob.core.windows.net/content/MediaLibrary/bdds/OPRI.zip), which is downloaded to `.cache` by `index.qmd`, describes these columns further.
* [`tidy-countrypair-netflows.csv`](tidy-countrypair-netflows.csv): this data frame attempts to calculate the net flow between any two countries (as opposed to <student-flows-tidy.csv> above, which gives each directional flow individually). Unfortunately, most estimates are missing because the flow one way or another is missing that year (either because it wasn't reported at all or because it was folded into another year's estimate).

Additionally, `index.qmd` downloads the UIS data into `data/.cache`, using the cached version if you repeatedly render the analysis.
