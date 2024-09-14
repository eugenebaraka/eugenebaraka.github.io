---
layout: post
type: post
title: "Today I learned #1"
date: 2024-09-03
author: EUGENE BARAKA
published: true
tags:
  - ml
  - til
header-img: 
description: "Introduction to supervised machine learning."
---


<!-- ```table-of-contents
title: 
style: nestedList # TOC style (nestedList|nestedOrderedList|inlineFirstLevel)
minLevel: 0 # Include headings from the specified level
maxLevel: 0 # Include headings up to the specified level
includeLinks: true # Make headings clickable
debugInConsole: false # Print debug info in Obsidian console
``` -->
## Introduction to machine learning

### Supervised ML
- Always have labels associated with features. Assume features are "questions" and the corresponding labels are "solutions", supervised ML is like teaching the model by showing it a combination of questions and answers with the goal to hopefully pick up the pattern and be able to get the "solutions" by itself
- Train the model with features + known labels -> model can make predictions on new features

<p class="callout summary">
The goal of supervised ML is to come up with a function, $g$ that takes in the feature matrix (i.e., a matrix with inputs), $X$, as a parameter and makes predictions as close as possible to the target, $y$
</p>

#### Types of supervised ML problems
- Regression: target variable is a continuous number (car's price)
- Classification: target variable is categorical (email is span or not)
	- Binary
	- Multi-class 
- Ranking: target variable is scores associated with particular items (e.g., used in recommender systems)

### Model selection process
- Split the data into three datasets (training, validation, and test)
	- The test set is very crucial to prevent the [Multiple comparison problem](https://en.wikipedia.org/wiki/Multiple_comparisons_problem)(MCP)
	- MCP occurs when you repeatedly test different models potentially leading to an overestimation (by pure change) of model performance
- Train various models on the training set
- Validate the models and tune hyperparameters on the validation set: this will give you performance for each model
- Select the best model
- Test the selected model on the test set to ensure generalization on unseen data
- Check the score on the validation and test sets are close enough to confirm the performance was not by pure chance/overfitting to the validation set (i.e., there was no multiple comparison problem in the validation process)

<div class="callout note">
What happens if, after using the test set, the performance is significantly worse than on the validation set, indicating overfitting or MCP?
**If performance on the test set is poor, focus on refining your model selection and validation process (e.g., using cross-validation) rather than tweaking the model based on the test results.**
</div>

### Resources
1. [ML Zoomcamp](https://github.com/DataTalksClub/machine-learning-zoomcamp/tree/master/01-intro)