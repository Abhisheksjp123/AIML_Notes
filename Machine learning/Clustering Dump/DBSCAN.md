Consider following clustering problem  
![[638856196185364988.png]]  
  
However, because these clusters are nested, meaning the green cluster wraps around the blue cluster, a relatively standard clustering method like, k-means clustering, might have difficultly identifying these two clusters.  
![[638856196575675984.png]]
  
How Can we archive it through DB scan  
  
Clusters are in high density regions, and outliers tend to be in - low density regions.  
Step 1) the first hing we can do is count the number of points close to each point.For example, if we start with this red point, and we draw an orange circle around it, then we see that the orange circle overlaps, at least partially, 8 other points.  
![[638856196645979138.png]]  
  
  
NOTE: The radius of the orange circle is user defined, so when using DBSCAN, you may need to fiddle around with this parameter.  
  
Step2 ) Now, in this example, we will define a Core Point to be one that is close to at least 4 other points.  
step3)Now we randomly pick a Core Point and assign it to the first cluster.Next, the Core Points that are close to the first cluster, meaning they overlap the orange circle are all added to the first cluster.Then the Core Points that are close to the growing first cluster join it and extend it to other Core Points that are close by, at this point, we only add the Core Points to the first cluster.  
Ultimately, all of the Core Points that are close to the growing first cluster are added to it and then used to extend it further.  
![[638856196843630193.png]]  
  
  
step4) Now we no longer add any more Core Points to the first cluster.we add all of the Non-Core Points that are close to Core Points in the first cluster.However, because this is not a Core Point,we do not use it to extend the first cluster any further.So, unlike Core Points, Non-Core Points can only join a cluster. They can not extend it further.  
![[638856197004219819.png]]  
![[638856197156412069.png]]  
  
  
Now we add all of the Non-Core Points that are close Core Points in the first cluster to the first cluster. And now we are done creating the first cluster.  
  
Similarly we keep on creating other clusters, Lastly, because all of Core Points have been assigned to a cluster, we're done making new clusters..  
  
![[638856197254742172.png]]