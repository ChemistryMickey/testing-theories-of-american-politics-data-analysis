# Data Analysis of: *Testing Theories of American Politics: Elites, Interest Groups, and Average Citizens*, 2014, by Gilens, M. and Page, B.

---
## Status: **Incomplete**
TODO:
- If authors don't respond with DS2 and DS3, continue trying to reverse engineer average citizens' and interest groups' policy pass proportion

**Please don't take this as an accusation of academic fraud. I currently have emails out to the authors asking for missing data and analysis methods. Until they've responded, please consider differences as my mistake.**
---
## TL;DR:
- Paper figures partially replicable despite missing data
- Those figure parts that can't be replicated are, unfortunately, critical to the central argument of economic influence on policy adoption
- Strong policy preference correlation (>= 0.85) among all economic classes. If a large proportion of a group is in favor of a piece of legislation, it's more likely to be adopted which is counter to the argument made in the paper. More data necessary to investigate cases where the average (50th income percentile) disagrees with the elite (90th income percentile); too few data points to make a determination.
- Only category investigated (education, income, ideology, political leanings, age) that doesn't have a strong correlation (>= 0.85) in policy preference is ideology/political leaning.

## Caveats:
- Not all data provided (1/3 datasets referenced provided (about 30% of the total dataset))
- Data analysis methods insufficiently explained in the paper. Inability to replicate figures may be due to missing data or unexpected method of analysis.

---
## Replicating Figure 1 (the only figure)
Note:
- Average Citizen is defined as 50th income percentile (income range unknown, pred50_sw in the dataset); Economic Elite is defined as 90th income percentile (>$146,000 in 2012 adjusted dollars, pred90_sw in the dataset)

Critiques:
- Paper states (pg. 573, paragraph 1) that the policy preferences of the 50th and 90th income percentiles are highly correlated but figure 1 doesn't show that to be the case; some additional decoupling must be performed to create the different figures 1a and 1c
- Paper states (pg. 573, 2 paragraphs above Economic Elites) that the 80% policy adoption preference bracket (grey bar) for average citizens got their policy adopted 43% of the time. That matches this analysis' recalculation but not figure 1a. This is further evidence of a different analysis method used to generate 1a and 1c but the method isn't clearly stated (or ignored/missed during my reading).
- Figure 1b is almost exactly replicated despite missing DS2 and DS3 (~70% of the data) such that it's unclear if more data would influence the differences seen in figures 1a and 1c.
- Very few cases of +-4 net interest groups such that the predicted probability of adoption is very noisy such that no conclusion can be drawn; this is likely a lack of data issue and would hopefully be fixed with the addition of DS2 and DS3. Unfortunately, the "Percent of cases" histogram (grey bars) matches such that DS2 and DS3 either have the exact same distribution or they also weren't used in the generation of figure 1c.
- Sharp spike in Percent of cases (grey columns) for figure 1c replicated by making smaller histogram bins; oddly enough, it looks like the bin size in the original image is 4 except for the singular bin at zero.
- Data oddly smooth in figure 1c except across the 0 boundary where the histogram bin is differently sized. Perhaps non-uniformly sized bins were used because a net number of interest groups in support or opposition is so heavily weighted at zero but with so few data points (as hinted at with the nearly zero "Percent of Cases"), the data appear far too smooth. It may be an additional logistic fit on top of the highly clustered data about [-4, 4]. If so, that's not strictly accurate and should be explicitly mentioned and notated in the figure.

### Comparisons
#### Average Citizens' Preferences
##### Paper
<img src="readme-images/paper/average-citizens-preferences.png" width="800" height="400">

##### Recalculation
<img src="readme-images/generated/average-citizens-preferences.png" width="800" height="400">

##### Comparison
- Percent of cases successfully replicated but predicted probability of adoption isn't. 
- Correction required to replicate figure not outlined in paper or supplemental materials.
- Predicted probability of adoption here shown leads to opposite conclusion as the paper.
- Paper states "the preferences of ordinary citizens tend to be positively correlated with the preferences of economic elites... \[such that they\] are more or less coincidental beneficiaries rather than causes of the victory.". This implies further processing was required to produce the flat line for average citizens' preferences to decouple them from the economic elites or interest groups but nowhere is this stated. An attempt to reverse engineer this analysis is made in the Additional Analysis section of this notebook.

#### Economic Elites' Preferences
##### Paper
<img src="readme-images/paper/economic-elites-preferences.png" width="800" height="400">

##### Recalculation
<img src="readme-images/generated/economic-elites-preferences.png" width="800" height="400">

##### Comparison
- Predicted probability much closer to the paper; it's not perfect but it's pretty close. I could believe the difference is because of the missing 70% of the dataset but it's still confusing why the Percent of cases would match so well but the predicted probability of adoption wouldn't. What are the chances the missing data have the same Percent of cases distribution?
- Percent of cases again replicated.


#### Interest Group Alignments
##### Paper
<img src="readme-images/paper/interest-group-preferences.png" width="800" height="400">

##### Recalculation
<img src="readme-images/generated/interest-group-preferences.png" width="800" height="400">

##### Comparison
- Unable to replicate predicted probability of adoption in figures 1a (average citizen) and 1c (interest groups).
- Interest groups most likely lack data to draw a strong conclusion but average citizen must have additional processing required to replicate paper's figure 1a. This analysis isn't outlined neither in the paper -- mathematically or verbally -- nor is it in the supplemental materials.
- Inability to replicate these figures undermines thesis of paper.


---
Additional analysis available in the "Additional Analysis" section of `code/analysis.ipynb`.

Data and supplemental materials available in `data`.

Original paper and a note on R-sq available in `papers`.