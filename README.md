# Child speech delays increase following lockdowns

![Seven-year-old Lewis is growing in confidence and can now hold a conversation after attending his school's speech hub](https://ichef.bbci.co.uk/news/976/cpsprodpb/E8B3/production/_127317595_7cc1bdf4-c63c-4e06-9695-a201fc28140c.jpg.webp)

In November 2022 the BBC Shared Data Unit [looked at the rise in the number of five and six year olds who need speech and language support at school](https://www.bbc.co.uk/news/education-63373804), finding that it had risen by 10% in England in the last year.

## Methodology

An R script was written in a Python notebook to download data, filter it, pivot it by local authority and year, and calculate year-on-year changes. 

A second script downloaded data on pupil numbers, combined it with the figures on special educational needs (SEN), and divided the SEN figures by total pupil numbers to get a proportion. This allowed us to test whether an increase in speech, language and communication (SLC) needs might simply be due to an increase in pupils (it was not)

A third script downloaded data on the numbers of pupils for whom English was a second language (ESL), to test whether an increase in speech, language and communication needs might be due to an increase in ESL pupils (it was not), or if there was a relationship between the proportion of ESL pupils in a local authority and the proportion needing speech, language and communication support (there was no correlation). 

A fourth analysis compared the increase in SLC needs against other forms of special educational needs. This was done using a pivot table generated from the `sen_ncyear.csv` file. Speech and language is the biggest category of need, accounting for more than half of year 1 children needing SEN support, and has experienced one of the biggest increases. Only two categories experienced bigger rises: Multi-sensory impairment increased by 33% but this was from a low base (from 239 to 319 children nationally in year 1); and “SEN support but no specialist assessment of type of need” increased by 13%, from 2698 to 3044 children. 


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

Data on SEN was downloaded from the Department for Education's [Special educational needs in England data page](https://explore-education-statistics.service.gov.uk/find-statistics/special-educational-needs-in-england) - specifically the 'Download all data' link and the file `sen_ncyear.csv` within that. Column M for 'primary_need' was filtered to 'Speech, Language and Communications needs'

Data on pupil numbers was obtained from [Schools, pupils and their characteristics](https://explore-education-statistics.service.gov.uk/find-statistics/school-pupils-and-their-characteristics). 


## Partner usage

The story [featured on BBC Online](https://www.bbc.co.uk/news/education-63373804) and BBC News at One. It was also discussed in debates on Radio 5Live.

The BBC Shared Data Unit makes data journalism available to the wider news industry as part of the BBC Local News Partnership.

Stories written in print and online by partners based on this research included:

* 
