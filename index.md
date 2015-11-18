---  
title       : Predicting Stature by Foot Length  
subtitle    : with shinyapp
author      : Sergey Cherkasov
job         : 
framework   : revealjs      # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides

--- 

# Predicting Stature
## by Foot Length
#### with shinyapp

<p>created by Sergey Cherkasov</p>
<p>as part of Developing Data Product course </p>

--- .class #id 

# Preamble

This presentation is a second part of Developing Data Products course. The first part is shiny application which can be found [here](https://pestoverde.shinyapps.io/Developing-Data-Products).

Data for this application can be found at the site of [Department of Statistics](http://www.stat.ufl.edu/~winner/data/stature_hand_foot.dat) (University of Florida).

Original files of this presentation can be found on [github.com](https://github.com/PestoVerde/Course_Project_Slidify)

--- 
# Application

The application provides interaction with simple linear model which predict the heigth of a person by size of his/her foot.

To use the application you need to choose the gender of a person with radio button. Then you can use slider to adjust size of a foot. Big green dot shows the prediction.

The app consist interactive part with the plot and documentation part with brief explanations.

Original files can be found on [github.com](https://github.com/PestoVerde/Developing-Data-Products)

--- 
# Data

Data contains <span style="color:red">155</span> observations with <span style="color:red">5</span> variations each. We remove useless numbers of observations.

The original data contains also hand length of the person. If we used it in our model it improved the prediction for about 5%. But we avoid this variance for the sake of <span style="color:red">brilliant simplicity of the application interface</span> and <span style="color:red">reducing the burden of server</span>.

--- 

# Model

More <span style="color:red">R</span> expression that got evaluated and displayed.

```r
fit <- lm(stature ~ ., data)
summary(fit)
```

```
## 
## Call:
## lm(formula = stature ~ ., data = data)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -9.7055 -2.6147  0.1318  1.9285 13.0125 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept) 84.69370    6.14796  13.776  < 2e-16 ***
## genderMale   6.18123    0.96623   6.397 1.85e-09 ***
## foot_length  0.32062    0.02612  12.277  < 2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 3.965 on 152 degrees of freedom
## Multiple R-squared:  0.824,	Adjusted R-squared:  0.8217 
## F-statistic: 355.9 on 2 and 152 DF,  p-value: < 2.2e-16
```

As we can see the model discribes <span style="color:red">82%</span> of variance.
