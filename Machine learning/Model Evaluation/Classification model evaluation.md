### Binary Classification model:
To compare a binary classification model **Confusion Matrix** is created:
![[Pasted image 20250617151158.png]]

Now why do we create confusion Matrix, a model which is best for an use case can not be that good for other, for example in a medical industry they are okay with false positives but a false negative can be dangerous to some ones life. Similarly in finance and loans industry they are ok with false negative but a false positive can be dangerous. So based on these parameters few KPIs are defined and Datascientist tries to maximize this KPI based on the requirement.

KPIs: Sensitivity, Specificity, Precision and Recall

**1. Sensitivity (Recall/True Positive Rate):**

- Formula: TP / (TP + FN)
- **"Of all actual positives, how many did we correctly identify?"**
- Measures model's ability to find positive cases
- High sensitivity = few false negatives
ex: we can priorities Sensitivity in Cases like finding Covid positive Where identification of every single positive Case is important (even if we identify Some negations as positives in the process)

**2. Specificity (True Negative Rate):**

- Formula: TN / (TN + FP)
- **"Of all actual negatives, how many did we correctly identify?"**
- Measures model's ability to avoid false alarms
- High specificity = few false positives
ex: we can priorities specificity in Cases like loan application where identifying Who are bad candidates for loan is more important then leaving some good candidates

**3. Precision (Positive Predictive Value):**

- Formula: TP / (TP + FP)
- **"Of all positive predictions, how many were actually positive?"**
- Measures prediction quality when model says "positive"
- High precision = few false positives in predictions

**4. Recall = Sensitivity** (same metric, different names)

**Trade-offs:**

- **High Sensitivity** ↔ **Low Specificity** (catch more positives but more false alarms)
- **High Precision** ↔ **Low Recall** (fewer false alarms but miss more positives)

Of a Model with different threshold how to determine which one is better of its several possible confusion matrix?
We can plot several possible confusion matrix with different threshold of a model(in this example we're taking logistic regression but we can create confusion matrix for other classification model as well) through:
[[ROC Curve]]