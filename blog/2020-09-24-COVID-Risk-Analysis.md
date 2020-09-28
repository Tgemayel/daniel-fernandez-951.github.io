---
layout: post
title: Who's At Risk For COVID?
subtitle: Graphical exploration using CDC Data
cover-img: /assets/img/covid-twists.png
thumbnail-img: /assets/img/covid_wash_hands.png
share-img: /assets/img/covid_wash_hands.png
tags: [data-science, health, risk-assessment, analysis, lambda-ds, build-week-1]
---

# Another Internet-Epidimeologist, GREAT! 🤦‍♂️
Do not fret, there will be no talk about R<sub>t</sub> nor R<sub>0</sub>; instead, we will import CDC data from across the United States and display the data to gain insights. Use this [colab link] to get a detailed view into the process, comments welcomed. This blog is for refrence and a rough gauge of risk relative to the population of the United States.

## About the Data
States and territories of the United States submit patient-level data to the CDC and [HealthData.gov] aggregates and standardizes the data. At the time of use, the most recent update to the database was made first day of September. Data represented within this database is subject to change and has a 14-day delay in reporting. Quality assurance measures are put in place to ensure consistency (onset date in the future, those values are set to null until an update is recieved). In total, this dataset contains in excess of 3 million rows representing individuals.

## Processing Techniques
After import, reported mortality was proirotized by removing any observations whose difinitivness was not included; any 'Missing' or 'Unknown' values in mortality were removed and not used for analysis. Age groups not reported are labeled as 'Unknown'. This data also measures the presence of comorbidities--other significant health issues present at time of reporting--and cleaning was conducted by renaming 'Missing' values as 'Unknown'. In total roughly 48% of the data was removed soley on the presence of a difinitive mortality outcome. Before calulating sums, both mortality and comorbidities were converted to binary data.


# Who's at Greatest Risk from COVID?
Besides anything that isn't human; we all have a risk of contracting and spreading COVID to others. With the holidays fast approaching and as we collectively poke our heads out of our cave-of-isolation, desperate for closer human contact, we all should tread carefully armed with actionalble information to protect those most at risk. Who should we focous on protecting most? In our first look--comparing mortality grouped by age--the majority of survival ocurrs in the younger population. As age increases, the amount of mortality due to COVID also increases. A jump in mortality becomes evident when the age approaches 50 years old. Below is an interactive graph with the capability of toggling mortality:


[colab link]: https://colab.research.google.com/drive/1NeaGzDxOzG9hgAeuovivH-6lSiVAApG-?usp=sharing
[HealthData.gov]: https://healthdata.gov/dataset/covid-19-case-surveillance-public-use-data
<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~danielf44m/1.embed"></iframe>

As the age increases, the change in mortality is drastic. The first biggest jump occurs around the 50-59 age group. At the other extreme, those below 39 years seem to be expiriencing the least mortality due to COVID. Transitioning to observing comorbidities of the patients, we see a flip at roughly 40 years old where the amount of people reporting comorbidities starts to overtake those who report none. This correlates with the jump in mortality for this age range.

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~danielf44m/3.embed"></iframe>


# Conclusion
Based on the information processed, it is safe to conclude that older and sicker populations of people bear the brunt of mortality from COVID. Those who have comorbidities also share the majority of mortality. Protecting those populations is of most importance and should be prioritized to limit their exposure to COVID.
