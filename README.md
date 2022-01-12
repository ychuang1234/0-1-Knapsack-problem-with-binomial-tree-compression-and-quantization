 <h1 align="left">0/1 Knapsack problem with binomial tree-based compression and quantization </h1>
<h2 align="center"> 
 
  ## Goal
 Using **compressed data** and **quantization** techniques to lessen the solving time in 0/1 knapsack problem with **acceptable deviation rate** from optimal solution.  
 
  ## Introduction
  
**Dynamic programming (DP)** is one of efficient way to solve 0/1 knapsack problem (**maximization problem with constraint**). However, when the selected items and contraint become larger, it **increases computation time** and **takes more memory to store the result of subproblem**. In real case, the weights (cost) distribution of items is **not uniform**. Normally, the distribution is skewed toward the lower half of the possible range of the weights. I utilize this characteristics and make some items with small cost to merge into one new item with bigger cost, resulting in smaller number of items being considered.

  
  
  ## Description
First, I create a binomial tree to each bucket of weights (e.g., bucket1: [w:1 - w:9], bucket2: [w:10 - w:19],...). The reason of choosing binomial heap to record the items is because it only takes **O(1) time** for **deleting**, **inserting**, and **merging operation**. Second, traverse the heaps to search if there are possible sub-heaps that could be merged into the bucket with higher range of cost. After compression, I also quantized the cost in the same bucket to trim some variability in weights, accelerating the process in solving problem.
 <p align="center">
 <img src=https://github.com/ychuang1234/0-1-Knapsack-problem-with-binomial-tree-compression-and-quantization/blob/057e6b00961f6a8722ce889eb0f954df7ea93dfe/compression_process.JPG " width="75%" height="75%">
 </p>
 
## Overall result
When the weights distribution is skewed more toward lower part of the possible range of weights, the compression rate become higher and the reduction rate of the elapsed time become higher. And the obtimality of the result is still retained around 95% of the optimal solution.

| Weight distribution                    | Compression rate        | Elapsed time reduction rate with compression (sec/sec)  | Elapsed time reduction rate with compression and quantization (sec/sec)| Performace (deviation rate compared with optimal solution)
|  ------------------------------------- |:-------------:| :-----:| :-----:| :-----:|
| Normal distribution (Center: 40)       | **40.76 %**    | **66.95% (6.42/19.43)** | **93.96% (1.17/19.43)** | **-4.96%(14556/15315)**
| Normal distribution (Center: 75)       | 32.07 %    | 61.28% (6.66/17.20) | 92.67% (1.26/17.20) | -5.34%(11798/12463)
| Uniform distribution                   |  23.50 %    |  54.00% (10.03/21.8) | 91.70% (1.81/21.80) | -2.92%(10972/11302)
| Normal distribution (Center: 100)      | 17.73%     |  55.44% (8.40/18.85) | 91.06% (1.65/18.45) | -4.98%(9057/9532)
| Normal distribution  (Center: 150)    | 5.20%       |  43.12% (10.91/19.18) | 87.96% (2.31/19.18) | -2.92%(6424/6617)

## Experiment settings and detailed results

This is the output from .ipynb file with various experiment settings.
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
