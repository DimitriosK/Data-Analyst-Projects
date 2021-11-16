# Prosper Loan Data 
## by Dimitrios Karslidis


## Dataset

The original Prosper Loan Data consited of approximately 114000 records (loans) and 80 attributes.
After removing the missing data, the resulting data had approximately 76000 records where each record had borrowers'history incluing their propser score. Based on this score the investors make their decisions when they lend their money to the borrowers. The description of the attributes can be found [here](https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit#gid=0)
This data was provided by Udacity


## Summary of Findings
The main goal of this project was to find the attributes that affect the attribute `PropserScore`
After investigation, it was clear that the attributes such as `RevolvingCreditBalance`, `DebtToIncomeRatio`, `StatedMonthlyIncome`, `AvailableBankcardCredit`, `IsBorrowerHomeowner`, `Currentdelinquencies` and `TotalInquiries` were related to `PropserScore` The distributions of the aforementioned variables were very skewed. However, applying a log transformation to the numerical variables, their distributions would become more symmetric.

I found out that the feature `ProsperScore` had a striking relation to variables such as `AvailableBankcardcredit` (increasing trend of medians along the increasing order of scores), `RevolvingCreditBalance` (increasing trend of medians along the increasing order of scores, although I expected a decreasing trend), `DebtToIncomeRatio` (decreasing trend of medians),`BorrowerRate` (decreasing trend), `StatedMonthlyIncome` (increasing trend) `CurrentDelinquencies` and `TotalInquiries`(decreasing trend of medians, was only apparent for the range [1,6]) In general, the disributions of the aforementioned features for low scores were distinguished clearly from the distributions for high scores as it was clearly indicated from the violin plots. The categorical variable `IsBorrowerHomeowner` affected the ditribution of `ProsperScore` especially for the range of scores [5,11].Moreover, the home owners were assigned scores from the range of [5,11] (good scores) more frequently. There were two things that drew my attention. First,  in case of `RevolvingCreditBalance` vs `ProsperScore` we saw an incresing trend of medians along the increasing order of scores, although I expected a decreasing trend. Second, for the case of `DebtToIncomeRatio` vs `ProsperScore`, there was a decreasing trend as I expected with some jump up at score 11 which I was not expecting.

furthermore, outside of the main variables of interest, I wanted to investigate if the attributes were correlated to each other besides the main variables, `ProsperScore`. I found out that `StatedMonthlyIncome` was related to `DebtToIncomeRatio`,`RevolvingCreditBalance` and `AvailablBankcardCredit` In case of `StatedMonthlyIncome` vs `DebtToIncomeRatio`, we could observe almost a hyperbolic relationship between these two variables via a scatterplot. Also, `DebtToIncomeRatio` was related in very steep increasing manner to `BorrowerRate` even for the small range of debt to income ratio values. Also people who had homes were borrowing money at a lower rate than those ones who did not owe a home.


## Key Insights for Presentation

First, I presented the distributions of each variable to indicate how skewed they were. Then, I showcased 
the bivariate exploration between the features and the main attribute `PropserScore` via point plots and violin plots. My main intention  was to understand more the two interesting things I observed in the bivariate exploration. For this purpose, I used two-dimensional histograms and found out that the  variable `IsBorrowerHomeowner` explained the increasing trend of the medians of`RevolvingCreditBalance` vs `Prosperscore` In fact, the borrowers who owned homes were assigned higher scores even for big values of `RevolvingCreditBalance` values than those who did not have any home ownership (to indicate this fact I used the colormap inferno_r where dark colors would correspond to high density of two variables) and this fact explained the increasing trend of the medians of `RevolvingCreditBalance` vs `ProsperScore`. Furthermore, I used again the two dimensional histogram with thesame color map to discover that the variable `IncomeVerifiable` affects to some extent the distribution of `DebtToIncomeRatio` and `ProsperScore`. In fact, the borrowers whose income was verifiable are assigned fairly high scores even if their debt to income ratio is kind of big and this fact explains to some extent the reason we saw a jump up of the median of `DebtToIncomeratio` at score 11 (low risk) afer the observed decreasing trend of the medians of`DebtToIncomeratio` vs `ProsperScore`.
