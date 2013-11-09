==
笔记
==
- 如何用`lm()`产生复相关系数
 `R2=summary(lmfunction)$r.sq`

 `R=sqrt(R2)`

- 如何访问lm中的子集

```
> lm.1<-lm(dat1)
> summary(lm.1)

Call:
lm(formula = dat1)

Residuals:
    Min      1Q  Median      3Q     Max 
-1.7397 -0.5525 -0.1032  1.1636  1.8056 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept) 33.56343    5.46536   6.141  0.00011 ***
x2          -0.19594    0.03044  -6.436 7.48e-05 ***
y            0.43942    0.03761  11.684 3.75e-07 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 1.351 on 10 degrees of freedom
Multiple R-squared:  0.965,	Adjusted R-squared:  0.958 
F-statistic:   138 on 2 and 10 DF,  p-value: 5.232e-08

> summary(lm.1)$r.sq
[1] 0.9650264
> summary(lm.1)$r.asq
NULL
> summary(lm.1)$p
NULL
> str(summary(lm.1))
List of 11
 $ call         : language lm(formula = dat1)
 $ terms        :Classes 'terms', 'formula' length 3 x1 ~ x2 + y
  .. ..- attr(*, "variables")= language list(x1, x2, y)
  .. ..- attr(*, "factors")= int [1:3, 1:2] 0 1 0 0 0 1
  .. .. ..- attr(*, "dimnames")=List of 2
  .. .. .. ..$ : chr [1:3] "x1" "x2" "y"
  .. .. .. ..$ : chr [1:2] "x2" "y"
  .. ..- attr(*, "term.labels")= chr [1:2] "x2" "y"
  .. ..- attr(*, "order")= int [1:2] 1 1
  .. ..- attr(*, "intercept")= int 1
  .. ..- attr(*, "response")= int 1
  .. ..- attr(*, ".Environment")=<environment: 0x3c987d0> 
  .. ..- attr(*, "predvars")= language list(x1, x2, y)
  .. ..- attr(*, "dataClasses")= Named chr [1:3] "numeric" "numeric" "numeric"
  .. .. ..- attr(*, "names")= chr [1:3] "x1" "x2" "y"
 $ residuals    : Named num [1:13] -0.4973 -0.1032 1.367 -0.5525 -0.0977 ...
  ..- attr(*, "names")= chr [1:13] "1" "2" "3" "4" ...
 $ coefficients : num [1:3, 1:4] 33.5634 -0.1959 0.4394 5.4654 0.0304 ...
  ..- attr(*, "dimnames")=List of 2
  .. ..$ : chr [1:3] "(Intercept)" "x2" "y"
  .. ..$ : chr [1:4] "Estimate" "Std. Error" "t value" "Pr(>|t|)"
 $ aliased      : Named logi [1:3] FALSE FALSE FALSE
  ..- attr(*, "names")= chr [1:3] "(Intercept)" "x2" "y"
 $ sigma        : num 1.35
 $ df           : int [1:3] 3 10 3
 $ r.squared    : num 0.965
 $ adj.r.squared: num 0.958
 $ fstatistic   : Named num [1:3] 138 2 10
  ..- attr(*, "names")= chr [1:3] "value" "numdf" "dendf"
 $ cov.unscaled : num [1:3, 1:3] 16.364045 -0.050935 -0.110065 -0.050935 0.000508 ...
  ..- attr(*, "dimnames")=List of 2
  .. ..$ : chr [1:3] "(Intercept)" "x2" "y"
  .. ..$ : chr [1:3] "(Intercept)" "x2" "y"
 - attr(*, "class")= chr "summary.lm"
```
                                             
