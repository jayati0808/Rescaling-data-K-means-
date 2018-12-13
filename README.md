# Rescaling-data-K-means-
Simple way to rescale your data in dataframe python.

The rescaling should be always done in a particular sequence. it is very very important 

Why the sequence matters?
Log transformation only works with positive data
Normalization forces data to have negative values and log will not work

Sequence
1. Unskew the data - log transformation
2. Standardize to the same average values
3. Scale to the same standard deviation
4. Store as a separate array to be used for clustering

Coding the sequence
Unskew the data with log transformation
Normalize the variables with StandardScaler
Store it separately for clustering
import numpy as np
datamart_log = np.log(datamart_rfm)
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
scaler.fit(datamart_log)
datamart_normalized = scaler.transform(datamart_log)
