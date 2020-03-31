# AU_COVID19
Time series of confirmed COVID-19 cases for Australian states, originally from and still cross-checked against https://www.covid19data.com.au/ When case numbers are reported at differing times of day, there may be differences between my data and that site.  I am trying to use my judgement to make the time series as consistent as possible, but the data is inherently messy and you shouldn't necessarily trust every daily percentage change for every state.

On 21 March, NSW changed from reporting case numbers as of 11am to case numbers as of 8pm the previous evening.

The NSW sources figures are extracted from the epidemiological curve figure at https://www.health.nsw.gov.au/Infectious/diseases/Pages/covid-19-latest.aspx My extraction code isn't necessarily precise (the axis ticks may be two pixels tall, for example), and there can be small discrepancies between my totals for each source of infection and the totals reported by NSW Health.  There are much larger discrepancies between the number of cases as shown in the epidemiological curve and the number of confirmed cases in time_series_cases.csv, presumably due to differences in the time of day of the two reports.  Expect the numbers for the last few days to be substantially revised upwards; date from earlier days is also subject to revision.

As of 16 March, relevant state health department links:

NSW: https://www.health.nsw.gov.au/Infectious/diseases/Pages/covid-19-latest.aspx

Vic: https://www.dhhs.vic.gov.au/coronavirus

Qld: https://www.qld.gov.au/health/conditions/health-alerts/coronavirus-covid-19/current-status/current-status-and-contact-tracing-alerts

SA: https://www.sahealth.sa.gov.au/wps/wcm/connect/public+content/sa+health+internet/about+us/news+and+media/all+media+releases

WA: https://ww2.health.wa.gov.au/Articles/A_E/Coronavirus

Tas: http://www.health.tas.gov.au/news/2020

ACT: https://health.act.gov.au/public-health-alert/updated-information-about-covid-19

NT: https://securent.nt.gov.au/alerts/coronavirus-covid-19-updates
