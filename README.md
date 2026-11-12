# Median home sale price by city

## What this site is for

Which of the 18 college-town cities has the highest and lowest typical home price? The site is a single page that shows the median sale price for each city, ranked from highest to lowest, with the number of sales counted and a small bar for each. It is for students, parents and anyone comparing housing costs in college towns.

## Live site

https://yuhanorv.github.io/bdi475-website-project/

## Data notes

- **Rows left out:** the 40 sales under $10,000 (including one at $0). Prices that low are not plausible home prices, so every figure on the site leaves them out. The other 35,402 of the 35,442 rows are counted, in 18 cities. The $10,000 rule is stated on the page. The description sheet's own medians use a $1,000 cutoff, so a few differ slightly (for example Ann Arbor is $572,000 here and $571,000 there).
- **Median sale price:** the middle `sale_price` of a city's counted sales, computed in the browser from `data/college_town_home_sales.csv`. When a city has an even number of sales, the median is the average of the two middle prices. Nothing is estimated or typed in by hand.
- **High prices:** 31 sales are over $5,000,000, up to $81,510,000. They are kept, because a median is barely moved by a few very high values.
- **Duplicate addresses:** rows are never removed for sharing a street address. 66 rows share one, mostly separate condo units in State College, and each is a real sale.
- **Small places:** Savoy (247 sales), Carrboro (205), Newberry (152) and Pittsboro (92) have fewer sales than the 14 main college towns, so their medians are less reliable. They are ranked together with the others.
- **Columns not used:** `home_type`, the three date columns, `living_area_sqft` and the lot size are not used, so the problems with those columns do not affect any figure.

## Tools we used

- Claude Code (web), with the Claude Sonnet 5.5 model, wrote the page and this README.
- Plain HTML, CSS and JavaScript, with no libraries. The page reads the CSV file in the browser.
- GitHub, GitHub Pages and GitHub Actions publish the site.

## Citation

College-town home sales dataset, version 1.0 (2026). University of Illinois-Deloitte Foundation Center for Business Emerging Technologies. Data collected March 2026.

## Who did what

_For teams: replace this line with each member's name and what they did. If you worked alone, delete this section._
