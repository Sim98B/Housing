**Predicting California House blocks'price.**
![Final results on test data](https://github.com/Sim98B/Housing/blob/main/Cover%20Picture.png?raw=true)
Full dataset is available on Kaggle: https://www.kaggle.com/datasets/kathuman/housing

**Problem Setting**
1. Every instance refers to an house block in california.
2. Features refers to both structural and population characteristics of every block.
3. The block's median price is the **target variable**.


**Analysis**
1. There were 20640 instances and 10 features
2. 207 null-values were detected and dropped, they were just the **1.003%**.
3. **5.21%** of the whole dataset are outlier, instances outside the interquartile range * 1.5 and were removed; we worked with 19369 instances
4. Multicollinearity was detected between four features: total rooms, total bedrooms, block population and number of housholders per block. To avoid introducing this multicollinearity 2 new features were created: bedrooms density and household density which didn't strongly correlate with any other feature

**Modeling the problem**
1. The whole dataset was split into train, test and validation, respectively **80%, 10% and 10%**
2. First, several models were trained with default parameters to select the top 3
3. Then hyper parameters of these models were tuned to get the best performance
4. An ensemble was implemented to outperform basic regressor

**Conclusion**
1. Ensmeble seems to be the best model, the one that should be implemented achieving an explained variance on never_seen_data of **80.188%**
2. Ensmeble predictions' residuals don't follow a normal distribution; on higher prices' predictions an understimation is made
3. Despite this this model has a mean error of **42578$**, which as percentage is a mean of **16.228%** error 
