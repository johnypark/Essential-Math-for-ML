

Reference

    After Friedman
    The elements of Statistical Learning (ESL)
    Trevor Hastie - Gradient Boosting Machine Learning, Dec 2, 2014. https://www.youtube.com/watch?v=wPqtzj5VZus

Keywords

    Bootstrap (ss8.4, ESL) - 264p. 

      - Take a random sample of training data, with duplication, and do that for many times. 
      - EX) draw B datasets each of size N with replacement from training data, pair of X and Y. zi=(xi,yi). To each bootstrap datset Z* we fit cubic spline. get 95% pointwise confidence band for each point and plot them. 
      - way of asesing accuracy (uncertainty) of a paramtere estimate or prediciton
      - can used to improve the estimate or prediction itself. 
      - Bootstrap mean is approximate of posterior average - connection between bootstrap, least square, maximum likelihood, bayesian models. "Poor man's" Bayes posterior. 

    Bagging: Bootstrap aggregation.

      - Take a random sample of training data, with duplicate. (with replacement). If we have N training data, take n samples for each bag, for B number of bags. Shakes the data up. Grow thousands of trees. 
      - Can take the variance down. 
      - average the prediction over a collection of bootstrap samples. -> reduce variance!
      - Averaging method; at given terminal node, probability outcome will be associated with any given data point. You average the outcomes. Each tree will give you the probability at this particular point that you want to make the prediction. Average the probabilities. 
      -Effects: Smoothes the decision boundaries. 
      -Downside: if the bagged trees are correlated, it limits the ability to reduce the variance. So the key is to have the trees uncorrelated from each other. 

    Random Forests ss15, ESL, pp 587. Refinement of Bagged trees, a way of decorrelating these trees some more. Additional randomness when growing the tree.

      - Each time you grow the tree; pick random features among full features. Typically sqrt(p), where p: number of features. "Randomness for which variable is used for splitting (Hastie, 2014)." -> decorrelate trees
      - Result in much more reduction in variance when doing the avaraging. 
      - You get leave-one-out prediciton error for free, by getting error rate of samples that where not involved in tree-generation at each bagging stage. 
      - With random forest you cannot overfit. 
      - You make quite busy trees, therefore bias is very small, but high variance, and you reduce the variance by averaing the trees. 

        $ Var\hat f_{rf}(x)= \rho (x) \sigma^{2}(x) $; sampling correlation reduces by the function of number of features selected at each node for tree generation.

    Boosting; another way of averging trees, learn from the previous; Boosting dominats random forest. Chap 10.
        Adaboost (1997) first proposed by Fraud and Shapiro
        Boosting reweight the trees
        Grow trees to fix up the mistakes
        Not growing i.i.d. trees.
        boosting depending on the problem you might grow very shallow trees.
        boosting with stumps. Stumps is a tree with single split.
        Boosting does not use training error to learn: because test error continues to go down after training error hits zero. It must be using something else.
        Boosting does overfit.
        Boosting is building special kind of model: "Stagewise additive modeling." It builds an additive model that each trees are basis functions. (weak learners).
        However not in normal sense, because in general cases in additive model, we optimize parameters jointly with gradient-type of convex optimziation methods.
        In boosting, we optimize parameters in "stagewise fashion". Each time, we parameterize the next tree we are growing, but all the rest of the trees held fixed. IS THIS A HANDICAP?VERY REASONABLE WAY FOR REGULARIZING THE RATE OF WHICH YOU OVERFIT THE DATA. No backfitting.
        Regression problem: repeatedly fitting its residuals.
        Shrinkage is important. Gives you opportunity to get lots and lots of little trees, and prevent you to from talking bold steps.
        Tree size is important parameter in the story.
        Learning ensembles and lasso -Shrink number of trees with lasso. sparse.

# What are the ways to optiminztging hyperparameters (# of variables in random forest; shrinkage, number of trees in boosting)??

# Is there any systematic way to fit them? such as convex optimiziatoin?