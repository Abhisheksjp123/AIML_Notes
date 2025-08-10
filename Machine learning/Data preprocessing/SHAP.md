SHAP (SHapley Additive exPlanations) is a unified framework for explaining machine learning model predictions by quantifying the contribution of each feature to ==individual predictions== (this is important as we can gauge how important is the overall feature in model prediction, but it doesn't say anything about the individual prediction) . It's based on cooperative game theory, specifically Shapley values from economics.

This is important as we can calculate Feature importance of each variable in model prediction but it cannot tell use 
 - ==individual predictions== -  but it doesn't say anything about the individual prediction.
 - for regression problem it tells about the increase and decrease caused by that feature
 - and classification the predicted probability
 
 
## Core Concept

SHAP answers the question: "How much does each feature contribute to moving the prediction away from the baseline (expected) value?" It provides both local explanations (for individual predictions) and global explanations (for overall model behavior).

In this particular example E[f(x)] defines the average bonus of a sample of 1000 employees. and f(x) defines the bonus for one particular employee. Left pane indicates the feature values for that employee, and waterfall tells the contribution of each feature for the resultant deviation of final average bonus of employee as compared to baseline.

![[Pasted image 20250809015008.png]]
We can also combine the values if individual outcomes in  different SHAP plots:
![[Pasted image 20250809015550.png]]