## StandardScaler() - standardization
- StandardScaler.fit() - 평균 𝜇과 표준편차 𝜎를 계산
- StandardScaler.transform() - Standardization, z = (𝑥-𝜇)/𝜎
- StamdardScaler.fit_transform() - fit() + standard()


## what is feature engineering? 
- the process of selecting and transforming raw data into useful features that can be used to build machine learning models. The goal of feature engineering is to extract relevant information from the input data and represent it in a way that is suitable for machine learning algorithms to learn from. 

- This can include tasks such as:   
1. Selecting relevant features from the available data   
2. Transforming features to be more informative or easier to work with  
3. Creating new features by combining existing ones  
4. Scaling or normalizing features to ensure that they are on similar scales  
5. Encoding categorical variables into numerical features  

## difference between one-hot encoding and label encoding  

- both of them are converting categorical variables into numerical features, but differ in the way they encode categorical variables. 
- label encoding: assign each unique value with an integer label
It assumes an ordering of values that may not actually exist, and may result in biased models or incorrect predictions 
- one-hot encoding: create a new binary feature for each unique value
The value of each feature would be 1 if the original variable had that value, and 0 otherwise. This encoding ensures that the model treats each categorical value equally, and eliminates the assumption of ordering.