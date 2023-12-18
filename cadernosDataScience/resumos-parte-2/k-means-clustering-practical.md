## [Clustering](https://islp.readthedocs.io/en/latest/labs/Ch12-unsup-lab.html)

The estimator `sklearn.cluster.KMeans()` performs

$K$-means clustering in `Python`. 

We begin with a simple simulated example in which there truly are two clusters in the data: 
- the first 25 observations have a mean shift relative to the next 25 observations.

```python

np.random.seed(0);
X = np.random.standard_normal((50,2));
X[:25,0] += 3;
X[:25,1] -= 4;

```
We now perform $K$-means clustering with $K$ = 2
```python

kmeans = KMeans(n_clusters=2,
                random_state=2,
                n_init=20).fit(X)

```
We specify `random_state` to make the results reproducible. The cluster assignments of the 50 observations are contained in `kmeans.labels_`.
```python
kmeans.labels_
```

```python
array([0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,< 0, 0, 0,  0, 0, 0, 0, 0, 1, 0, 0, 0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1],dtype=int32)
```

The K-means clustering perfectly separated the observations into two clusters even though we did not supply any group information to `KMeans()`. We can plot the data, with each observation colored according to its cluster assignment.

```python
fig, ax = plt.subplots(1, 1, figsize=(8,8))
ax.scatter(X[:,0], X[:,1], c=kmeans.labels_)
ax.set_title("K-Means Clustering Results with K=2");
```

![[Pasted image 20231217184517.png]]

Here the observations can be easily plotted because they are two-dimensional. If there were more than two variables then we could instead perform PCA and plot the first two principal component score vectors to represent the clusters.

In this example, we knew that there really were two clusters because we generated the data. However, for real data, we do not know the true number of clusters, nor whether they exist in any precise way. We could instead have performed K-means clustering on this example with K=3

```python

kmeans = KMeans(n_clusters=3,
                random_state=3,
                n_init=20).fit(X)
fig, ax = plt.subplots(figsize=(8,8))
ax.scatter(X[:,0], X[:,1], c=kmeans.labels_)
ax.set_title("K-Means Clustering Results with K=3");

```
![[Pasted image 20231217184620.png]]

When , K=3, k-means clustering splits up the two clusters. 
We have used the `n_init` argument to run the k-means with 20 initial cluster assignments (the default is 10). If a value of `n_init` greater than one is used, then k-means clustering will be performed using multiple random assignments in Step 1 of Algorithm 12.2, and the `KMeans()` function will report only the best results. Here we compare using `n_init=1` to `n_init=20`.

```python

kmeans1 = KMeans(n_clusters=3,
                random_state=3,
                n_init=1).fit(X)
kmeans20 = KMeans(n_clusters=3,
                  random_state=3,
                  n_init=20).fit(X);
kmeans1.inertia_, kmeans20.inertia_

```

```python
(76.85131986999251, 75.06261242745386)
```

Note that `kmeans.inertia_` is the total within-cluster sum of squares, which we seek to minimize by performing k-means clustering (12.17).

We _strongly_ recommend always running k-means clustering with a large value of n_init, such as 20 or 50, since otherwise an undesirable local optimum may be obtained.

When performing k-means clustering, in addition to using multiple initial cluster assignments, it is also important to set a random seed using the `random_state` argument to `KMeans()`. This way, the initial cluster assignments in Step 1 can be replicated, and the k-means output will be fully reproducible.

```python

```


```python



```