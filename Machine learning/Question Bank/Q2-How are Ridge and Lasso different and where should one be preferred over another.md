The big difference between Ridge and Lasso Regression is that Ridge Regression can only shrink the slope asymptotically close to 0 while Lasso Regression can shrink the slope all the way to 0.

Because of which lasso Can remove unnecessary Variables & hence considered better, but Ridge Regression works best when most of the variables in your model are useful.

How?

For Liner model example plots of Ridge and lasso will be as follows:![[638851551493364324.png]]

Notice as the lambda increases the the optimal slope decreases. Ridge regression penalizes heavily, because of which the slope can come very close to zero  but not exactly to 0. This can be seen from above graph as well.
Lasso on the other hand penalizes less and gradually, and can force the slope to be 0.

Because of this Lasso Regression can also be used for [[Feature selection]]

#Question
