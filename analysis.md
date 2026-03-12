# Introduction

One year after the Trump’s “Liberation Day” tariffs, global trade flows
have shifted. Trade data shows which countries gained, which lost – and
who is footing the bill.

*In this repository, you will find the methodology, data and code behind
the stories that came out of this analysis.*

**Read the full story here:** [English](https://p.dw.com/p/xxx) \|
[German](https://p.dw.com/p/xxx)

**Story by:** [Kira
Schacht](https://www.dw.com/en/kira-schacht/person-46893544)

# Overview

We’ll look at US import data provided through [ITC Trade
Map](https://www.trademap.org/) to analyze:

- How overall imports to the US have changed
- Which countries have seen additional imports in various phases of the
  implementation, e.g.: – January to March 2025: Stockpiling in
  anticipation of tariffs – April to July 2025: Import substitution
  during between announcement (April 2) and implementation (August 7)
- Customs duties collected by the US treasury over time, collated by the
  [Penn Wharton Budget
  Model](https://budgetmodel.wharton.upenn.edu/data-interactives/real-time-federal-budget-tracker.md/?_inputs_&budget_category=%22Taxes%22&budget_category_mirror=%22Taxes%22&maintabs=%22Tracker%22&budget_item=%22Customs%20Duties%20and%20Related%20Taxes%22&years=%2210%22&cumulative=%22TRUE%22&daily_freq=%22TRUE%22&inflation_adjust=%22TRUE%22&comparison_value=%22Previous%20Year%22&chart_tooltip_show_all=false)

# Analysis

## Read Data: Monthly US imports

ITC Trade Map provides the monthly import volume to the US by country.

We’ll focus on the years 2022-2024 as a baseline for comparison with
2025, since 2021 imports might still have been skewed by the Covid-19
pandemic.

| Exporters |  value | year | month |
|:----------|-------:|-----:|------:|
| World     | 258.78 | 2022 |     1 |
| World     | 244.28 | 2022 |     2 |
| World     | 308.52 | 2022 |     3 |
| World     | 284.40 | 2022 |     4 |
| World     | 297.24 | 2022 |     5 |
| World     | 297.84 | 2022 |     6 |
| World     | 282.57 | 2022 |     7 |
| World     | 295.63 | 2022 |     8 |
| World     | 286.39 | 2022 |     9 |
| World     | 293.30 | 2022 |    10 |
| World     | 265.37 | 2022 |    11 |
| World     | 261.63 | 2022 |    12 |

data preview, imports to the US in USD bn:

We’ll focus our analysis on the **19** countries that trade the most
with the US (make up at least 1% of US imports between 2022 and 2024):

**Brazil, Canada, China, France, Germany, India, Ireland, Italy, Japan,
Malaysia, Mexico, Netherlands, Singapore, South Korea, Switzerland,
Taiwan, Thailand, United Kingdom, Vietnam**

## Total US import deviations

We’ll compare total monthly US import values for 2025 to the average in
the corresponding months of 2022-2024. The results show that total
import values to the US briefly rose in early 2025, then returned to
normal. We’ll export this result to `trademap_us_imports_deviation.csv`.

| month |   2025 | average | deviation |
|:------|-------:|--------:|----------:|
| Jan   | 325.30 |  260.89 |     64.41 |
| Feb   | 295.42 |  243.99 |     51.43 |
| Mar   | 350.61 |  281.81 |     68.80 |
| Apr   | 283.74 |  273.81 |      9.93 |
| May   | 283.86 |  283.94 |     -0.09 |
| Jun   | 272.74 |  278.71 |     -5.96 |
| Jul   | 300.54 |  280.50 |     20.04 |
| Aug   | 270.49 |  284.87 |    -14.38 |
| Sep   | 283.01 |  283.07 |     -0.06 |
| Oct   | 281.52 |  291.52 |    -10.00 |
| Nov   | 269.36 |  270.03 |     -0.67 |
| Dec   | 289.99 |  269.47 |     20.52 |

Q1 additional imports, in USD bn

## Q1 2025: Import Surges by country

In early 2025, anticipation of tariffs led US importers to stockpile
goods from many trading partners. Focusing on the countries with more
than 1% average import share to the US, we’ll show the magnitude of
additional imports in Q1 2025 compared to the average of Q1 2022-2024
per country.

The result is exported to `trademap_us_exporters_deviation_Q1.csv`

| Exporters   | Q1_2025 | Q1_average | deviation | change_percent |
|:------------|--------:|-----------:|----------:|---------------:|
| Switzerland |   62.48 |      14.88 |     47.60 |           4.20 |
| Ireland     |   59.73 |      19.93 |     39.81 |           3.00 |
| Mexico      |  132.34 |     114.97 |     17.37 |           1.15 |
| Taiwan      |   34.73 |      22.46 |     12.27 |           1.55 |
| Vietnam     |   41.30 |      29.59 |     11.70 |           1.40 |
| India       |   28.65 |      21.90 |      6.74 |           1.31 |
| Canada      |  111.57 |     105.58 |      5.99 |           1.06 |
| Germany     |   42.71 |      38.01 |      4.70 |           1.12 |
| France      |   17.77 |      13.85 |      3.92 |           1.28 |
| Thailand    |   18.18 |      14.65 |      3.52 |           1.24 |

Q1 additional imports, in USD bn

## April-July 2025: Import shifts during tariff pause

Between the announcement of tariffs on April 2 and their implementation
in August, importers tried to shift to lower-tariff countries.

We’ll show the resulting shift in imports on a map, the data of which is
exported in `trademap_us_exporters_deviation_Apr_Jul.csv`

| Exporters   | AJ_2025 | AJ_average | deviation | change_percent |
|:------------|--------:|-----------:|----------:|---------------:|
| Taiwan      |   68.70 |      34.43 |     34.27 |           2.00 |
| Vietnam     |   69.06 |      44.48 |     24.59 |           1.55 |
| World       | 1140.88 |    1116.96 |     23.92 |           1.02 |
| Mexico      |  179.81 |     163.54 |     16.27 |           1.10 |
| Thailand    |   30.50 |      20.91 |      9.59 |           1.46 |
| India       |   39.12 |      31.37 |      7.75 |           1.25 |
| Switzerland |   24.35 |      18.54 |      5.81 |           1.31 |
| Ireland     |   35.36 |      29.98 |      5.38 |           1.18 |
| Malaysia    |   20.66 |      17.23 |      3.43 |           1.20 |
| Indonesia   |   12.90 |      10.34 |      2.56 |           1.25 |
| Chile       |    8.16 |       5.90 |      2.26 |           1.38 |
| Australia   |    7.87 |       5.66 |      2.21 |           1.39 |

April-July change in imports, in USD bn

## Monthly import changes in 2025

For a view of the year 2025 in total, we’ll show the monthly deviation
from the 2022-2024 average for all countries with at least 1% historic
import share.

| month | Taiwan | Vietnam | Mexico | Thailand | India | Switzerland | Ireland | Malaysia | France |
|:------|-------:|--------:|-------:|---------:|------:|------------:|--------:|---------:|-------:|
| Dec   |  16.91 |    8.82 |   5.05 |     5.44 |  1.78 |       -2.52 |   -3.38 |     1.44 |   1.56 |
| Oct   |  13.26 |    6.32 |   5.59 |     3.51 | -0.41 |       -1.24 |   -3.57 |     0.12 |   0.46 |
| Nov   |  11.96 |    6.73 |   4.89 |     4.21 |  0.57 |       -1.17 |   -3.10 |     0.77 |   1.81 |
| Jul   |  10.09 |    7.22 |   5.82 |     3.23 |  2.16 |        6.51 |   -2.69 |     0.90 |   0.61 |
| Jun   |   8.99 |    7.06 |   3.92 |     2.70 |  1.73 |       -0.20 |   -1.04 |     1.04 |  -0.10 |
| Aug   |   8.51 |    5.02 |   3.20 |     2.37 |  1.15 |       -0.71 |   -2.50 |     0.19 |  -0.29 |
| May   |   8.27 |    5.24 |   4.72 |     1.65 |  1.30 |       -1.61 |    6.22 |     0.77 |   0.16 |
| Apr   |   6.93 |    5.07 |   1.81 |     2.01 |  2.57 |        1.11 |    2.90 |     0.71 |   1.36 |
| Sep   |   6.28 |    5.64 |   3.51 |     3.23 |  0.18 |       -0.28 |   11.59 |     0.30 |   0.08 |
| Mar   |   4.65 |    4.93 |   6.34 |     1.94 |  3.81 |       12.24 |   23.48 |     0.89 |   3.00 |
| Feb   |   3.91 |    3.27 |   5.47 |     0.60 |  1.96 |       15.82 |    9.20 |     0.69 |   0.43 |
| Jan   |   3.71 |    3.50 |   5.56 |     0.98 |  0.96 |       19.54 |    7.12 |     0.67 |   0.49 |

Preview: Monthly deviations by country, in USD bn

## Penn Wharton Budget Model: Customs duties collected by US Treasury

`pennwharton_budget_model_taxes.csv` shows weekly amounts of customs
duties collected by the US, processed from the data source for
visualization.
