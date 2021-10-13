# HCDS 512 Assignment 1 - Bias in Data

# Goal of the Project
The goal of this assignment is to explore the concept of bias through data on Wikipedia articles - specifically, articles on political figures from a variety of countries. In this project, I combined a dataset of Wikipedia articles with a dataset of country populations (`WPDS_2020_data.csv` and `page_data.csv`), and used a machine learning service called ORES to estimate the quality of each article. I performed an analysis of how the coverage of politicians on Wikipedia and the quality of articles about politicians varies between countries. My analysis will consist of a series of tables that show:
*  the countries with the greatest and least coverage of politicians on Wikipedia compared to their population.
*  the countries with the highest and lowest proportion of high quality articles about politicians.
*  a ranking of geographic regions by articles-per-person and proportion of high quality articles.


# APIs
The source datasets of this project are: 
1.  Politicians by Country from the English-language Wikipedia(Keyes, Os, 2017):  Figshare.  
*  Licensed under the CC-BY-SA 4.0 licenses
*  Privacy policy & Terms of use: https://doi.org/10.6084/m9.figshare.5513449.v6 

2.  2020 World Population Data Sheet
*  Published by the Population Reference Bureau.
*  Privacy policy & Terms of use: https://www.prb.org/privacy-policy/

The documentation for the two APIs can be found here:
* The Wikipedia politicians by country dataset: https://figshare.com/articles/dataset/Untitled_Item/5513449
* The population data: https://www.prb.org/international/indicator/population/table/

# Model
We're using a machine learning system called ORES. This was originally an acronym for "Objective Revision Evaluation Service" but was simply renamed “ORES”. ORES is a machine learning tool that can provide estimates of Wikipedia article quality. The article quality estimates are, from best to worst:
1.   FA - Featured article
2.   List item
3.   GA - Good article
4.   B - B-class article
5.   C - C-class article
6.   Start - Start-class article
7.   Stub - Stub-class article

These were learned based on articles in Wikipedia that were peer-reviewed using the Wikipedia content assessment procedures. These quality classes are a sub-set of quality assessment categories developed by Wikipedia editors. For more details, please see https://en.wikipedia.org/wiki/Wikipedia:Content_assessment.

In this project, we are using ORES client, which is licensed under the MIT license. Please see https://github.com/wikimedia/ores for installation instructions.


# Curated Data

The processed data are stored into a single CSV file, `wp_wpds_politicians_by_country.csv`, with the following headers:
| Column | Description |
|--------|-------------|
| country | Name of the country |
| article_name | Name of the article |
| revision_id | Revision ID of the article on Wikipedia |
| article_quality | Quality class as determined by ORES |
| Population | Population of the country |

For the analysis and results, the following headers were used:

| Column | Description |
|--------|-------------|
| country/Region | Name of the country/region |
| bad-articles | Number of non-FA and non-GA class articles |
| good-articles | Number of FA or GA class articles |
| Total-articles| Total number of articles for the corresponding country/region; equals to bad-articles+good-articles |
| quality rate | The relative proportion of politician articles that are of GA and FA-quality |
| Coverage | Percentage of politician articles as a proportion of country population |
| Population | Population of the country |

Please see the data cleaning and analysis process in the notebook `hcds-a2-bias.ipynb`.

# Reflections and Implications
Please see the notebook `hcds-a2-bias.ipynb`.
