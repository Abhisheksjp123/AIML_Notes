2.) K means clustering
Step 1: Select the number of clusters you want to identify in your data. This is the "K" in "K-means clustering"
In this case, we'll select K=3. That S! to say, we want to identify 3 clusters.
![[638856176436235512.png]]
Step 2: Randomly select 3 distinct data points,
 ![[638856176620294846.png]]

Step 3: Measure the distance between the 1s point and the three initial clusters.
Step 4: Assign the 1* point to the nearest cluster. In this case, the nearest cluster is the blue cluster.
Drop the same for others
 ![[638856176766705732.png]]
Step 5: calculate the mean of each cluster.
![[638856177011936195.png]]
And repeat same steps taking these means as new clusters
Repeat until there is no change in means,  or you reached maximum number of steps
In this case the clusters that were created were
 

We can see k means did terribly here. 
We can assess the quality of the clustering by adding up the variation within each cluster.
Since K-means clustering can't "see" the best clustering, its only option is to keep track of these clusters, and their total variance, take the new centroids as starting point for new clusters and do the whole thing over again, And with this K means converges to best cluster.

Now, How to decide what K to use?
Each time we add a new cluster, the total variation within each cluster is smaller than before. And when there is only one point per cluster, the variation =0.
However, if we plot the reduction in variance per value for k.
 ![[638856177130660709.png]]
This is called an "elbow plot", and you can pick "K" by finding the "elbow" in the plot

![[638856177264877083.png]]