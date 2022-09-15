#### fitting-mixed-effect-models-in-R



# random intercept model using standard maximum likelihood parameter
# Fixed effect = No_exposed, colony, Age, Bednet_Status
# Outcome variable = Total_traped
## Random effect = Host
model2<-lmer(Total_traped~1+No_exposed+Colony+Age+Bednet_Status+(1|Host),REML=FALSE,data=data)


## summary(model2)
#### Linear mixed model fit by maximum likelihood . t-tests use Satterthwaite's method ['lmerModLmerTest']
###### Formula: Total_traped ~ 1 + No_exposed + Colony + Age + Bednet_Status + (1 | Host)
###### Data: data
###### AIC BIC logLik deviance df.resid
###### 516.2 532.3 -251.1 502.2 67
###### Scaled residuals:
###### Min 1Q Median 3Q Max
###### -2.28421 -0.75941 -0.02234 0.73173 2.35115
###### Random effects:
###### Groups Name Variance Std.Dev.
###### Host (Intercept) 0.00 0.0
###### Residual 51.84 7.2
###### Number of obs: 74, groups: Host, 2
###### Fixed effects:
###### Estimate Std. Error df t value Pr(>|t|)
###### (Intercept) 13.40209 16.70297 74.00000 0.802 0.425
###### No_exposed 0.11544 0.02319 74.00000 4.979 4.06e-06 ***
###### Colony 4.00162 2.78248 74.00000 1.438 0.155
###### Age 2.64541 4.44513 74.00000 0.595 0.554
###### Bednet_Status -13.62395 1.72720 74.00000 -7.888 2.11e-11 ***
---
###### Signif. codes: 0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1
###### Correlation of Fixed Effects:
###### (Intr) No_xpsd Colony Age
###### No_exposed 0.523
###### Colony 0.753 0.531
Age -0.981 -0.664 -0.799
###### Bednet_Stts -0.289 -0.086 -0.182 0.228
###### optimizer (nloptwrap) convergence code: 0 (OK)
###### boundary (singular) fit: see ?isSingular

## confint(model2)
###### 2.5 % 97.5 %
###### .sig01 0.00000000 3.052839
###### .sigma 6.17941837 8.536655
###### (Intercept) -19.76458792 46.568774
###### No_exposed 0.06939528 0.161477
###### Colony -1.52348752 9.52672

## anova(model2, test="chisq")
## exp(coef(model2))

