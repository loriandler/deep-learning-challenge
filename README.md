# deep-learning-challenge
Module 21 UM Bootcamp Challenge

## Background
For this challenge, I used Python in google collab to create a tool to help the nonprofit foundation Alpahbet Soup can use to select the applicants for funding with the best chance of success in their ventures.  A CSV containing more than 34,000 organizaitons that have received funding from AlphabetSoup over the years was provided.

## Step 1: Preprocess the Data
Using knowledge of Pandas and scikit-learn's StandardScaler() was used to preprocess the data set.
- The target for the model was the "IS_SUCCESSFUL" column.
- The columns "EIN" and "NAME" were dropped with the remaining feature columns remaining:
  - APPLICATION_TYPE
  - AFFILIATION
  - CLASSIIFICATION
  - USE_CASE
  - ORGANIZATION
  - STATUS
  - INCOME_AMT
  - SPECIAL CONSIDERATIONS
  - ASK_AMT 

## Step 2: Comile, Train, and Evaluate the Model
This <span style = "color: blue">original model</span>, dropped "EIN" and "NAME" columns and determined the unique values in the remaining columns. Binning was used on the CLASSIFICATION value.  The dataframe was converted to numeric with pd.get_dummies.  The preprocessed data was split in the X and y values.  The StandardScaler() was used to fit and transform the model.
- Cutoff value for APPLICATION_TYPE was set to 10
- Cutoff value for CLASSIFICATION was set to 1000
- First hidden layer used 10 units and activation of "relu"
- Second hidden layer used 5 units and activation of "relu"
- Output layer used activation of "sigmoid"
- epochs = 50

<span style = "color: blue">Optimization #1</span>
Dropped "EIN" and "NAME" columns and determined the unique values in the remaining columns. Binning was used on the CLASSIFICATION value.  The dataframe was converted to numeric with pd.get_dummies.  The preprocessed data was split in the X and y values.  The StandardScaler() was used to fit and transform the model.
- Cutoff value for APPLICATION_TYPE was set to 500
- Cutoff value for CLASSIFICATION was set to 700
- First hidden layer used 10 units and activation of "relu"
- Second hidden layer used 5 units and activation of "sigmoid"
- Added a third hidden layer using 3 units and activation of "sigmoid"
- Output layer used activation of "sigmoid"
- epochs = 100

<span style = "color: blue">Optimization #2</span>
Dropped "EIN" and "NAME" columns and determined the unique values in the remaining columns. Binning was used on the CLASSIFICATION value.  The dataframe was converted to numeric with pd.get_dummies.  The preprocessed data was split in the X and y values.  The StandardScaler() was used to fit and transform the model.
- Cutoff value for APPLICATION_TYPE was set to 1000
- Cutoff value for CLASSIFICATION was set to 1500
- First hidden layer used 10 units and activation of "leaky_relu"
- Second hidden layer used 5 units and activation of "leaky_relu"
- Added a third hidden layer using 3 units and activation of "sigmoid"
- Output layer used activation of "sigmoid"
- epochs = 125

<span style = "color: blue">Optimization #3</span>
Dropped "EIN" and "NAME" columns and determined the unique values in the remaining columns. Binning was used on the CLASSIFICATION value.  The dataframe was converted to numeric with pd.get_dummies.  The preprocessed data was split in the X and y values.  The StandardScaler() was used to fit and transform the model.
- Also dropped "SPECIAL_CONSIDERATIONS" and "ASK_AMT" columns
- Cutoff value for APPLICATION_TYPE remained at the original 10
- Cutoff value for CLASSIFICATION remained at the original 1000
- First hidden layer used 20 units and activation of "relu"
- Second hidden layer used 5 units and activation of "sigmoid"
- Added a third hidden layer using 3 units and activation of "sigmoid"
- Output layer used activation of "sigmoid"
- epochs = 100

## Results
After these three attempts at training the neural network, the accuracy goal of 75% was not attained.  The changes made made minimal impact and the model might need more data to make the training more precise.

## Credits
Thank you to Limei Hou, tutor, who assisted in reviewing my code and for assisting with ideas on how to improve the model.  Thank you to Hunter Hollis, instructor, and TA's Randy and Sam for the instruction on this unit.

