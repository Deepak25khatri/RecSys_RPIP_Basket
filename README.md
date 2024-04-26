
# Basket Sensitive Personalized Item Recommendation

## Overview
This Jupyter notebook presents a method for making personalized item recommendations based on the contents of a user's shopping basket. The approach considers the sensitivity of items within the basket to generate tailored recommendations that enhance the shopping experience, aiming to increase customer satisfaction and sales.

## Features
- **Data Processing**: Cleaning and preparing the data for analysis.
- **Model Development**: Building and training a model to predict which items a user might be interested in based on their current basket.
- **Evaluation**: Assessing the effectiveness of the model using various metrics.
- **Visualization**: Visualizing the relationships and patterns among different items in the baskets.

# Bayesian Fusion Model (BFM) with Constraints

This code implements a Bayesian Fusion Model (BFM) with constraints for personalized item ranking and recommendation. The BFM combines user-item associations, item-basket associations, and user-basket associations to predict the relevance of items for a given user and basket. Additionally, it incorporates a constraint based on Pointwise Mutual Information (PMI) to capture item co-occurrence patterns.

## Dataset

The code reads and processes a dataset from a CSV file `'ta_feng_all_months_merged.csv'`. It filters the data, creates mappings for customer and product IDs, and groups transactions into baskets.

## Model

The model comprises the following components:

1. **Singular Value Decomposition (SVD)**: SVD is applied to the user-item interaction matrix to obtain initial user and item factor vectors.

2. **Bayesian Fusion Model (BFM)**: The BFM score is calculated as a weighted combination of user-item, item-basket, basket-basket, and user-basket associations.

3. **Constrained BFM (CBFM)**: The CBFM incorporates a constraint based on the PMI matrix to capture item co-occurrence patterns within the basket.

4. **Parameter Optimization**: The user and item factor vectors are optimized using stochastic gradient descent, with the objective of maximizing the BFM score while minimizing the CBFM constraint.

5. **Item Ranking**: Items are ranked for a given user by combining the BFM score and the CBFM constraint.

6. **Half-Life Utility (HLU)**: The HLU score is calculated for the ranked list of items, providing a measure of recommendation quality.

## Usage

1. Ensure that the required dependencies (`numpy`, `pandas`, `scipy`) are installed.
2. Place the dataset file `'ta_feng_all_months_merged.csv'` in the directory.
3. Run the code to train the model, optimize the parameters, and obtain the ranked list of items for a user.
4. The HLU score for the specified user will be printed at the end.

## Configuration

The following parameters can be adjusted in the code:

- `num_factors`: Number of factors for SVD decomposition.
- `alpha`: Regularization parameter for the CBFM constraint.
- `learning_rate`: Learning rate for parameter optimization.
- `epochs`: Number of epochs for parameter optimization.
- `GAMMA1`, `GAMMA2`, `GAMMA3`, `GAMMA4`: Weights for the BFM score components.
- `beta`: Half-life parameter for HLU calculation.
- `C`: Scaling factor for HLU calculation.

## Note

This code is provided as an example implementation and may require further modifications or optimizations for specific use cases or datasets.
## Contribution    
1. Nisarg Ganatra		(202311018)
2. Deepak Khatri		(202311042)
3. Shubham Shah		(202311049)
4. Vikram Sarvagyam	(202318034)


## License
This project is licensed under the MIT License - see the LICENSE file for details.
