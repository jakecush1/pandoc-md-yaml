---
dependencyRatios:
  title: "Figure 1: Dependency ratios for community, regional district, and BC, 2021"

  meta:
    source: 
      author: Statistics Canada
      title: "Age (in single years), average age and median age and gender: Canada, provinces and territories, census divisions and census subdivisions"
      year: 2022
      url: https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=9810002201

  data:
    url: /statics/data/cp_demographics_dependencyRatios.csv

  mark: bar

  encoding:
    tooltip:
    - field: Geography
      type: nominal
    - field: Dependent
      type: nominal
    - field: Count 
      type: quantitative
      title: 'Number of Dependents / 100 workers'
    - field: 2021 Total
      type: quantitative
    - field: 2016 Total
      type: quantitative
    
    y:
      field: Geography
      type: nominal
      sort: 
        op: sum
        field: 2021 Total
        order: descending
      title: Region
    
    x:
      field: Count 
      aggregate: sum
      title: Number of Dependents / 100 workers

    color:
      field: Dependent
      type: nominal
---

# Dependency

Many of the supports provided to children and seniors such as personal care, parenting, education, playgrounds, health care, activity programs, and facilities are supported by personal time and tax dollars contributed by those who are in the workforce. As dependency increases with the aging population, communities may be challenged to maintain supports and services that rely on contributions from the workforce.

This indicator compares the percentage of residents who are of working age to those who are not of working age. Both youth (aged 0 to 19 years) and senior (aged 65 years and over) dependencies are presented. The working age population includes all residents aged 20 to 64. The dependency level is calculated by dividing the dependent population by the workforce population to determine the percentage of the population that is 'dependent' on the workforce. Data for this indicator are from the 2016 and 2021 Census of Population.[^1]

## Dependency Ratio

<data-plot class="text-center" :spec=data.dependencyRatios/>

[^1]: Statistics Canada. (2022). *[Census Profile, 2021 Census of Population](https://www12.statcan.gc.ca/census-recensement/2021/dp-pd/prof/index.cfm?Lang=E)*.

<!--
Purpose: Community Profiles Web Development
Date: 2022-11-08
Analyst: Leeza Perehudoff
Version: 1
-->