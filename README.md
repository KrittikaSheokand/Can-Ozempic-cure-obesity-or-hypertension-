## Can-Ozempic-cure-obesity-or-hypertension?

# Causal Analysis: Estimating the impact of ozempic on the treatment of obesity/hypertension using double lasso regression.

Causal Analysis Setup: Since this is not a randomized experiment, potential endogeneity issues can arise while determining the effect of ozempic on the target population through observational data. Whether a patient is given ozempic or not is not completely random, therefore trying to look at patients who got ozempic and who did not and calculating the average treatment effect as their difference would be misleading. We need to control for confounding factors here, which means there are factors influencing whether a patient was given ozempic or not and that needs to be controlled. For example, a patient might have been given ozempic in hospital but not during a home visit. 

The method used to control for covariates here is double lasso regression. <br> First, treatment variable ~ covariates. <br> Second, outcome variable ~ treatment variable, predicted treatment variable, covariates. Partial lasso is used here - treatment variable and predicted treatment are not penalized as coefficient of the treatment variable needs to be observed to determine the average treatment effect and predicted treatment variable controls for confounding factors.

We aim to measure the effect of part of the treatment variable which is independent of covariates, that would be the treatment effect (impact of ozempic on obesity/hypertension). To accomplish that, we use the predicted treatment variable in the second regression (mentioned above). The predicted treatment variable captures the endogeneity effect and provides an estimate of the treatment effect free of confounding factors.
