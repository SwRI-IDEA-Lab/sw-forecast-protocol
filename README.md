# sw-forecast-protocol



1. Before any development takes place, set aside two test sets: one operational and one cycle-agnostic.  These sets should not be interacted with until all design decisions have been made and it is time to publish the results of the study.  We suggest setting aside the last two years of available data for an operational test and two months each year for the cycle-agnostic test. Random splitting of samples is not a valid way to construct a test set due to temporal leakage. Removing C flares or otherwise balancing the test data is not an operational test.
2. Use the remainder of the data to train an ensemble of models.  Each ensemble member can be exposed to different random seeds, different training-validation splits, etc.
3. Training ensembles may necessitate the creation of holdout sets (besides training and validation sets) for making decisions involving classification thresholds, architectural choices, hyper-parameters, etc.  Under no circumstances should these decisions be made based on the test sets set aside in step 1.
4. The entire training process should be repeated using a simple baseline model (e.g. logistic regression for classification, random forest for regression). This includes matching training-validation-holdout strategies, as well as training an ensemble of models.  This is critical for understanding the benefit of more sophisticated approaches and mitigates the need for every effort to use identical testing sets.
