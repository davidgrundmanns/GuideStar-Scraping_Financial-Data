## Description

Scraping script using `R` to extract annual income revenues from <https://www.guidestar.org.il/>. For any entry, the latest available year of financial data is extracted. Targets the `/finance` tab of each Organisation. If no financial data is displayed, i.e. `https://www.guidestar.org.il/organization/_9-digit-id_/finances` does not exist, then no data is extracted. Financial Reports filed as PDFs are not considered.

### Copyright / Terms of Service

Please honor [GuideStar.org.il's Terms of Service](https://www.guidestar.org.il/page/terms). Do not flood the website with massive requests. It is advisable to scrape small sets and not too fast. While the Terms do not appear to explicitly prohibit automated Content retrieval, it does prohibit use of the website in a way that may cause overload, spamming or interference to the Services of any Kind. If in doubt, request permission before scraping the Website.

## Execute

Run `scrape_budgets.R`. Supply a vector `org_nums` of 9-digit association identifiers to locate associations on the association registrar (see line 10). In line 13, make sure to declare your version of Chrome.

## Dependencies

* RSelenium
* wdman
* dplyr
* stringr
* tidyr
* readxl
* chromedriver (Chrome Version 138.0.7204.169)

## Output

`income_table.csv` includes 14 columns, one for each of to the total annual revenue categories on the association registrar, column `ngo_no` to for the 9-digit association identifier and column `budget_sum`, the sum of all revenue categories, so the total annual income.

If `budget_sum == 0` then no Financial data tab is listed for the corresponding association, or no financial data is reported in the Financial data segment.


