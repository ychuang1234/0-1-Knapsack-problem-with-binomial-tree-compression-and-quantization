 <h1 align="left">0/1 Knapsack problem with binomial tree-based compression and quantization </h1>
<h2 align="center"> 
 
  ## Goal
  
Learning models with suitable hypermeters is critical for the performance of models. However, we usually select hyperparameters manually and empirically. In order to sufficiently choose the combination of hypermeters (maybe continous or discrete), which deepens the exploration for the relationship between hyperparameters and overall perforamance, one of the possible way is to utilize the gaussian process model to explore the "dark side" (not well known region, a.k.a high covariance part) in the relationship and sampling some of the combination which benefits our understanding the most.

  
  
  ## Description
I implemented Baysiean optimization algorithm with gaussian model to sample the possible combinations of hyperparamters in KNN model. The dataset was created randomly with 5 cluster with 2D feature (a.k.a number of features is two), which were not disclosed in the real scenario in training process. I randomly sampled 50 combinations of hyperparameters to make the gaussian model efficienly simulate the relationship between hypermeters and overall performance of the KNN model. Through simulation with Baysiean optimization (maximizing the posterior probility), instead of training to get the real data of the model performation, which is time-comsuming.
## Overall result

Markdown 的核心標準沒有表格，不過表格是 GFM 的一部分，而且 *Markdown Here* 支援表格。這是在電子郵件中加入表格的好方法 － 本來是需要從其他應用程式複製貼上的工作。

| Weight distribution                    | Compression rate        | Elapsed time reduction rate with compression (sec/sec)  | Elapsed time reduction rate with compression and quantization (sec/sec)| Performace (deviation rate compared with optimal solution)
|  ------------------------------------- |:-------------:| :-----:| :-----:| :-----:|
| Normal distribution (Center: 40)       | **40.76 %**    | **66.95% (6.42/19.43)** | **93.96% (1.17/19.43)** | **-4.96%(14556/15315)**
| Normal distribution (Center: 75)       | 32.07 %    | 61.28% (6.66/17.20) | 92.67% (1.26/17.20) | -5.34%(11798/12463)
| Uniform distribution                   |  23.50 %    |  54.00% (10.03/21.8) | 91.70% (1.81/21.80) | -2.92%(10972/11302)
| Normal distribution (Center: 100)      | 17.73%     |  55.44% (8.40/18.85) | 91.06% (1.65/18.45) | -4.98%(9057/9532)
| Uniform distribution  (Center: 150)    | 5.20%       |  43.12% (10.91/19.18) | 87.96% (2.31/19.18) | -2.92%(6424/6617)

## Experiment setting and detailed result

這是我們的 Logo（把游標指向 Logo 可以看到標題文字）
<p align="left">
 <img src=https://github.com/ychuang1234/0-1-Knapsack-problem-with-binomial-tree-compression-and-quantization/blob/2b3796104b9c9fe68211f2cecdfa33ffc9f4c052/result1.JPG " width="30%" height="40%">
  <img src=https://github.com/ychuang1234/0-1-Knapsack-problem-with-binomial-tree-compression-and-quantization/blob/2b3796104b9c9fe68211f2cecdfa33ffc9f4c052/result2.JPG " width="30%" height="40%">
  <img src=https://github.com/ychuang1234/0-1-Knapsack-problem-with-binomial-tree-compression-and-quantization/blob/2b3796104b9c9fe68211f2cecdfa33ffc9f4c052/result3.JPG " width="30%" height="40%">
 </p>
<p align="left">
 <img src=https://github.com/ychuang1234/0-1-Knapsack-problem-with-binomial-tree-compression-and-quantization/blob/2b3796104b9c9fe68211f2cecdfa33ffc9f4c052/result4.JPG " width="30%" height="40%">
 <img src=https://github.com/ychuang1234/0-1-Knapsack-problem-with-binomial-tree-compression-and-quantization/blob/2b3796104b9c9fe68211f2cecdfa33ffc9f4c052/result5.JPG " width="30%" height="40%">
 </p>

[logo]: https://raw.githubusercontent.com/adam-p/markdown-here/master/src/common/images/icon48.png "Logo 標題文字 2"
