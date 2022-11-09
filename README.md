# Child speech delays increase following lockdowns

![Seven-year-old Lewis is growing in confidence and can now hold a conversation after attending his school's speech hub](https://ichef.bbci.co.uk/news/976/cpsprodpb/E8B3/production/_127317595_7cc1bdf4-c63c-4e06-9695-a201fc28140c.jpg.webp)

In November 2022 the BBC Shared Data Unit [looked at the rise in the number of five and six year olds who need speech and language support at school](https://www.bbc.co.uk/news/education-63373804), finding that it had risen by 10% in England in the last year.

## Methodology

An [R script was written in a Python notebook](https://github.com/BBC-Data-Unit/child-speech/blob/main/sen_covid_R1_ChangeByLA.ipynb) to download data, filter it, pivot it by local authority and year, and calculate year-on-year changes. 

A [second script](https://github.com/BBC-Data-Unit/child-speech/blob/main/sen_covid_R2_pupilNumbers.ipynb) downloaded data on pupil numbers, combined it with the figures on special educational needs (SEN), and divided the SEN figures by total pupil numbers to get a proportion. This allowed us to test whether an increase in speech, language and communication (SLC) needs might simply be due to an increase in pupils (it was not)

A [third script](https://github.com/BBC-Data-Unit/child-speech/blob/main/sen_covid_R3_eslNumbers.ipynb) downloaded data on the numbers of pupils for whom English was a second language (ESL), to test whether an increase in speech, language and communication needs might be due to an increase in ESL pupils (it was not), 

[A spreadsheet was used to test (using the `CORREL` function)](https://github.com/BBC-Data-Unit/child-speech/blob/main/SEN%20correlation%20vs%20ESL.xlsx) if there was any indication of a relationship between the proportion of ESL pupils in a local authority and the proportion needing speech, language and communication support: there was no correlation. 

The increase in SLC needs was also compared against other forms of special educational needs. This was done using [a pivot table](https://github.com/BBC-Data-Unit/child-speech/blob/main/sen_ncyear_COMPARE_NEEDS%20-%20Sheet1.csv) generated from the `sen_ncyear.csv` file downloaded from the DfE (see 'Get The Data' below). 

Speech and language was the biggest category of need, accounting for more than half of year 1 children needing SEN support, and had experienced one of the biggest increases. Only two categories experienced bigger rises: Multi-sensory impairment increased by 33% but this was from a low base (from 239 to 319 children nationally in year 1); and “SEN support but no specialist assessment of type of need” increased by 13%, from 2698 to 3044 children. 

[Further spreadsheet analysis compared the rise in Year 1 to other year groups](https://github.com/BBC-Data-Unit/child-speech/blob/main/sen_ncyear_COMPARE_YRGROUP.xlsx). This found that the rise in Year 1 was higher than any other age group, apart from Early Years. However, this was distorted by the number of pupils in Early Years education dropping significantly in the previous year due to parents keeping children home during the pandemic. The same drop did not exist in Year 1. The same pattern applied when the change in proportion was compared between years. 


## Regional analysis

A [dedicated website](https://senspeech.github.io/website/index.html) was created for the story which provided quotes from:

* Kamini Gadhok, Chief Executive of the Royal College of Speech, Language, Therapists (RCSLT)
* Jane Harris, chief executive of Speech and Language UK
* Minister for Schools and Childhood, Kelly Tolhurst, Department for Education

In addition, a page for each local authority provided:

* A customised text description of the situation in that area: how much numbers had risen or fallen in that area, whether the year-on-year change was higher or lower than the national average, and where the authority ranked in its region for change, compared to other local authorities
* Interactive tables putting each local authority into the context of other parts of the region, both in terms of absolute numbers and year-on-year change
* A line chart which showed how numbers in that area had changed in the last 6 years
* A grouped bar chart showing year-on-year changes in that area compared to the national figures

## Get the data

* [Special educational needs in England](https://explore-education-statistics.service.gov.uk/find-statistics/special-educational-needs-in-england) - the data used in this project can be found under the 'Download all data' link and the file `sen_ncyear.csv` within that. Column M for 'primary_need' was filtered to 'Speech, Language and Communications needs'
* [Schools, pupils and their characteristics](https://explore-education-statistics.service.gov.uk/find-statistics/school-pupils-and-their-characteristics)
* [Speech, communication and language needs by by local authority 2015-22 - year 1 pupils](https://github.com/BBC-Data-Unit/child-speech/blob/main/SEN%20(language)%20by%20LA%202015-22%20-%20year%201%20pupils.xlsx)
* [Additional Support Needs (ASN) in Scotland by type of need and local authority](https://github.com/BBC-Data-Unit/child-speech/blob/main/Scotland%20ASN%20(SEN)%20data%20by%20type%20of%20need.xlsx)
* [SEN in Wales 2018-22 by local authority](https://github.com/BBC-Data-Unit/child-speech/blob/main/walesSEN18to22_pup_analysis.xlsx)


## Partner usage

![](https://raw.githubusercontent.com/BBC-Data-Unit/child-speech/main/images/telegraph_image.jpg)

The story [featured on BBC Online](https://www.bbc.co.uk/news/education-63373804) and BBC News at One. It was also discussed in debates on Radio 5Live.

The BBC Shared Data Unit makes data journalism available to the wider news industry as part of the BBC Local News Partnership.

Stories written in print and online by partners based on this research included:

* Rutland and Stamford Mercury: [More children need speech and language support in first year of school, with the rise in Lincolnshire above the national average](https://www.stamfordmercury.co.uk/news/more-children-need-speech-and-language-support-in-first-year-9282911/)
