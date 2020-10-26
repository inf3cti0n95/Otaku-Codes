---
layout: post
title:  "Types of Error in Models"
date:   2020-10-26 20:00:00 +0530
categories: [Data Science Basics, Bias, Variance, Error]
excerpt: "Introduction to Model Bias and Variance"

---


Total Error = Irreducible Error + Reducible Error

Reducible Error = Bias + Variance

# Bias
Bias are the simplifying assumptions made by a model to make the target function easier to learn.
Generally, linear algorithms have a high bias making them fast to learn and easier to understand but generally less flexible. In turn, they have lower predictive performance on complex problems that fail to meet the simplifying assumptions of the algorithms bias.
Low Bias: Suggests less assumptions about the form of the target function.
High-Bias: Suggests more assumptions about the form of the target function.
Examples of low-bias machine learning algorithms include: Decision Trees, k-Nearest Neighbors and Support Vector Machines.

Examples of high-bias machine learning algorithms include: Linear Regression, Linear Discriminant Analysis and Logistic Regression.

# Variance
Variance occurs when the model performs good on the trained dataset but does not do well on a dataset that it is not trained on, like a test dataset or validation dataset. Variance tells us how scattered are the predicted value from the actual value.
High variance causes overfitting that implies that the algorithm models random noise present in the training data.
Generally, nonlinear machine learning algorithms that have a lot of flexibility have a high variance. For example, decision trees have a high variance, that is even higher if the trees are not pruned before use.
Examples of low-variance machine learning algorithms include: Linear Regression, Linear Discriminant Analysis and Logistic Regression.
Examples of high-variance machine learning algorithms include: Decision Trees, k-Nearest Neighbors and Support Vector Machines.

# Bias-Variance Trade-Off
The goal of any supervised machine learning algorithm is to achieve low bias and low variance. In turn the algorithm should achieve good prediction performance.
You can see a general trend in the examples above:
Linear machine learning algorithms often have a high bias but a low variance.
Nonlinear machine learning algorithms often have a low bias but a high variance.
The parameterization of machine learning algorithms is often a battle to balance out bias and variance.

## References
- https://machinelearningmastery.com/gentle-introduction-to-the-bias-variance-trade-off-in-machine-learning/#:~:text=Bias%20is%20the%20simplifying%20assumptions,the%20bias%20and%20the%20variance.
- https://medium.com/datadriveninvestor/bias-and-variance-in-machine-learning-51fdd38d1f86
- https://towardsdatascience.com/understanding-the-bias-variance-tradeoff-165e6942b229
