Exercise 1
================

## 2. Loading data

``` r
connections <- read_csv("Connections.csv")
```

    ## Rows: 412 Columns: 6
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr (6): First Name, Last Name, Email Address, Company, Position, Connected On
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

## 3. Get count of contacts by employer

I’m using `dplyr` functions (“verbs”) to do the counts. Also note the
pipe operator `%>%` that passes the data from one step to the next.

``` r
connections %>% 
  count(Company) %>% 
  filter(!is.na(Company)) %>% 
  arrange(-n)
```

    ## # A tibble: 319 × 2
    ##    Company                                                  n
    ##    <chr>                                                <int>
    ##  1 The Johns Hopkins University - Carey Business School    23
    ##  2 McGill University - Desautels Faculty of Management     11
    ##  3 Johns Hopkins University Carey Business School           7
    ##  4 McGill University                                        7
    ##  5 Johns Hopkins University                                 6
    ##  6 MIT Sloan School of Management                           6
    ##  7 INSEAD                                                   4
    ##  8 NYU Stern School of Business                             3
    ##  9 The Johns Hopkins University                             3
    ## 10 Vizient, Inc                                             3
    ## # … with 309 more rows
