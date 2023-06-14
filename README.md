# Palmer Lab Technical Assignment

# Data Exploration
Counting null values in each column and dropping the six columns containing only null values decreased the proportion of nulls in the dataset from 21.1% to 13.6%.

Explanations for null values may lie in exploring differences between cohorts, sex, or behavioral environments.

Males and females contributed similarly to total null values; sex does not seem to be the best avenue to pursue at first glance.

Cohorts 16 and 17 differ from other cohorts in that they each contribute to more than 10% of total null values in the dataset. However, further comparing against the proportion of total animals reveals that cohorts 4 and 16 contribute 1.6 null values per capita, and cohorts 2 and 17 contribute 1.5 null values per capita.

Similarly, room BSB273B contributes to 23.6% of total null values in the dataset, but it also was used to run 23.5% of all animals in the dataset, so it only contributes to 1.0 null values per capita.

The top three rooms by null values per capita ran too few animals to draw meaningful conclusions; excluding these, only room MTF134B had a higher null count per capita than BSB273B. Comparing room number against cohort number reveals that 75% of cohort 16 was run in BSB273B, while 100% of cohort 17 was run in MTF134B. The computers in these rooms may have had issues exporting data from Med Associates software because of how the MPC2XL export template was written, or they may have been using MedState Notation programs that were not written to record all the same variables recorded on other computers.

Condensing the dataset to the most utile columns and re-inspecting null values added some support to exploring cohort and room differences. For the remaining dataset, columns relating to aggressive/defensive behavior counts contributes to approximately 33% of all null values.

An easy first step to exploring this further would be confirming which animals were excluded from the aggressive/defensive behavior count aspect of the project, and why. If the number of animals excluded and the reasons for excluding those animals does not correlate with the spread of null values, there may be another issue at play for the missing data.

# Stats
Because there are so many missing values for traits relating to aggressive/defensive behavior, I decided to only explore self-administration for this assignment.

Because there are no clearly indicated group differences with respect to genotype, treatment, or training context, the only obvious parameters to run group comparisons for behavioral data are sex and age.

Given more time for the assignment I might classify animals into age brackets and run two-way ANOVA for different traits against age and sex. Because the maximum age for what is seemingly the last experiment in the project, pr_03_age, is only 143 days, and because there is no indication from the dataset that this strain of animal is a model of age-related disorders, I decided to focus only on exploring sex differences.

Outliers were defined as those with values further than 1.5x the IQR away from the first or third quartile. Outliers were only removed before grouping by sex. Upon inspecting within groups, it appeared that groups had visibly different spreads.

Independent t-tests for short access rewards, short access total responses, long access rewards, and long access total responses revealed p-values of 6.152e-11, 1.063e-11, 4.534e-11, and 4.744e-12 respectively, entreating the rejection of the null-hypothesis for differences between sex.

These results evoke questions of whether this self-administration paradigm controlled for bodyweight differences between males and females by using a higher concentration of cocaine in saline for males than for females, and regularly updating concentrations based on average group bodyweight. Assuming so, these results are in line with literature documenting differences in acquisition and maintenance of cocaine self-administration in rats.
