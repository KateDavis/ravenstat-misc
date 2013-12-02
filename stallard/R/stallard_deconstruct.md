==Process Stallard Data tables


1
in the attached by Stallard Tables 3-6 -- just need the upper block Date of first exposure and Date of claim In data frames


```r
projyears = seq(2009, 2059, 5)
rdtbl <- function(infile) {
    cnames <- c("date.first.exposure", projyears, "total", "development.factor")
    tbl = read.delim(infile, header = F, sep = " ")
    colnames(tbl) = cnames
    str(tbl)
    print(tbl)
    return(tbl)
}
```



```r
table3 = rdtbl("table3.txt")
```

```
## 'data.frame':	14 obs. of  14 variables:
##  $ date.first.exposure: chr  "1915-1919" "1920-1924" "1925-1929" "1930-1934" ...
##  $ 2009               : int  0 0 5 50 342 2563 2738 3966 3769 3138 ...
##  $ 2014               : int  0 0 0 5 92 1371 1847 2945 3492 3478 ...
##  $ 2019               : int  0 0 0 0 9 357 910 1966 2629 3265 ...
##  $ 2024               : int  0 0 0 0 0 41 212 946 1795 2509 ...
##  $ 2029               : int  0 0 0 0 0 0 15 244 916 1737 ...
##  $ 2034               : int  0 0 0 0 0 0 0 21 222 986 ...
##  $ 2039               : int  0 0 0 0 0 0 0 0 14 232 ...
##  $ 2044               : int  0 0 0 0 0 0 0 0 0 15 ...
##  $ 2049               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ 2054               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ 2059               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ total              : int  0 0 5 55 442 4332 5720 10088 12838 15361 ...
##  $ development.factor : num  NA NA 1 1.1 1.29 1.69 2.09 2.54 3.41 4.89 ...
##    date.first.exposure 2009 2014 2019 2024 2029 2034 2039 2044 2049 2054
## 1            1915-1919    0    0    0    0    0    0    0    0    0    0
## 2            1920-1924    0    0    0    0    0    0    0    0    0    0
## 3            1925-1929    5    0    0    0    0    0    0    0    0    0
## 4            1930-1934   50    5    0    0    0    0    0    0    0    0
## 5            1935-1939  342   92    9    0    0    0    0    0    0    0
## 6            1940-1944 2563 1371  357   41    0    0    0    0    0    0
## 7            1945-1949 2738 1847  910  212   15    0    0    0    0    0
## 8            1950-1954 3966 2945 1966  946  244   21    0    0    0    0
## 9            1955-1959 3769 3492 2629 1795  916  222   14    0    0    0
## 10           1960-1964 3138 3478 3265 2509 1737  986  232   15    0    0
## 11           1965-1969 2647 2847 3057 2798 2097 1468  761  148   10    0
## 12           1970-1974 1452 1700 1780 1857 1760 1331 1027  533  127    8
## 13           1975-1979  671 1133 1199 1286 1220 1153  932  598  307   46
## 14           1980-1984  122  315  480  469  443  417  438  280  203   78
##    2059 total development.factor
## 1     0     0                 NA
## 2     0     0                 NA
## 3     0     5               1.00
## 4     0    55               1.10
## 5     0   442               1.29
## 6     0  4332               1.69
## 7     0  5720               2.09
## 8     0 10088               2.54
## 9     0 12838               3.41
## 10    0 15361               4.89
## 11    0 15831               5.98
## 12    0 11575               7.97
## 13    7  8551              12.75
## 14   19  3265              26.66
```

```r
table4 = rdtbl("table4.txt")
```

```
## 'data.frame':	14 obs. of  14 variables:
##  $ date.first.exposure: chr  "1915-1919" "1920-1924" "1925-1929" "1930-1934" ...
##  $ 2009               : int  0 0 2 22 144 1028 1246 1943 1893 1557 ...
##  $ 2014               : int  0 0 0 2 39 535 736 1322 1720 1744 ...
##  $ 2019               : int  0 0 0 0 3 148 367 774 1184 1597 ...
##  $ 2024               : int  0 0 0 0 0 14 82 376 698 1140 ...
##  $ 2029               : int  0 0 0 0 0 0 5 96 345 698 ...
##  $ 2034               : int  0 0 0 0 0 0 0 7 80 405 ...
##  $ 2039               : int  0 0 0 0 0 0 0 0 5 90 ...
##  $ 2044               : int  0 0 0 0 0 0 0 0 0 5 ...
##  $ 2049               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ 2054               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ 2059               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ total              : int  0 0 2 23 187 1725 2435 4518 5924 7236 ...
##  $ development.factor : num  NA NA 1 1.08 1.3 1.68 1.95 2.33 3.13 4.65 ...
##    date.first.exposure 2009 2014 2019 2024 2029 2034 2039 2044 2049 2054
## 1            1915-1919    0    0    0    0    0    0    0    0    0    0
## 2            1920-1924    0    0    0    0    0    0    0    0    0    0
## 3            1925-1929    2    0    0    0    0    0    0    0    0    0
## 4            1930-1934   22    2    0    0    0    0    0    0    0    0
## 5            1935-1939  144   39    3    0    0    0    0    0    0    0
## 6            1940-1944 1028  535  148   14    0    0    0    0    0    0
## 7            1945-1949 1246  736  367   82    5    0    0    0    0    0
## 8            1950-1954 1943 1322  774  376   96    7    0    0    0    0
## 9            1955-1959 1893 1720 1184  698  345   80    5    0    0    0
## 10           1960-1964 1557 1744 1597 1140  698  405   90    5    0    0
## 11           1965-1969 1366 1383 1491 1328  903  555  266   53    3    0
## 12           1970-1974  769  851  828  877  815  568  387  202   53    3
## 13           1975-1979  359  626  605  622  559  504  402  220  122   11
## 14           1980-1984   58  174  259  224  209  175  212  115   74   23
##    2059 total development.factor
## 1     0     0                 NA
## 2     0     0                 NA
## 3     0     2               1.00
## 4     0    23               1.08
## 5     0   187               1.30
## 6     0  1725               1.68
## 7     0  2435               1.95
## 8     0  4518               2.33
## 9     0  5924               3.13
## 10    0  7236               4.65
## 11    0  7347               5.38
## 12    0  5354               6.96
## 13    1  4032              11.25
## 14    8  1529              26.35
```

```r
table5 = rdtbl("table5.txt")
```

```
## 'data.frame':	14 obs. of  14 variables:
##  $ date.first.exposure: chr  "1915-1919" "1920-1924" "1925-1929" "1930-1934" ...
##  $ 2009               : int  0 0 1 5 44 328 343 498 445 399 ...
##  $ 2014               : int  0 0 0 1 9 188 244 370 420 409 ...
##  $ 2019               : int  0 0 0 0 1 36 114 260 332 407 ...
##  $ 2024               : int  0 0 0 0 0 7 21 111 218 314 ...
##  $ 2029               : int  0 0 0 0 0 0 2 28 110 209 ...
##  $ 2034               : int  0 0 0 0 0 0 0 2 22 118 ...
##  $ 2039               : int  0 0 0 0 0 0 0 0 2 23 ...
##  $ 2044               : int  0 0 0 0 0 0 0 0 0 2 ...
##  $ 2049               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ 2054               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ 2059               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ total              : int  0 0 1 6 54 559 724 1270 1549 1881 ...
##  $ development.factor : num  NA NA 1 1.16 1.24 1.7 2.11 2.55 3.48 4.71 ...
##    date.first.exposure 2009 2014 2019 2024 2029 2034 2039 2044 2049 2054
## 1            1915-1919    0    0    0    0    0    0    0    0    0    0
## 2            1920-1924    0    0    0    0    0    0    0    0    0    0
## 3            1925-1929    1    0    0    0    0    0    0    0    0    0
## 4            1930-1934    5    1    0    0    0    0    0    0    0    0
## 5            1935-1939   44    9    1    0    0    0    0    0    0    0
## 6            1940-1944  328  188   36    7    0    0    0    0    0    0
## 7            1945-1949  343  244  114   21    2    0    0    0    0    0
## 8            1950-1954  498  370  260  111   28    2    0    0    0    0
## 9            1955-1959  445  420  332  218  110   22    2    0    0    0
## 10           1960-1964  399  409  407  314  209  118   23    2    0    0
## 11           1965-1969  366  363  356  336  275  184  107   12    1    0
## 12           1970-1974  215  226  225  203  228  178  136   68    7    1
## 13           1975-1979   91  174  157  155  129  151  110   67   30    5
## 14           1980-1984   11   47   92   67   50   42   57   34   16    8
##    2059 total development.factor
## 1     0     0                 NA
## 2     0     0                 NA
## 3     0     1               1.00
## 4     0     6               1.16
## 5     0    54               1.24
## 6     0   559               1.70
## 7     0   724               2.11
## 8     0  1270               2.55
## 9     0  1549               3.48
## 10    0  1881               4.71
## 11    0  2001               5.47
## 12    0  1487               6.91
## 13    0  1069              11.70
## 14    0   424              38.35
```

```r
table6 = rdtbl("table6.txt")
```

```
## 'data.frame':	14 obs. of  14 variables:
##  $ date.first.exposure: chr  "1915-1919" "1920-1924" "1925-1929" "1930-1934" ...
##  $ 2009               : int  0 0 9 92 710 5693 7509 12697 14505 16556 ...
##  $ 2014               : int  0 0 0 6 138 2259 3425 6605 9052 11242 ...
##  $ 2019               : int  0 0 0 0 10 426 1281 2985 4968 7283 ...
##  $ 2024               : int  0 0 0 0 0 33 220 1047 2447 4224 ...
##  $ 2029               : int  0 0 0 0 0 0 9 198 1000 2070 ...
##  $ 2034               : int  0 0 0 0 0 0 0 15 184 1014 ...
##  $ 2039               : int  0 0 0 0 0 0 0 0 7 166 ...
##  $ 2044               : int  0 0 0 0 0 0 0 0 0 7 ...
##  $ 2049               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ 2054               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ 2059               : int  0 0 0 0 0 0 0 0 0 0 ...
##  $ total              : int  0 0 9 99 858 8411 12445 23548 32163 42562 ...
##  $ development.factor : num  NA NA 1 1.07 1.21 1.48 1.66 1.85 2.22 2.57 ...
##    date.first.exposure  2009  2014 2019 2024 2029 2034 2039 2044 2049 2054
## 1            1915-1919     0     0    0    0    0    0    0    0    0    0
## 2            1920-1924     0     0    0    0    0    0    0    0    0    0
## 3            1925-1929     9     0    0    0    0    0    0    0    0    0
## 4            1930-1934    92     6    0    0    0    0    0    0    0    0
## 5            1935-1939   710   138   10    0    0    0    0    0    0    0
## 6            1940-1944  5693  2259  426   33    0    0    0    0    0    0
## 7            1945-1949  7509  3425 1281  220    9    0    0    0    0    0
## 8            1950-1954 12697  6605 2985 1047  198   15    0    0    0    0
## 9            1955-1959 14505  9052 4968 2447 1000  184    7    0    0    0
## 10           1960-1964 16556 11242 7283 4224 2070 1014  166    7    0    0
## 11           1965-1969 20590 11180 7536 5060 3190 1723  723  111    3    0
## 12           1970-1974 17283  9780 5688 4223 3067 1911 1287  562   77    3
## 13           1975-1979 11077 11070 5900 3618 2323 1856 1239  582  207   27
## 14           1980-1984  1971  3362 4043 2149 1309  970  987  409  211   70
##    2059 total development.factor
## 1     0     0                 NA
## 2     0     0                 NA
## 3     0     9               1.00
## 4     0    99               1.07
## 5     0   858               1.21
## 6     0  8411               1.48
## 7     0 12445               1.66
## 8     0 23548               1.85
## 9     0 32163               2.22
## 10    0 42562               2.57
## 11    0 50116               2.43
## 12    0 43881               2.54
## 13    5 37904               3.42
## 14   16 15497               7.86
```

2
Build a set of data frames in which the dates of claims are by single year, not 5-year groups
Basically, let y = the cumulative number of claims, going across
Then build a splinefun of the cumulative number of claims
Interpolate the spline fun to individual years
Go from cumulative back to indiv year counts by subtraction
(Standard demographic stuff)


```r
sdata <- function(df) {
    tbl <- df[, 1:12]
    for (cc in 3:12) {
        tbl[, cc] = tbl[, cc] + tbl[cc - 1]
    }
    
    tall = melt(tbl)
    tall = tall[order(tall$date.first.exposure), ]
    sdf = data.frame(exposure = tall$date.first.exposure, claims = tall$value, 
        year = projyears[as.numeric(tall$variable)])
    # okay so we have 14 exposure periods of 11 obs each
    projvec = projyears[1]:projyears[11]
    nproj = length(projvec)
    xdf = data.frame(data.first.exposure = character(), year = numeric(), cum.proj = numeric(), 
        inc.proj = numeric())
    for (exp in 1:14) {
        rn = exp * 11
        r1 = rn - 11 + 1
        sps = splinefun(x = projyears, y = sdf$claims[r1:rn])(projvec)
        # print(sps) decumulate
        isps = sps
        isps[2:nproj] = sps[2:nproj] - sps[1:(nproj - 1)]
        # print(isps)
        tdf = (data.frame(data.first.exposure = rep(df$date.first.exposure[exp], 
            nproj), year = projvec, cum.proj = sps, inc.proj = isps))
        g <- ggplot() + geom_line(data = tdf, aes(year, inc.proj)) + geom_bar(data = sdf[r1:rn], 
            aes(year, claims))
        print(g)
        xdf = rbind(xdf, tdf)
    }
    return(xdf)
}
proj3 = sdata(table3)
```

```
## Using date.first.exposure as id variables
```

```
## Error: undefined columns selected
```

```r
proj4 = sdata(table4)
```

```
## Using date.first.exposure as id variables
```

```
## Error: undefined columns selected
```

```r
proj5 = sdata(table5)
```

```
## Using date.first.exposure as id variables
```

```
## Error: undefined columns selected
```

```r
proj6 = sdata(table6)
```

```
## Using date.first.exposure as id variables
```

```
## Error: undefined columns selected
```


3
Then build a function
Given a vector of years of first exposure, injury (4-level injuries here), and current date
Return a data frame
     Variables year of future claim
     Expected number of claims (NOT rounded at this point)
Processing
   Each incoming vector element produces a set of probabilities, going across, based on single year of claim counts from 2 above
   Then add these probabilities across all vector elements
SInce the starting date will be in the middle of a year, you will have to prorate the first year of expected counts accordingly
You might allow for an additional weight vector on input

4
Build an inverter function
Suppose we have a matrix of counts from a trust that is in the same form as the Stallard matrix, but by year of claim
We also have a "from date" and a "to date" for dates of claims
We want to estimate how our trust's mix of claims by "Date of first exposure" compares with the Stallard mix
Simple inverter -- between "from date" and "to date" in each first exposure group, calculate the ratio of our total number of claims divided by the stallard number
Return a frame
        date of first exposure (grouped)
        ratio of us to stallard

5
You can feed these ratios into function 3 as "pseudo counts" to get the runoff curves for out trust's particular mix of first exposures
