---
maritalStatus:
  title: "Figure 1: Total population by marital status (%), 2021"

  meta:
    source: Statistics Canada
    year: 2022
    title: Census Profile, 2021 Census of Population
    url: https://www12.statcan.gc.ca/census-recensement/2021/dp-pd/prof/index.cfm?Lang=E

  data:
    url: /statics/data/cp_demographics_maritalStatus.csv

  mark: bar

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
        - field: Marital Status
          type: ordinal
        - field: Percent
          type: quantitative
          format: '.1%'
        - field: Gender
          type: nominal      
        y:
          field: Marital Status
          type: ordinal
          axis: null
          sort:
            [
              "Never legally married",
              "Married",
              "Common-law",
              "Separated",
              "Divorced",
              "Widowed",
            ]
        x:
          # aggregate: sum
          field: Percent
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
          field: Marital Status
          type: ordinal
          axis: null
          sort:
            [
              "Never legally married",
              "Married",
              "Common-law",
              "Separated",
              "Divorced",
              "Widowed",
            ]
        text:
          field: Marital Status
          type: ordinal

    - transform:
        - filter:
            field: Gender
            equal: Women+
      title: Women+
      mark: bar
      encoding:
        tooltip:
        - field: Marital Status
          type: ordinal
        - field: Percent
          type: quantitative
          format: '.1%'
        - field: Gender
          type: nominal  
        y:
          field: Marital Status
          type: ordinal
          title: null
          axis: null
          sort:
            [
              "Never legally married",
              "Married",
              "Common-law",
              "Separated",
              "Divorced",
              "Widowed",
            ]
        text:
        x:
          field: Percent
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

---

# Family Characteristics

Family characteristics such as size and composition of families can help inform social, economic, health, and education programming, as well as planning and development around infrastructure needs. [^1]

## Family Composition

<data-table title="Table 1: Total number of families, individuals, and average family size, 2021" url="/statics/data/cp_demographics_families.csv" />

<data-table title="Table 2: Total number of parents, children, and average number of children, 2021" url="/statics/data/cp_demographics_parentsChildren.csv" />

## Marital Status

The chart below shows men+ and women+ who are married, living common law, single, separated, divorced or widowed as a percent of the total population aged 15 years and older.[^2]

The 2021 Census of Population marked the first time separate questions were asked about the respondent's sex at birth and their gender.[^3] Gender refers to a person's personal and social characteristics, which can include their gender identity (internal and individual feelings) and gender expression (the way their gender is presented, regardless of gender identity). A person's gender may change over time and can differ from their sex at birth or what is indicated on their legal documents, or a person may not identify with any specific gender.

While the Census collected data on gender diversity of Canadians, these data are only available for levels of geography with large populations (national, provincial, urban centres) to protect the confidentiality of non-binary and transgender persons. For all other levels of geography, non-binary and transgender persons have been aggregated into the two categories of gender - 'men+' and 'women+'.[^4] This change is not expected to have a significant impact on data analysis and historical comparability due to the small size of the transgender and non-binary populations.

<data-plot :spec="data.maritalStatus" />

[^1]: Statistics Canada. (2022). *[Census Profile, 2021 Census of Population](https://www12.statcan.gc.ca/census-recensement/2021/dp-pd/prof/index.cfm?Lang=E)*.
[^2]: The total summed percent will equal more than 100% because those who identify as never legally married, separated, divorced, and widowed may also identify as common-law.
[^3]: Statistics Canada. (2022). *[Filling the gaps: Information on gender in the 2021 Census](https://www12.statcan.gc.ca/census-recensement/2021/ref/98-20-0001/982000012021001-eng.cfm)*.
[^4]: Selkirk Innovates recognizes that gender identity and gender expression are not a binary of male and female and that some transgender, non-binary, two spirit, and intersex populations may not be correctly represented by the data. With more nuanced questions on sex and gender identity, we hope these updates to Canada's 2021 Census of Population better represent LGBTQIA2+ populations.

<!--
Purpose: Community Profiles Web Development
Date: 2022-11-17
Analyst: Leeza Perehudoff
Version: 1
-->
