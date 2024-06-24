# Data Analysis of: *Testing Theories of American Politics: Elites, Interest Groups, and Average Citizens*, 2014, by Gilens, M. and Page, B.

## Status: **Complete**

## Conclusion:
*Testing Theories of American Politics: Elites, Interest Groups, and Average Citizens* contains significant material error such that we recommend it be retracted.

## Summary:
- Multivariate model derived in paper is insufficient to support the conclusions drawn from it. 
- Attempted model replication, even using R script provided by authors, resulted in a contradictory conclusion.
- Insufficient data to properly decouple two of the three correlated variables.
- Figure 1c contains logical[^1], mathematical[^2], and analytical errors[^3].

[^1]: The metric "net interest group alignment" isn't shown to be effective and there's good reason to believe it wouldn't be so.

[^2]: The x-axis cannot be using the formula proposed. The claimed upper limit on the x-axis would imply there are more interest groups than there are humans on earth by an order of magnitude.

[^3]: Extrapolating a logistic function into regions of the x-axis in which there are no data is erroneous at best and misleading at worst.

---
For a more complete critique, please see the pdf provided in the tex section.

---
Additional analysis available in the "Additional Analysis" section of `code/analysis.ipynb`.

Data and supplemental materials available in `data`.

Original paper and a note on R-sq calculations available in `papers`.

Paper and the data also available at [cambridge.org, doi:10.1017/S1537592714001595](https://doi.org/10.1017/S1537592714001595)

Additional R script used to perform a similar analysis used in Alex Branhman's paper, *Replication Data for: When do the Rich Win* ([doi:10.7910/DVN/UZSQTV](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/UZSQTV)), can be found in `additional-author-correspondence`

Many thanks to Dr. Martin Gilens for responding to my request for data and calculation clarification.