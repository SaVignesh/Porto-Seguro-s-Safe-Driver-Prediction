# Porto-Seguro-s-Safe-Driver-Prediction

## Table of Contents
-  [Overview](#overview)
- [Business Problem](#business-problem)
- [Dataset](#dataset)
- [Business Constraints](#business-constraints)
- [Performance Metric](#performance-metric)
- [Modeling](#modeling)


## Overview:

  Porto Seguro is one of Brazil’s largest auto and homeowner insurance companies. They want to predict whether a customer that has bought auto insurance will initiate an auto insurance claim in the next year given some data about the customer.
  
## Business Problem:

<p> When a customer applies for an auto insurance, a premium quote is created using vehicle data like the age of the vehicle, vehicle’s mileage and customer data like driving history, number of times they have claimed auto insurance, etc. If they had claimed auto insurance multiple times, it can be seen as a measure of unsafe driving habits. For these reasons, the premium payable by that customer will increase compared to all other customers. On the other end of spectrum, there will be customers who did not claim auto insurance for multiple years. These customers will be given a discount on their premium as not claiming auto insurance for multiple years can be seen as a measure of safe driving habits.  </p>

<p>Predicting if a customer will initiate an insurance claim in the next year is useful because the insurance provider can charge a higher premium to that particular customer if the probability of that customer claiming insurance is very high. On the other hand, predicting that a customer will not initiate an auto insurance claim in the next year can make the insurance provider charge a lower premium to that customer. This is particularly useful now-a-days as customers can apply for auto insurance online where they get quotes from multiple insurance providers, compare them and will choose the provider who quoted the lowest premium. </p>

## Dataset:
**Source:** https://www.kaggle.com/competitions/porto-seguro-safe-driver-prediction/
	<p> The given dataset consists of multiple binary, categorical and continuous features. We do not know what these features mean as the features are named ambiguously like ‘ps_ind_11_bin’. The feature names include a postfix ‘bin’ to indicate it is a binary feature and postfix ‘cat’ indicates that it is a categorical feature. The features without these designations are either continuous or ordinal features. </p>
  
 <p> Some features will have value ‘-1’ to indicate that it is a feature missing from observations.	</p>
 <p> The ‘target’ column signifies whether a claim was filed (target = 1) or not (target = 0). </p>
 <p>This is a Binary Classification problem where we need to predict the target given input features. </p>

## Business Constraints:
- Reasonable latency requirement because when a customer applies for an insurance online, they must get their quote within a few seconds after providing the required information.
- Interpretability would be more important if this is a real world problem but in this kaggle competition, Porto Seguro wants high number correct predictions and has not given importance to interpretability.

## Performance Metric:
<p> Port Seguro has mentioned that the performance metric to be used for this problem is Normalized Gini Coefficient. For calculating Normalized Gini Coefficient, we first need to calculate Gini coefficient. </p>
<p>The Gini Coefficient ranges from approximately 0 for random guessing, to approximately 0.5 for a perfect score. </p>
<p>The Normalized Gini Coefficient adjusts the score by the theoretical maximum so that the maximum score is 1. </p>

## Modeling:
LightGBM model is used here as it gave the best results compared to other models.
