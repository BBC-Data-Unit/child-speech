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

To present the analysis for each local authority R notebooks were written using **parameterisation**:

* [Produce an analysis for a given local authority](https://github.com/BBC-Data-Unit/child-speech/blob/main/parameterisation/01latemplate.Rmd)
* [Render 155 versions of that analysis](https://github.com/BBC-Data-Unit/child-speech/blob/main/parameterisation/02rendering.Rmd) - one for each local authority
* [Generate 155 HTML versions of that analysis - including code cleaning](https://github.com/BBC-Data-Unit/child-speech/blob/main/parameterisation/03renderandclean.Rmd)
* [Generate an index page that linked to those](https://github.com/BBC-Data-Unit/child-speech/blob/main/parameterisation/index.Rmd)

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

* Bolton News: [Bolton: Hundreds of children need extra language support post-lockdown](https://www.theboltonnews.co.uk/news/23101201.bolton-hundreds-children-need-extra-language-support-post-lockdown/)
* Breitbart: [Britain Sees Spike in Children Requiring Speech Support After Lockdown](https://www.breitbart.com/europe/2022/11/08/britain-sees-spike-in-children-requiring-speech-support-after-lockdown/)
* Cambridge Independent: [Children’s language needs in Cambridgeshire rise post-lockdown, figures show](https://www.cambridgeindependent.co.uk/news/children-s-language-needs-in-cambridgeshire-rise-post-lockdo-9284418/)
* EdCentral: [Child speech delays increase due to lockdowns](https://edcentral.uk/ednews/early-years-primary/6586-child-speech-delays-increase-due-to-lockdowns)
* Education Executive: [Child speech delays increase following lockdown](https://edexec.co.uk/child-speech-delays-increase-following-lockdown/)
* Grantham Journal: [More children need speech and language support in first year of school, with the rise in Lincolnshire above the national average](https://www.granthamjournal.co.uk/news/more-children-need-speech-and-language-support-in-first-year-9282772/)
* Jack FM: [20% rise in children needing help with speech and language in Oxfordshire](https://www.jackfm.co.uk/news/oxfordshire-news/20-rise-in-children-needing-help-with-speech-and-language-in-oxfordshire/)
* Lichfield Live: [Figures show rise in number of Staffordshire children needing speech and language support](https://lichfieldlive.co.uk/2022/11/07/figures-show-rise-in-number-of-staffordshire-children-needing-speech-and-language-support/)
* Lynn News: [More Year 1 children in Norfolk needed speech and language support year after Covid lockdown, data shows](https://www.lynnnews.co.uk/news/more-child-speech-delays-in-norfolk-after-covid-lockdowns-9282965/)
* Manchester World: [More children starting school in Greater Manchester need speech and language support, data shows](https://www.manchesterworld.uk/news/more-children-starting-school-in-greater-manchester-need-speech-and-language-support-data-shows-3912772)
* Manchester World: [How parents can help children with speech and language if they are struggling to get help - a therapist’s tips](https://www.manchesterworld.uk/news/how-parents-can-help-children-with-speech-and-language-therapists-tips-3921891)
* MK Citizen: [New data shows 13% increase in number of children in Milton Keynes needing speech therapy support](https://www.miltonkeynes.co.uk/news/people/new-data-shows-13-increase-in-number-of-children-in-milton-keynes-needing-speech-therapy-support-3913889)
* NASEN: [More early speech and language support needed as a result of the lockdowns ](https://nasen.org.uk/news/more-early-speech-and-language-support-needed-result-lockdowns)
* Newark Advertiser: [Rise in number of Nottinghamshire school children needing support with speech and language](https://www.newarkadvertiser.co.uk/news/rise-in-number-of-school-children-needing-support-with-speec-9282723/)
* Newbury Today: [West Berkshire in the top 10 areas for increases in speech and language needs of children](https://www.newburytoday.co.uk/news/child-speech-problems-rise-after-lockdown-9283423/)
* On The Wight: [Isle of Wight children needing support for speech, language and communication in Year 1 rose by 15.29 per cent compared to previous year](https://onthewight.com/isle-of-wight-children-needing-support-for-speech-language-and-communication-in-year-1-rose-by-15-29-per-cent-compared-to-previous-year/)
* Peterborough Today: [Concern as some children in Peterborough schools fall behind in language skills](https://www.peterboroughtoday.co.uk/news/people/concern-as-some-children-in-peterborough-schools-fall-behind-in-language-skills-3912204)
* Rutland and Stamford Mercury: [More children need speech and language support in first year of school, with the rise in Lincolnshire above the national average](https://www.stamfordmercury.co.uk/news/more-children-need-speech-and-language-support-in-first-year-9282911/)
* Suffolk News: [Bury St Edmunds head Maria Kemble speaks of rise in pupils with speech and language struggles as data shows 9% increase in need in Suffolk in Year 1](https://www.suffolknews.co.uk/bury-st-edmunds/news/data-reveals-9-rise-in-year-1-pupils-needing-speech-and-lan-9282684/)
* Thurrock Nub News: [Problem of communication learning for early years children is rising steeply in Thurrock](https://thurrock.nub.news/news/local-news/problem-of-communication-learning-for-early-years-children-is-rising-steeply-in-thurrock-158074)
* Wigan Today: [Huge rise in the number of Wigan children starting school needing speech and language support](https://www.wigantoday.net/education/huge-rise-in-the-number-of-wigan-children-starting-school-needing-speech-and-language-support-3915250)
