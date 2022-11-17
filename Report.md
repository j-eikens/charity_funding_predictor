# Alphabet Soup Report

## Overview
The purpose of this project was to develop a tool that predicts which charity funding candidates are most likely to be successful. A neural network model was developed to accomplish this goal. The model demonstrated accuracy of 99.0% and loss of 5.0% when evaluated on the test dataset.

## Results

### Data Preprocessing
* The target variable for this analysis is campaign success (denoted in the dataset as "IS_SUCCESSFUL"). 
* The following features are variable in the model.
    * Affiliation
    * Use Case
    * Organization
    * Status
    * Income Amount
    * Special Considerations
    * Ask Amount
* The following features were removed from the input dataset:
    * Name
    * EIN

### Neural Network Model
* The neural network model was constructed as follows:

Layer | # of Neurons | Activation Function
---|---|---
Input|1|Relu
Output|1|Sigmoid

* These parameters were selected arbitrarily as initial model parameters. Evaluation demonstrated that these initial parameters had suitable performance when evaluated on the test dataset (accuracy = 99.0%, loss = 5.0%). Therefore, no additional optimization was performed and the initial parameters were kept.
* Data preprocessing was likely the greatest contributor to the quick development of a suitable model. One notable step in the data preprocessing was binning of categorical features. Two categorial features, APPLICATION_TYPE and CLASSIFICATION, contained greater than 10 unique values. Binning was performed on both of these columns. To determine suitable bins, histograms of both features were plotted and used to determine which categories had the greatest value counts. In the APPLICATION_TYPE feature, the T3 category contained ~80% of all values, therefore, any row in the dataset with T3 was assigned 1 and all others were assigned 0. The CLASSIFICATION column was treated similarily. Rows where CLASSIFICATION was C1000, C2000, C1200, C2700, C3000, or C2100 accounted for 93% of the total values. These rows were assigned a 1 and all other rows were assigned zero. 

## Summary
The neural network model developed here demonstrated 99.0% accuracy and 5.0% loss when evaluated on the test dataset. A random forest classifier would be an appropriate alternativel model choice. 

