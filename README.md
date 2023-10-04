# Community built protocol for the application of AI to Space Weather Forecast

## Motivation

In the understanding that space weather forecasting has clear challenges, and we as a community can benefit from clear guidelines and protocols, this document is meant to act as a community-mantained repository of best practices and protocols that ensure our work is comparable and follows standards that lead to true progress.

## Rules

All contributions should be constructive and discussion is encouraged as github issues.  All parties involved should engage in good faith and always with the advancement of space weather as the number 1 priority.

No form of harassment and/or discrimination is acceptable.

Pull requests are accepted from any party that has engaged in legitimate space weather forecast.  This includes, but it is not limited to:

- Published work on space weather forecast.
- Membership on a space weather forecasting center/group (e.g. NOAA/SWPC).

## Moderation

We are openly looking for mantainers that can evaluate and merge pull requests.  If interested, please let us know.



## Protocol

1. Before any development takes place, set aside two test sets: one operational and one cycle-agnostic.  These sets should not be interacted with until all design decisions have been made and it is time to publish the results of the study.  We suggest setting aside the last two years of available data for an operational test and two months each year for the cycle-agnostic test. Random splitting of samples is not a valid way to construct a test set due to temporal leakage. Removing C flares or otherwise balancing the test data is not an operational test.
2. Use the remainder of the data to train an ensemble of models.  Each ensemble member can be exposed to different random seeds, different training-validation splits, etc.
3. Training ensembles may necessitate the creation of holdout sets (besides training and validation sets) for making decisions involving classification thresholds, architectural choices, hyper-parameters, etc.  Under no circumstances should these decisions be made based on the test sets set aside in step 1.
4. The entire training process should be repeated using a simple baseline model (e.g. logistic regression for classification, random forest for regression). This includes matching training-validation-holdout strategies, as well as training an ensemble of models.  This is critical for understanding the benefit of more sophisticated approaches and mitigates the need for every effort to use identical testing sets.
