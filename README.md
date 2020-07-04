# AU_COVID19
Time series of confirmed COVID-19 cases for Australian states, originally from and still cross-checked against [covid19data.com.au](https://www.covid19data.com.au/), compiled primarily by Juliette O'Brien.  When case numbers are reported at differing times of day, there may be differences between my data and that site.  I am trying to use my judgement to make the time series as consistent as possible, but the data is inherently messy and you shouldn't necessarily trust every daily percentage change for every state.

## Notes on NSW
- On 3 July, NSW reported 189 historical cases from cthe Ruby Princess to the federal government, which now appear in NSW's totals published by the federal Department of Health, but not by NSW Health (the cases &ndash; all crew members &ndash; were diagnosed and managed on the ship).  My numbers follow the NSW Health website, so exclude these cases.

- The NSW sources of infection are from [Data.NSW's CSV file](https://data.nsw.gov.au/data/dataset/nsw-covid-19-cases-by-location-and-likely-source-of-infection/resource/2776dbb8-f807-4fb2-b1ed-184a6fc2c8aa), which now contains the full case dataset, up to several days ago ("Publication of some data in this dataset is being delayed because the risk of gaining information about an individual in the dataset increases as the number of cases decreases").  The following bullet points are no longer relevant unless you're trying to piece together the history of time_series_nsw_sources.csv. **Update 4 June** On 3 June, the dates in the CSV file for all or most cases were changed. I believe that previously, the date was the date of test sample, and now I don't know, but it might now be date of test analysis or something related.

- ~~The NSW sources figures prior to 9 March are extracted from the epidemiological curve graph at the [NSW Health statistics page](https://www.health.nsw.gov.au/Infectious/diseases/Pages/covid-19-latest.aspx). My extraction code isn't necessarily precise (the axis ticks may be two pixels tall, for example), and there can be small discrepancies between my totals for each source of infection and the totals reported by NSW Health.  On 3 April, the published graph stopped distinguishing between 'locally acquired from unknown source' and 'locally acquired from a known contact/cluster', and I have used the graph published on 2 April for these early dates, which will probably cause minor inconsistencies as this early data is still occasionally revised.  I have arbitrarily placed two cases (1 March and 7 March) in the amalgamated 'local' category into 'local unknown'.~~

- ~~Numbers since 9 March are counted from the CSV file [at Data.NSW](https://data.nsw.gov.au/data/dataset/nsw-covid-19-cases-by-likely-source-of-infection/resource/2f1ba0f3-8c21-4a86-acaf-444be4401a6d) There are much larger discrepancies between the number of cases as shown in the epidemiological curve and the number of confirmed cases in time_series_cases.csv, I think because the date reported in this file (and graph) is the date that the sample was taken, and there can be quite a lag between the sample being taken and it being analysed to a positive result.  Expect the numbers for the last few days to be substantially revised upwards as the backlog of samples is tested; data from earlier days is also subject to revision.~~

- ~~On 11 April, many cases previously classified as 'Locally acquired - contact not identified' were reclassified into the new category 'Overseas or interstate'.  On 14 April, a separate 'Interstate' category was introduced into the source CSV; this standalone category doesn't exist in the graphs, so my data does not show any interstate infections prior to 9 March, even though some may be recorded as such internally at NSW Health.~~

- On 21 March, NSW changed from reporting case numbers as of 11am to case numbers as of 8pm the previous evening.

Thanks to [@tetrakazi](https://twitter.com/tetrakazi) for [her scraper](https://github.com/theojulienne/covid-19-data-aus/blob/master/scripts.hourly/50-vic.py) of the Victorian data, which I have adapted for the sources of infections for that state.  I don't know why our time series don't agree.

Prior to 21 April, a bug in my parsing scripts meant that there were occasional errors in time_series_vic_sources.csv and time_series_act_sources.csv.  From 21 April, the total numbers of reported cases should tally correctly with time_series_cases.csv.

In time_series_tests.csv:
- WA's figures are persons tested until 30 April; from 1 May they are tests performed.
- NSW's figures are persons tested until 25 May; from 26 May they are tests performed.
- Other states are (I believe) all tests performed.
- On 6 June, Victoria's number fell by about 12,000 after removing duplicated data.
- Qld added about 38,500 tests from a private provider on 22 June.

As of 23 April, relevant state health department links:

NSW: [COVID-19 page](https://www.nsw.gov.au/covid-19), [Source of infections CSV](https://data.nsw.gov.au/data/dataset/nsw-covid-19-cases-by-location-and-likely-source-of-infection/resource/2776dbb8-f807-4fb2-b1ed-184a6fc2c8aa)

Vic: [Dashboard](https://app.powerbi.com/view?r=eyJrIjoiODBmMmE3NWQtZWNlNC00OWRkLTk1NjYtMjM2YTY1MjI2NzdjIiwidCI6ImMwZTA2MDFmLTBmYWMtNDQ5Yy05Yzg4LWExMDRjNGViOWYyOCJ9)

Qld: [Statistics](https://www.qld.gov.au/health/conditions/health-alerts/coronavirus-covid-19/current-status/statistics)

SA: [Dashboard](https://www.covid-19.sa.gov.au/home/dashboard)

WA: [Dashboard](https://experience.arcgis.com/experience/359bca83a1264e3fb8d3b6f0a028d768)

Tas: [Statistics](https://coronavirus.tas.gov.au/facts/cases-and-testing-updates); my daily updates used to follow the (discontinued as of 12 June) evening case announcements, usually tweeted by [Monte Bovill (ABC)](https://twitter.com/MonteBovill), [Emily Jarvie (Advocate/Examiner)](https://twitter.com/emilyjjarvie), and others.

ACT: [Dashboard](https://app.powerbi.com/view?r=eyJrIjoiZTY4NTI1NzQtYTBhYy00ZTY4LTk3NmQtYjBjNzdiOGMzZjM3IiwidCI6ImI0NmMxOTA4LTAzMzQtNDIzNi1iOTc4LTU4NWVlODhlNDE5OSJ9)

NT: [COVID-19 page](https://coronavirus.nt.gov.au/)

The federal government's [PDF infographic](https://www.health.gov.au/resources/publications/coronavirus-covid-19-at-a-glance) has some testing statistics not always released by the state health departments.
