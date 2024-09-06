#  Mammogram Investment Analysis Project
####  Submitted for Rice University Datathon 2023
#### 2nd Place Winner - Beginner Challenge
##### Submission Page: [https://devpost.com/software/mammogram-investment-for-a-mammoth-impact](https://devpost.com/software/mammogram-investment-for-a-mammoth-impact)
[![ScreenShot](README%20Images/ytvid.png)](https://youtu.be/KR5FAVb8hns)
<pre>
</pre>
**Problem Description:** 
The FDA has received an international grant to provide mammography equipment and training to currently uncertified medical facilities nationwide. The FDA needs your help to identify characteristics of facilities where the allocation of their funds would make the greatest impact. To accomplish this, you have been provided with two datasets: the FDA Certified Mammograms Facility Dataset (beginner.csv) which provides information on all currently certified mammography facilities in the United States, and a 2019 Census Dataset (sc-est2019-agesex-civ.csv) which contains information regarding the age, sex, and race compositions of state populations in the United States from 2010-2019. <ins>Using these datasets, analyze the characteristics of already certified facilities and state populations to determine gaps in current mammography coverage in order to help the FDA allocate their funds.</ins> You are not required to but may choose to select an additional dataset of your choosing to complete your project.
<pre>
</pre>
**Our Solution:** 
1. The mammogram facilities dataset was messy, so I just counted the number of rows that had a cell containing a state abbreviations to <ins>determine the number of facilities in each state</ins>.
2. Using the census data for population of each sex and age in each state, for each year from 2010-19, I <ins>computed 8,600 linear regressions to predict the size of each population in Jan. 2023</ins>.
3. I <ins>found external [data](https://tinyurl.com/3p8zv28p)</ins> from Cancer Research UK on breast cancer rates based on sex and age.
4. I <ins>computed a cancer risk metric for each state</ins>, which is the product of the cancer rate for a sex, age group (from step 3) and the predicted 2023 state population for that sex, age group (from step 2), all summed for each sex, age group.
5. I finally <ins>determined the "relative overcapacity" of each state</ins> as the ratio between the cancer risk metric and the number of facilities. We ranked states by this metric.
<pre>
</pre>
**Results:**
- We found the most overburdened states (metrics) were South Carolina (4.34M), Washington (4.25M), Maryland (4.24M), California (4.23M), Massachusetts (3.99M).
- The most underburdened state was North Dakota (1.2M).
