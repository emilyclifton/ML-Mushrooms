# Mushroom Edibility Classification Project
## Project Overview
This machine learning project aims to develop a model for accurately classifying the edibility of mushrooms. Focusing on distinguishing  between mushrooms that are definitely edible, definitely poisonous, or of unknown edibility, the study addresses the challenges posed by the unique dataset from hypothetical samples of 23 species in the Agaricus and Lepiota Family. 
### Motivation:
The increasing interest in mushroom foraging and the potential risks associated with misidentification underscore the importance of accurate edibility classification. This project seeks to contribute valuable insights for mushroom enthusiasts and foragers.
### Dataset:
* Source: [UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/dataset/73/mushroom)
* Characteristics: Descriptions of hypothetical samples from 23 species in the Agaricus and Lepiota Family
## Performance Metrics
### Binary Classification Metircs
This project involves binary classification, focusing on distinguishing between edible and poisonous mushrooms.
1. **Accuracy**: Overall correctness of the model in predicting edibility.
2. **Precision**: Accuracy of positive predictions, measuring the models ability to correctly identify edible mushrooms.
3. **Recall**: Ability of the model to identify all actual edible mushrooms.
4. **F1 score**: Harmonic mean of precision and recall, providing a balanced measure that considers both false positives and false negatives.
5. **AUC-ROC**: Measures the model's ability to distinguish between classes. A higher AUC-ROC indicates better discrimination between edible and poisonous mushrooms.
## Confusion Matrix
A confusion matrix will be employed to evaluate the model's performance in predicting mushroom edibility.
| Confusion Matrix | **Predicted: Edible (Positive)** | **Predicted: Poisonous (Negative)** |
| ---------------- | -------------------------------- | ------------------------------------ |
| **Actual: Edible** | True Positive | False Negative |
| **Actual: Poisonous** | False Positive | True Negative |
### Matrix interpretation:
* **True Positive (TP)**: Accurate prediction of edible mushrooms
* **True Negative (TN)**: Accurate predictions of poisonous mushrooms
* **False Positive (FP)**: Incorrectly predicted as edible when poisonous.
* **False Negative (FN)**: Incorrectly predicted as poisonous when edible.
## Economic Cost of Misclassification
Mushroom poisoning has been identified as a serious public health concern globally, with significant economic implications. This cost breakdown is designed to provide an approximate overview of the economic burden of mushroom poisoning based on the informatiom from [Epidemiology and Economic Burden of an Outbreak of Cyclopeptide-Containing Mushroom Poisoning in the West of Iran](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9337693/).

*These numbers are calculated in the GDP of West Iran in 2019, I will look into adjusting for the US.*

### Direct Costs:

[comment]: These numbers appear to be calculated in the GDP of West Iran where the study was taken.  Would it make sense to adjust for US GDP? (ask in class)

Direct medical costs and non-medical costs contribute to 10% of the total economic impact.
1. **Direct Medical Costs**:

| Category | Average Cost per Patient |
| ------------ | ---------------------------- |
| Hospitalizated (7-14 days) | $744.49 |
| Out-Patient | $53.93 |

2. **Direct Non-Medical Costs**:

| Resident Type | Average Cost per Resident |
| ------------ | ---------------------------- |
| Rural | $71.85 |
| Urban | $19.52 |
### Indirect Costs:
Indirect costs associated with disability and death contribute to 90% of the total economic impact.
1. **Indirect Costs Associated with Disability**:

| Indirect Cost Type | Average Cost per Individual |
| ------------ | ---------------------------- |
| Patient | $85.95 |
| Caregiver | $26.94 |  
2. **Other Indirect Costs**:

| Cost Type | Average Cost |
| ------------ | ---------------------------- |
| Burial | $1757 |

### Total Costs:
| Cost Type | Total Cost |
| ------------ | ---------------------------- |
| Direct Medical | $69281.65 |
| Direct Non-medical | $10727.23 |
| Total Direct | $80008.88 |
| Indirect Cost of Death | $1125829.70 |
| Total Economic Impact | $1259349.26 |

### Price Predictions:
| Confusion Matrix | **Predicted: Edible (Positive)** | **Predicted: Poisonous (Negative)** |
| ---------------- | -------------------------------- | ------------------------------------ |
| **Actual: Edible** | True Positive - $0 (minimal or negligible) | False Negative - $53.93 (outpatient treatment) |
| **Actual: Poisonous** | False Positive - $892.19 (Average cost of hospitalization + 20%) | True Negative - $0-$1757 (zero or total) |

[comment]: I believe false positive and true negative are switched around. (fixed)

**Price Prediction Interpretation**:
* **True Positive (TP)**: The cost of a true positive is minimal, as it accurately predicts that the mushroom is edible. Individuals in this category would not incur significant medical expenses or related costs.
* **True Negative (TN)**: The cost to the individual of a true negative is also minimal, as it accuratelt predicts that the mushroom is poisonous. Individuals in this category avoid the potential health risks associated with consuming a poisonous mushroom. However, the cost to society of a true negative may include burial costs making the range $1757 depending on if the individual ate the known poisonous mushroom.
* **False Negative (TN)**: The cost of a false negative is moderate, as it predicts that an edible mushroom is poisonous. While the individual might initially incur minimal medical expenses die to misclassification, these costs are usually mitigated once they realize the mushroom is edible and medical intervention is not necessary.
* **False Positive (FP)**: The cost of a false positive is higher, as it predicts that a mushroom is edible when it is actually poisonous. This could lead to medical expenses and indirect costs if the individual consumes the misclassified poisonous mushroom and is not treated quickly.

This breakdown emphasizes the individual perspective, considering the potential impact on health and associated costs based on the accuracy or inaccuracy of the model's predictions.
