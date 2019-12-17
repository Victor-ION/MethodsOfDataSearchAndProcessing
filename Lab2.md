# Лабораторна робота № 2. Функції lapply, sapply, split

## Task 1

#### Створить список list1 \<- list(observationA = c(1:5, 7:3), observationB = matrix(1:6, nrow=2)). Для цього списку знайдіть sum за допомогою lapply.

  - Create list:

<!-- end list -->

``` r
list1 <- list(observationA = c(1:5, 7:3), observationB = matrix(1:6, nrow=2))
list1
```

    ## $observationA
    ##  [1] 1 2 3 4 5 7 6 5 4 3
    ## 
    ## $observationB
    ##      [,1] [,2] [,3]
    ## [1,]    1    3    5
    ## [2,]    2    4    6

  - Calculate sum using lapply:

<!-- end list -->

``` r
lapply(list1, sum)
```

    ## $observationA
    ## [1] 40
    ## 
    ## $observationB
    ## [1] 21

## Task 2

#### Для кожного елементу списку list1 знайдіть максимальне та мінімальне значення (range) за допомогою lapply та sapply.

  - Using lapply:

<!-- end list -->

``` r
lapply(list1, range)
```

    ## $observationA
    ## [1] 1 7
    ## 
    ## $observationB
    ## [1] 1 6

  - Using sapply:

<!-- end list -->

``` r
sapply(list1, range)
```

    ##      observationA observationB
    ## [1,]            1            1
    ## [2,]            7            6

## Task 3

#### Для вбудованого набору даних InsectSprays знайти середнє count для кожного spray.

``` r
groups <- split(InsectSprays, InsectSprays$spray)

sapply(groups, function(x) mean(x$count, na.rm = TRUE))
```

    ##         A         B         C         D         E         F 
    ## 14.500000 15.333333  2.083333  4.916667  3.500000 16.666667
