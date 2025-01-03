---
layout: mathjax
math: mathjax
# date:   2025-01-01 10:05:58 +0800
title: Creating Groundtruth Labels
# categories: credit risk
nav_order: 4
---

## Target label creation
Creating target labels for binary prediction may appear straightforward, but the process can be not trivial in reality. For example, in probability of default (PD) modeling, determining the definition of the ground truth label for default, such as the number of days late that constitutes default, requires careful consideration. A very short gap between the payment due date and the default designation may make the label overly sensitive, where borrowers might just forget to pay or be waiting for payday before settling their loan. Conversely, a too-wide gap can result in an imbalanced label. In summary, this process involves balancing trade-offs.

Deciding on the how long the observation window is also not trivial. Target labels are typically determined after borrowers have been on the books for a while. Many financial institutions employ a two-year performance window, meaning that ground truth labels are only confirmed 24 months after the initial snapshot of the features. This approach, while common, might not be suitable for everyone. A significant gap between the time when feature data is captured and when target labels are determined can lead to outdated or irrelevant feature data, undermining the accuracy of the model. 

### Rollrate analysis
Roll rate analysis is a technique used in credit risk management to understand how loans transition between various delinquency stages over time. This method involves defining categories such as 'Current', '1-30 days past due', '31-60 days past due', and further stages up to 'written-off'. By collecting historical payment data, analysts create transition matrices for consecutive periods, each showing the percentage of accounts moving from one delinquency status to another. These matrices reveal patterns of account stability, deterioration, and recovery. For instance, high percentages remaining in the same category ('Current' to 'Current') indicate stable accounts, while shifts towards more severe delinquency suggest increasing credit risk. By analyzing these patterns, financial institutions can identify at what delinquency stage accounts rarely recover, establishing a data-driven definition of 'default'.

Placeholder for exaample

### Vintage analysis
One method to determine the performnce window is to use vintage analysis. Vintage analysis is an analytical technique used in credit risk modeling to assess the performance of loans across different time periods, known as vintages. A vintage in this context refers to a group of loans issued within a specific time frame, often within a particular month. The primary goal of vintage analysis is to evaluate how loans from each vintage perform over their lifetime, allowing financial institutions to determine the optimal performance window for assessing default risks. The analysis focuses on the 'loss curve' which plots the cumulative percentage of defaults or losses against the age of the loan. By examining these curves, analysts can determine how long it typically takes for the performance of a vintage to stabilize. This stabilization point is critical as it indicates when the data becomes predictive and representative of the ultimate performance of the loans.

Placeholder for example

[Previous: Understanding Logistic Regression](./logistic-regression-modelling.md) | [Next: Feature Engineering](./feature-engineering.md)