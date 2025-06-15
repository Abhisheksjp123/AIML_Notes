Decision free care easy to build, use and interpret , but in practice they are not that awesome. They usually have the tendency to overfit the data they are build upon.  
There Comes random forest. which provides vast improvement in accuracy. How? Let's make a RF.  
step 1: Create a bootstrapped dataset  
To Create a bootstrapped dataset that has the same size as original dataset , we just randomly select Samples (Rows) from original dataset. Important detail is we're allowed to pick the same sample more than once.  
Step 2: Create a decision tree using the bootstrapped dataset, but only use a random subset of variables (or columns) at each step.  
Step 3: Now go back to Step 1 and repeat: Make a new bootstrapped dataset and build a tree considering a subset of variables at each step.  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\64@files_250324_130312_623.jpg)  
  
  
Sweet! Now that we've created a random dt forest, how do we use it?  
We'll test RF on a sample data. Now we ran the sample through first DT and get a yes. similarly we do it with all DT and keep the track. And we see which option receives more votes and mark it as the outcome.  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\73@paste_250324_131911_775.jpg)  
  
Terminology Alert!!  
Bootstrapping the data plus using the aggregate to make a decision is called "Bagging"  
  
Now, How to test How good is our RF  
Usually in a bootstrap data more than 1/3 of entries are not present from the Original dataset (these are Called out of Bag data) . we then test these Out of Bag Sample with their conjugate trees And through aggregation check weather our DTs aver able to classify it Correctly. The proportion of out of bag Samples which are incorrectly classified is Called out of bag error. This gives us accuracy of a Rf model.  
  
Also we Can also test out of bag error of RF Created with 2 variables vs 3 variables.  
  
**Random forest for missing** **data** **and sample clustering**  
on training data we fill the missing Values for discrete variable as mode of variable for that outcome, and for Continous date as medicen/ average. This is the initial guess, we Can refine this through RF .  
We do this by first determining which samples are similar to the one with missing data. So let's talk about how to determine similarity.  
Step 1: Build a random forest..  
Step 2: Run allof the data down all of the trees,  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\81@files_250324_133915_254.jpg)  
  
Notice, while running the data through, 1st DT Sample 3,4 ended in Same node that means they are similar.  
We Keep track of these Similar Sample Using proximity matrix. A proximity meetrix has a row for lack semple enda Column for each sample.  
since sample 3 and h ended up in same node aka Similar we put a 1 there.  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\83@files_250324_134411_420.jpg)  
  
Ultimately, we run the data down all the trees and the proximity matrix fills in.  
  
  
  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\88@paste_250324_134533_391.jpg)  
  
Then we divide each proximity value by the total number of trees. In this example, assume we had 10 trees.  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\97@paste_250324_134632_512.jpg)  
  
Now we use the proximity values for sample 4 to make better guesses about the missing data. for Blocked arteries Cak for missing value is as follows :  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\99@files_250324_135056_423.jpg)  
  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\101@20250324_135521.jpg)  
  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\102@files_250324_135812_964.jpg)  
since No has higher weighted frequency we'll fill the mhissing value as No  
for Contineous variable like weight we are proxinities to Calculate weighted average  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\103@files_250324_140151_741.jpg)  
  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\104@files_250324_140236_327.jpg)  
  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\105@paste_250324_140306_032.jpg)  
  
Now that we've revised our guesses a little bit, we do the whole thing over again...  
We build a random forest, run the data through the trees, recalculate the proximities and recalculate the missing values.  
We do this 6 or 7 times until the missing values converge (i.e. no longer change each time we recalculate).  
  
Similarly we can estimate missing values in the testing data ( discussed in statequest)  
Note: we Calculate distance matrix as  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\106@paste_250324_140520_606.jpg)  
  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\107@files_250324_140643_622.jpg)  
  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\108@files_250324_140713_769.jpg)