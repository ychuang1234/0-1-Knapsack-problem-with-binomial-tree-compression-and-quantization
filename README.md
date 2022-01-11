# 0/1 Knapsack problem with binomial tree-based compression and quantization 
 
## Result

Markdown 的核心標準沒有表格，不過表格是 GFM 的一部分，而且 *Markdown Here* 支援表格。這是在電子郵件中加入表格的好方法 － 本來是需要從其他應用程式複製貼上的工作。

冒號可以用來標示欄位的對齊方式。

| Weight distribution                    | Compression rate        | Elapsed time reduction rate with compression  | Elapsed time reduction rate with compression and quantization
|  ------------------------------------- |:-------------:| :-----:| :-----:|
| Normal distribution (Center: 40)       | **40.76 %**    | **66.95% (6.42/19.43)** | **93.96% (1.17/19.43)** |
| Normal distribution (Center: 75)       | 32.07 %    | 61.28% (6.66/17.20) | 92.67% (1.26/17.20) |
| Uniform distribution                   |  23.50 %    |  54.00% (10.03/21.8) | 91.70% (1.81/21.80) |
| Normal distribution (Center: 100)      | 17.73%     |  55.44% (8.40/18.85) | 91.06% (1.65/18.45) |
| Uniform distribution  (Center: 150)    | 5.20%       |  43.12% (10.91/19.18) | 87.96% (2.31/19.18) |
