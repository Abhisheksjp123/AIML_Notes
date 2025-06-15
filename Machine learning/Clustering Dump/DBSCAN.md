Consider following clustering problem  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\7@paste_250317_133803_206.jpg)  
  
However, because these clusters are nested, meaning the green cluster wraps around the blue cluster, a relatively standard clustering method like, k-means clustering, might have difficultly identifying these two clusters.  
  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\8@paste_250317_134102_973.jpg)  
  
  
How Can we achive it through DB scan  
  
Clusters are in high density regions, and outliers tend to be in - low density regions.  
Step 1) the first hing we can do is count the number of points close to each point.For example, if we start with this red point, and we draw an orange circle around it, then we see that the orange circle overlaps, at least partially, 8 other points.  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\13@files_250317_135116_281.jpg)  
  
  
NOTE: The radius of the orange circle is user defined, so when using DBSCAN, you may need to fiddle around with this parameter.  
  
Step2 ) Now, in this example, we will define a Core Point to be one that is close to at least 4 other points.  
step3)Now we randomly pick a Core Point and assign it to the first cluster.Next, the Core Points that are close to the first cluster, meaning they overlap the orange circle are all added to the first cluster.Then the Core Points that are close to the growing first cluster join it and extend it to other Core Points that are close by, at this point, we only add the Core Points to the first cluster.  
Ultimately, all of the Core Points that are close to the growing first cluster are added to it and then used to extend it further.  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\52@files_250317_140023_694.jpg)  
  
  
step4) Now we no longer add any more Core Points to the first cluster.we add all of the Non-Core Points that are close to Core Points in the first cluster.However, because this is not a Core Point,we do not use it to extend the first cluster any further.So, unlike Core Points, Non-Core Points can only join a cluster. They can not extend it further.  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\50@paste_250317_135509_086.jpg)  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\56@files_250317_140706_376.jpg)  
  
  
Now we add all of the Non-Core Points that are close Core Points in the first cluster to the first cluster.And now we are done creating the first cluster.  
  
Similarly we keep on creating other clusters, Lastly, because all of Core Points have been assigned to a cluster, we're done making new clusters..  
  
![](file:///C:\Users\abhis\AppData\Local\Packages\SAMSUNGELECTRONICSCoLtd.SamsungNotes_wyx1vj98g3asy\TempState\72@files_250317_141049_895.jpg)