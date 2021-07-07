# Essential-Math-for-ML
Repo for essential mathematics of statistical learning methods.

Goes down to probability theory, numerical analysis, linear algebra, and statistics and explain the connections of those subjects in the methods.  


1. Approximating relationship of data
 	- Ordinary least squared methods for getting the best approximation onto vector space (Vector space, inner product, linear independence, basis expansion (multiple linear regression being same as higher polynomial approximation), QR decomposition, rank, column space, norm, partial derivative, guassian distribution, maximum liklihood estimation, log liklihood) 
	- Non-parametric estimation: LOESS regression
	- Classification: Logistic regression (cross entropy cost function and gradient descent)

2. Optimization
	- Cost function (RMSE& Guassian, MAE & laplacian)
	- Norm (Euclidean, manaholobis)
	- Convex optimization (Hessian, gradient descent)
	- Advanced methods 
		- Newton's method; curvature. Penalizes wiggliness of the surface, therefore finding geodesic path with steepest gradient.   
		- Stochastic gradient desecent and mini-batch technique; random sampling
		- Adam; momentum-based learning noise reduction
		- Coordinate descent
            - Pros: Will always converge. Converge faster than stochastic gradient descent. 
            - Cons: Can stuck in local minima. Optimization happen one variable at a time, parallelization could be challenging with multiple variables. 


2. Validation
	 -Training and testing data for robust prediction 
	 -Cross-validation (using cross validation for ordinary least squares)
	 -Model selection (AIC, AICC, BIC)


4. Dimensionality reduction
	-PCA
	-ZCA
	-LDA
	-PLS-DA
	-Kernel methods

5. Bayesian inference


##### References

- StatQuest with Josh Starmer https://www.youtube.com/channel/UCtYLUTtgS3k1Fg4y5tAhLbw
- Convex Optimization by Ryan Tishirani https://www.youtube.com/playlist?list=PLjbUi5mgii6AGJW3La3BpEXe27n8v3biT
- Natural language processing by Dan Jurafsky https://www.youtube.com/watch?v=oWsMIW-5xUc&list=PLLssT5z_DsK8HbD2sPcUIDfQ7zmBarMYv



