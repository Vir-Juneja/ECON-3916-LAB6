# Sampling for Machine Learning — Train-Test Splits

## Objective

I explored how sampling methods affect machine learning, focusing on train-test splits, data leakage, and how sampling bias can make large datasets less accurate.

## Methodology

- **Titanic Dataset:** I explored the Titanic dataset containing 891 passengers, using survival as the target variable for prediction.
- **Train-Test Splits:** I compared naive random splitting with stratified splitting to see how each method affects the distribution of survival outcomes in the training and test sets.
- **Stratified Sampling:** I checked that stratification preserves approximately the same survival rate in both the training and test sets.
- **Data Leakage:** I identified and fixed data leakage in the `StandardScaler` and `SimpleImputer` steps by fitting preprocessing operations only on the training data before applying them to the test data.
- **Custom Splitting Function:** I wrote a function called `split_by_share()` that splits a dataset based on a specified test share and random seed. I compared its results with the lab's built-in splitting method.
- **Literary Digest Simulation:** I simulated the 1936 Literary Digest polling failure using a population of 10 million voters to study how biased sampling can produce inaccurate predictions.
- **Data Defect Correlation:** I calculated Meng's data defect correlation to measure the relationship between sample inclusion and the outcome being estimated.
- **Repeated Sampling:** I ran 100 replications comparing biased sampling with random sampling to examine how sample design affects estimation accuracy.

## Key Findings

- **Train-Test Splits:** Stratified splitting maintained approximately equal survival rates across the training and test sets, while naive splitting did not guarantee this balance.
- **Data Leakage:** I learned that fitting preprocessing steps on the full dataset allows information from the test set to influence training. Fitting only on training data prevents this leakage and gives a more reliable evaluation.
- **Custom Splitting:** I verified that my `split_by_share()` function produced results consistent with the lab's splitting method.
- **Sampling Bias:** In the Literary Digest simulation, a biased sample of **[YOUR VALUE] responses** produced a less accurate estimate than a random sample of just **50,000 responses**.
- **Data Defect Correlation:** A data defect correlation of **[YOUR VALUE]** resulted in an estimation error of **[YOUR VALUE] percentage points**, showing how even a small relationship between sample selection and the outcome can affect accuracy in a large population.
- **Repeated Simulations:** Across 100 replications, I compared the performance of biased and random samples and observed how sampling methods influenced estimation errors.

## Conclusion

The main lesson I learned from this lab is that **sample design matters more than sample size**. A large dataset can still produce misleading results if the sample is biased.

I also learned why stratified splitting is useful for preserving class distributions and why preventing data leakage is important for evaluating machine learning models accurately. The Literary Digest simulation showed me that collecting more data does not necessarily improve an estimate when the sampling method is flawed.
