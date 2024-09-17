Data Import
================
ak5357
2024-09-17

This document will show how to import data.

## Import the FAS Litters CSV

Import the dataset and clean the names.

``` r
litters_df = read.csv(
  file = "data/FAS_litters.csv",
  na = c("NA", "", ".")
  )
litters_df = janitor::clean_names(litters_df)
```

## Look at the dataset

``` r
litters_df
```

    ##    group   litter_number gd0_weight gd18_weight gd_of_birth pups_born_alive
    ## 1   Con7             #85       19.7        34.7          20               3
    ## 2   Con7       #1/2/95/2       27.0        42.0          19               8
    ## 3   Con7   #5/5/3/83/3-3       26.0        41.4          19               6
    ## 4   Con7     #5/4/2/95/2       28.5        44.1          19               5
    ## 5   Con7     #4/2/95/3-3         NA          NA          20               6
    ## 6   Con7     #2/2/95/3-2         NA          NA          20               6
    ## 7   Con7 #1/5/3/83/3-3/2         NA          NA          20               9
    ## 8   Con8       #3/83/3-3         NA          NA          20               9
    ## 9   Con8         #2/95/3         NA          NA          20               8
    ## 10  Con8     #3/5/2/2/95       28.5          NA          20               8
    ## 11  Con8     #5/4/3/83/3       28.0          NA          19               9
    ## 12  Con8   #1/6/2/2/95-2         NA          NA          20               7
    ## 13  Con8 #3/5/3/83/3-3-2         NA          NA          20               8
    ## 14  Con8       #2/2/95/2         NA          NA          19               5
    ## 15  Con8   #3/6/2/2/95-3         NA          NA          20               7
    ## 16  Mod7             #59       17.0        33.4          19               8
    ## 17  Mod7            #103       21.4        42.1          19               9
    ## 18  Mod7       #1/82/3-2         NA          NA          19               6
    ## 19  Mod7       #3/83/3-2         NA          NA          19               8
    ## 20  Mod7       #2/95/2-2         NA          NA          20               7
    ## 21  Mod7       #3/82/3-2       28.0        45.9          20               5
    ## 22  Mod7       #4/2/95/2       23.5          NA          19               9
    ## 23  Mod7     #5/3/83/5-2       22.6        37.0          19               5
    ## 24  Mod7      #8/110/3-2         NA          NA          20               9
    ## 25  Mod7            #106       21.7        37.8          20               5
    ## 26  Mod7           #94/2       24.4        42.9          19               7
    ## 27  Mod7             #62       19.5        35.9          19               7
    ## 28  Low7           #84/2       24.3        40.8          20               8
    ## 29  Low7            #107       22.6        42.4          20               9
    ## 30  Low7           #85/2       22.2        38.5          20               8
    ## 31  Low7             #98       23.8        43.8          20               9
    ## 32  Low7            #102       22.6        43.3          20              11
    ## 33  Low7            #101       23.8        42.7          20               9
    ## 34  Low7            #111       25.5        44.6          20               3
    ## 35  Low7            #112       23.9        40.5          19               6
    ## 36  Mod8             #97       24.5        42.8          20               8
    ## 37  Mod8           #5/93         NA        41.1          20              11
    ## 38  Mod8         #5/93/2         NA          NA          19               8
    ## 39  Mod8       #7/82-3-2       26.9        43.2          20               7
    ## 40  Mod8      #7/110/3-2       27.5        46.0          19               8
    ## 41  Mod8         #2/95/2       28.5        44.5          20               9
    ## 42  Mod8           #82/4       33.4        52.7          20               8
    ## 43  Low8             #53       21.8        37.2          20               8
    ## 44  Low8             #79       25.4        43.8          19               8
    ## 45  Low8            #100       20.0        39.2          20               8
    ## 46  Low8           #4/84       21.8        35.2          20               4
    ## 47  Low8            #108       25.6        47.5          20               8
    ## 48  Low8             #99       23.5        39.0          20               6
    ## 49  Low8            #110       25.5        42.7          20               7
    ##    pups_dead_birth pups_survive
    ## 1                4            3
    ## 2                0            7
    ## 3                0            5
    ## 4                1            4
    ## 5                0            6
    ## 6                0            4
    ## 7                0            9
    ## 8                1            8
    ## 9                0            8
    ## 10               0            8
    ## 11               0            8
    ## 12               0            6
    ## 13               0            8
    ## 14               0            4
    ## 15               0            7
    ## 16               0            5
    ## 17               1            9
    ## 18               0            6
    ## 19               0            8
    ## 20               0            7
    ## 21               0            5
    ## 22               0            7
    ## 23               0            5
    ## 24               0            9
    ## 25               0            2
    ## 26               1            3
    ## 27               2            4
    ## 28               0            8
    ## 29               0            8
    ## 30               0            6
    ## 31               0            9
    ## 32               0            7
    ## 33               0            9
    ## 34               2            3
    ## 35               1            1
    ## 36               1            8
    ## 37               0            9
    ## 38               0            8
    ## 39               0            7
    ## 40               1            8
    ## 41               0            9
    ## 42               0            6
    ## 43               1            7
    ## 44               0            7
    ## 45               0            7
    ## 46               0            4
    ## 47               0            7
    ## 48               0            5
    ## 49               0            6

``` r
head(litters_df)
```

    ##   group litter_number gd0_weight gd18_weight gd_of_birth pups_born_alive
    ## 1  Con7           #85       19.7        34.7          20               3
    ## 2  Con7     #1/2/95/2       27.0        42.0          19               8
    ## 3  Con7 #5/5/3/83/3-3       26.0        41.4          19               6
    ## 4  Con7   #5/4/2/95/2       28.5        44.1          19               5
    ## 5  Con7   #4/2/95/3-3         NA          NA          20               6
    ## 6  Con7   #2/2/95/3-2         NA          NA          20               6
    ##   pups_dead_birth pups_survive
    ## 1               4            3
    ## 2               0            7
    ## 3               0            5
    ## 4               1            4
    ## 5               0            6
    ## 6               0            4

``` r
tail(litters_df, 10)
```

    ##    group litter_number gd0_weight gd18_weight gd_of_birth pups_born_alive
    ## 40  Mod8    #7/110/3-2       27.5        46.0          19               8
    ## 41  Mod8       #2/95/2       28.5        44.5          20               9
    ## 42  Mod8         #82/4       33.4        52.7          20               8
    ## 43  Low8           #53       21.8        37.2          20               8
    ## 44  Low8           #79       25.4        43.8          19               8
    ## 45  Low8          #100       20.0        39.2          20               8
    ## 46  Low8         #4/84       21.8        35.2          20               4
    ## 47  Low8          #108       25.6        47.5          20               8
    ## 48  Low8           #99       23.5        39.0          20               6
    ## 49  Low8          #110       25.5        42.7          20               7
    ##    pups_dead_birth pups_survive
    ## 40               1            8
    ## 41               0            9
    ## 42               0            6
    ## 43               1            7
    ## 44               0            7
    ## 45               0            7
    ## 46               0            4
    ## 47               0            7
    ## 48               0            5
    ## 49               0            6

``` r
view(litters_df)
```

## Import the FAS Pups CSV

Use relative path, much easier to use and to share with collaborators.

``` r
pups_df = read.csv("data/FAS_pups.csv")
pups_df = janitor::clean_names(pups_df)

head(pups_df)
```

    ##   litter_number sex pd_ears pd_eyes pd_pivot pd_walk
    ## 1           #85   1       4      13        7      11
    ## 2           #85   1       4      13        7      12
    ## 3     #1/2/95/2   1       5      13        7       9
    ## 4     #1/2/95/2   1       5      13        8      10
    ## 5 #5/5/3/83/3-3   1       5      13        8      10
    ## 6 #5/5/3/83/3-3   1       5      14        6       9

## Import MLB 2011 Summary Data

``` r
mlb_df = read_excel("data/mlb11.xlsx", sheet = "mlb11")
```

## Import SAS data

``` r
pulse_df = read_sas("data/public_pulse_data.sas7bdat")
head(pulse_df)
```

    ## # A tibble: 6 × 7
    ##      ID   age Sex   BDIScore_BL BDIScore_01m BDIScore_06m BDIScore_12m
    ##   <dbl> <dbl> <chr>       <dbl>        <dbl>        <dbl>        <dbl>
    ## 1 10003  48.0 male            7            1            2            0
    ## 2 10015  72.5 male            6           NA           NA           NA
    ## 3 10022  58.5 male           14            3            8           NA
    ## 4 10026  72.7 male           20            6           18           16
    ## 5 10035  60.4 male            4            0            1            2
    ## 6 10050  84.7 male            2           10           12            8
