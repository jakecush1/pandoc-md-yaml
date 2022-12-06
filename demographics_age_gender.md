---
populationPyramid:
  title: 
    text: "Figure 1: Population age structure by 5-year cohort and gender, 2021"
    anchor: middle
    offset: 20

  meta:
    source: Statistics Canada
    title: Census Profile, 2021 Census of Population
    year: 2022
    url: https://www12.statcan.gc.ca/census-recensement/2021/dp-pd/prof/index.cfm?Lang=E

  data:
    url: /statics/data/cp_demographics_populationPyramid.csv

  spacing: 0
  hconcat:
    - transform:
        - filter:
            field: Gender
            equal: Men+
      title: Men+
      mark: bar
      encoding:
        tooltip:
        - field: Age Cohort
          type: ordinal
        - field: Percentage
          type: quantitative
          format: '.1%'
        - field: Gender
          type: nominal      
        y:
          field: Age Cohort
          type: ordinal
          axis: null
          sort:
            [
              "100 years and over",
              "95 to 99 years",
              "90 to 94 years",
              "85 to 89 years",
              "80 to 84 years",
              "75 to 79 years",
              "70 to 74 years",
              "65 to 69 years",
              "60 to 64 years",
              "55 to 59 years",
              "50 to 54 years",
              "45 to 49 years",
              "40 to 44 years",
              "35 to 39 years",
              "30 to 34 years",
              "25 to 29 years",
              "20 to 24 years",
              "15 to 19 years",
              "10 to 14 years",
              "5 to 9 years",
              "0 to 4 years",
            ]
        x:
          # aggregate: sum
          field: Percentage
          type: quantitative
          axis:
            title: Population
            format: '%'
          sort: descending
        color:
          field: Gender
          type: nominal
          scale:
            range:
              - "#675193"
              - "#ca8861"
          legend: null

    - width: 35
      view:
        stroke: null
      mark:
        type: text
        align: center
      encoding:
        y:
          field: Age Cohort
          type: ordinal
          axis: null
          sort:
            [
              "100 years and over",
              "95 to 99 years",
              "90 to 94 years",
              "85 to 89 years",
              "80 to 84 years",
              "75 to 79 years",
              "70 to 74 years",
              "65 to 69 years",
              "60 to 64 years",
              "55 to 59 years",
              "50 to 54 years",
              "45 to 49 years",
              "40 to 44 years",
              "35 to 39 years",
              "30 to 34 years",
              "25 to 29 years",
              "20 to 24 years",
              "15 to 19 years",
              "10 to 14 years",
              "5 to 9 years",
              "0 to 4 years",
            ]
        text:
          field: Age Cohort
          type: ordinal

    - transform:
        - filter:
            field: Gender
            equal: Women+
      title: Women+
      mark: bar
      encoding:
        tooltip:
        - field: Age Cohort
          type: ordinal
        - field: Percentage
          type: quantitative
          format: '.1%'
        - field: Gender
          type: nominal  
        y:
          field: Age Cohort
          type: ordinal
          title: null
          axis: null
          sort:
            [
              "100 years and over",
              "95 to 99 years",
              "90 to 94 years",
              "85 to 89 years",
              "80 to 84 years",
              "75 to 79 years",
              "70 to 74 years",
              "65 to 69 years",
              "60 to 64 years",
              "55 to 59 years",
              "50 to 54 years",
              "45 to 49 years",
              "40 to 44 years",
              "35 to 39 years",
              "30 to 34 years",
              "25 to 29 years",
              "20 to 24 years",
              "15 to 19 years",
              "10 to 14 years",
              "5 to 9 years",
              "0 to 4 years",
            ]
        x:
          field: Percentage
          type: quantitative
          axis:
            title: Population
            format: '%'
        color:
          field: Gender
          type: nominal
          legend: null
  config:
    view:
      stroke: null
    axis:
      grid: false

labourForcePyramid: #sorry in advance - I modified the code above for this graph
  title: 
    text: "Figure 2: Labour force population by age range, 2021"
    anchor: middle
    offset: 20

  meta:
    source: Statistics Canada
    title: Census Profile, 2021 Census of Population
    year: 2022
    url: https://www12.statcan.gc.ca/census-recensement/2021/dp-pd/prof/index.cfm?Lang=E

  data:
    url: /statics/data/cp_demographics_labourForcePyramid.csv

  spacing: 0
  hconcat:
    - transform:
        - filter:
            field: Gender
            equal: Men+
      title: Men+
      mark: bar
      encoding:
        tooltip:
        - field: Cohort
          type: ordinal
        - field: Percentage
          type: quantitative
          format: '.1%'
        - field: Gender
          type: nominal      
        y:
          field: Cohort
          type: ordinal
          axis: null
          sort:
            [
              "Seniors (65+)",
              "Primary Labour Force (25-64)",
              "Emerging Labour Force (15-24)",
              "Children (0-14)",
            ]
        x:
          # aggregate: sum
          field: Percentage
          type: quantitative
          axis:
            # title: Population
            format: '%'
          sort: descending
        color:
          field: Gender
          type: nominal
          scale:
            range:
              - "#675193"
              - "#ca8861"
          legend: null

    - width: 35
      view:
        stroke: null
      mark:
        type: text
        align: center
      encoding:
        y:
          field: Cohort
          type: ordinal
          axis: null
          sort:
            [
              "Seniors (65+)",
              "Primary Labour Force (25-64)",
              "Emerging Labour Force (15-24)",
              "Children (0-14)",
            ]
        text:
          field: Cohort
          type: ordinal

    - transform:
        - filter:
            field: Gender
            equal: Women+
      title: Women+
      mark: bar
      encoding:
        tooltip:
        - field: Cohort
          type: ordinal
        - field: Percentage
          type: quantitative
          format: '.1%'
        - field: Gender
          type: nominal  
        y:
          field: Cohort
          type: ordinal
          title: null
          axis: null
          sort:
            [
              "Seniors (65+)",
              "Primary Labour Force (25-64)",
              "Emerging Labour Force (15-24)",
              "Children (0-14)",
            ]
        x:
          field: Percentage
          type: quantitative
          axis:
            #title: Population
            format: '%'
        color:
          field: Gender
          type: nominal
          legend: null
  config:
    view:
      stroke: null
    axis:
      grid: false

genderRatios:
  title: 
    text:
      - "Figure 2: Gender ratios (Men+:Women+) by community, regional district, and BC, 2021"
    anchor: middle
    offset: 20

  meta:
    source: Statistics Canada
    title: "Age (in single years), average age and median age and gender: Canada, provinces and territories, census divisions and census subdivisions"
    year: 2022
    url: https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=9810002201

  data:
    url: /statics/data/cp_demographics_genderRatios.csv
  
  mark: 
    type: bar
    clip: true
      
  encoding:
    tooltip:
    - field: Geography
      type: ordinal
      title: Geography
    - field: Ratio
      type: quantitative
      format: '.2f'

    y:
      field: Geography
      type: ordinal
      sort: -x
    
    x:
      field: Ratio
      type: quantitative
      scale:
        domain:
        - 0.60
        - 1.20
      axis:
        title: Gender ratio (Men+:Women+)
---

# Age & Gender

Demographic shifts have important consequences for our communities. Different age groups and household structures have different needs in terms of housing, services (e.g., health, education), employment, and consumption. Age and gender are two of the demographic characteristics collected by Statistics Canada during the Census of Population.[^1]

The 2021 Census of Population marked the first time separate questions were asked about the respondent's sex at birth and their gender.[^2] Gender refers to a person's personal and social characteristics, which can include their gender identity (internal and individual feelings) and gender expression (the way their gender is presented, regardless of gender identity). A person's gender may change over time and can differ from their sex at birth or what is indicated on their legal documents, or a person may not identify with any specific gender.

While the Census collected data on gender diversity of Canadians, these data are only available for levels of geography with large populations (national, provincial, urban centres) to protect the confidentiality of non-binary and transgender persons. For all other levels of geography, non-binary and transgender persons have been aggregated into the two categories of gender - 'men+' and 'women+'.[^3] This change is not expected to have a significant impact on data analysis and historical comparability due to the small size of the transgender and non-binary populations.

## Population Pyramid

Population pyramids illustrate the age and sex structure of a population. <!-- As of 2021, _% of the population in _ was 65 or above, and _% of the population was 19 or younger. -->

<data-plot class="text-center" :spec=data.populationPyramid />

## Labour Force Population Pyramid

The figure below shows the age range distribution of children, emerging labour force, primary labour force, and seniors within the population.

<data-plot class="text-center" :spec=data.labourForcePyramid />

## Average Age

<data-table title="Table 1: Population average age and gender by community and regional district, 2021" url="/statics/data/cp_demographics_averageAge.csv" />

## Gender Ratio

The figure below shows the gender balance through the ratio of men to women.

<data-plot class="text-center" :spec=data.genderRatios />

[^1]: Statistics Canada. (2022). *[Census Profile, 2021 Census of Population](https://www12.statcan.gc.ca/census-recensement/2021/dp-pd/prof/index.cfm?Lang=E)*.

[^2]: Statistics Canada. (2022). *[Filling the gaps: Information on gender in the 2021 Census](https://www12.statcan.gc.ca/census-recensement/2021/ref/98-20-0001/982000012021001-eng.cfm)*.

[^3]: Selkirk Innovates recognizes that gender identity and gender expression are not a binary of male and female and that some transgender, non-binary, two spirit, and intersex populations may not be correctly represented by the data. With more nuanced questions on sex and gender identity, we hope these updates to Canada's 2021 Census of Population better represent LGBTQIA2+ populations.

<!--
Purpose: Community Profiles Web Development
Date: 2022-11-08
Analyst: Leeza Perehudoff
Version: 2
-->