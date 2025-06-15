Decision Tree makes a statement and then makes a decision based on whether or not that statement is True or False.  
When a Decision Tree classifies things into categories it is a classification tree. And when a Decision Tree predicts numeric values it is Called a regression tree.  
![[638856198289464609.png]]  
  
  
let's build a classification tree from Raw data  
![[638856198410528483.png]]  
  
  
The first thing we do is decide is whether Loves Popcorn, Loves Soda, or Age should be the question we ask at the very top of the tree.To make that decision, we'll start by looking at how well Loves Popcorn predicts whether or not someone Loves Cool As Ice.  
Because these three Leaves all contain a mixture of people who do and do not Love Cool As Ice they are called impure.  
to quantify the difference blw who did a better job classifying from loves popcorn and loves Soda , there are Several ways. One of the most popular methods is called Gini Impurity, but there are also fancy sounding methods like Entropy and Information Gain.However, numerically, the methods are all quite similar, so we will focus on Gini Impurity since, not only is ![[638856198516806238.png]]  
it very popular, I think it is the most straightforward  
  
To calculate the Gini Impurity for Loves Popcorn, we start by calculating the Gini Impurity for the individual Leaves  
  
so  
Gini impurity of loves popcorn = 0.405  
similarly Gini impurity of loves Soda = 0.214  
![[638856198645753455.png]]These both were discrete Variable , but how do we Calculate it for Age , which is a Continuous variable ?  
![[638856199041860713.png]]  
The first thing we do is sort the rows by Age, from lowest value to highest value,  
Then we calculate the average Age for all adjacent people.  
Lastly, we calculate the Gini Impurity values for each average age.  
lowest impurity= 0.343 , Hence  
Gini impurity for Age > 15 = 0.343  
![[638856199677509018.png]]  As loves Soda has the lowest gini impurity , it goes on the top of the tree  
  
final tree after following , similar approach on new nodes  
  
  
  
technical detail  
Remember, when we built this tree, only one person in the original dataset made it to first Leaf. That's why it's hard to have confidence that it will do a great job making predictions with future data.And it's possible that we have Overfit the data  
How to deal with this problem?  
![[638856199863828058.png]]  
**  
**pruning** **is basically** **like cutting** **unnecessary** **branches****,** **This Can be done by 2** **methods** **:**  
**1)** **Pre** **pruning** **-** **based** **On** **certain** **Criterion** **We can Stop the growth of tre****e** **like** **:** **min** **values** **req** **in leaf** **node** **,** **min drop in** **gini impurity** **req**  
**2) Post pruning - after in depth trees have been created, pruning the unnecessary nodes based on certain Criterion**  
  
Note: Decision Trees have the downside of often being over fit, Requiring each split to make a large reduction in impurity helps a tree from being over fit. (This is also Core idea of feature selection through Decision tree)  
  
**Decision tree** **regressor**  
when to use regression tree ? Consider we have to predict effectiveness of a drug given its dosage. Now if the relation b/w them is linear we Can easily fit a linear model  
![[638856199983724068.png]]  
  
  
However what if the data looked like this instead :  
![[638856200209226627.png]]  
  
  
In this case, fitting a straight line to the data wil not be very useful. Here one of the methods to do prediction in regression tree![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\75@paste_250319_020007_477_638856180447516383.jpg)  
  
  
Now, let's just try make this regression tree from scratch ( Note, some of the steps are in the image)  
![[638856200493351508.png]]  
Their average Dosage is 3, and that corresponds to this dotted red line.  
we can Create a tree talking that as the starting point  
  
  
  
![[638856200828498269.png]]  
  
from here we Calculate some of squared residuals ( SS )= 27,468.5  
next we Can use average of next 2 points to create the tree and Calculate its residuals , and plot all these residuals on a Plot  
![[638856201206745952.png]]  
  
This makes 14-5 as Our root node, similarly we can create other branches of the tree. Let's say we predict every point (starting with the left branch) perfectly  
![[638856201328941133.png]]When a model fits the training data perfectly, it probably means it is overfit and will not perform well with new data. There are bunch of techniques to handle this, The simplest is to only split observations when there are more than some minimum number. Lets set it to 7.  
In other words, since there are only 6 observations with Dosage < 14.5, we will not split the observations in this node. Instead, this node will become a leaf, .and the output will be the average Drug Effectiveness for the 6 observations with Dosage < 14.5, 4.2%.  
And with this we Can create our entire tree  
![[638856201753617163.png]] 
Now let's talk about how to build a tree to predict Drug Effectiveness using a bunch of predictors. And check the best Candidate and Compare thier SSRs.  
![[638856202035519691.png]]  
pruning a regression tree ( we'll Cover this when question arrives)