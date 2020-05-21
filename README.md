# COVID-19 New York City Data
_**Update - May 21, 2020:** We are now updating `hospitalized.csv` using data [from the state](https://forward.ny.gov/daily-hospitalization-summary-region), which is a more accurate version of our existing numbers from city hall. We've updated all records since March 26._

_**Update - May 19, 2020:** We are no longer updating `borough.csv`, `age.csv`, `gender.csv`, `nyc.csv` and `zcta.csv`. This data is now available from May 18 on through the Department of Health and Mental Hygiene [coronavirus data repo](https://github.com/nychealth/coronavirus-data). We will continue to update `state.csv`, `hospitalized.csv` and `beds.csv` as we receive data._

[THE CITY](https://thecity.nyc) is releasing data we have been collecting since the outbreak of COVID-19 in New York City, tracking confirmed cases, deaths and hospitalizations by borough, age and gender, confirmed cases and tests by ZIP code, current hospitalizations and ICU hospitalizations in New York City, and testing, hospitalization, case number and hospital bed availability data released by the state. This is the same data that powers our [Coronavirus in New York City tracker](https://projects.thecity.nyc/2020_03_covid-19-tracker/).

The data is primarily based on [daily reports](https://www1.nyc.gov/site/doh/covid/covid-19-data.page) issued by the city Department of Health and Mental Hygiene and [daily press briefings](https://www.youtube.com/user/nygovcuomo/videos) from the governor’s office, as well as the state Department of Health [COVID-19 tracker](https://covid19tracker.health.ny.gov/views/NYS-COVID19-Tracker/NYSDOHCOVID-19Tracker-Map). We also reach out to the mayor's office and governor's office every day for data on current hospitalizations in New York City and hospital bed availability for the city and state. We will attempt to update this repository whenever we post an update to our tracker, which is at least once a day.

Please email us at [data@thecity.nyc](mailto:data@thecity.nyc) with any questions and we will respond as time permits.

## Record types

The following types are used to categorize records for borough, gender and age data.

- `cases`: Total number of confirmed cases with a positive COVID-19 test.

- `deaths-probable`: Number of probable deaths with demographic data reported. This is a fraction of the total probable deaths recorded in nyc.csv. Probable deaths are cases where COVID-19 was listed as the cause of death on a death certificate, but there is no positive COVID-19 test. This data was first made available for April 13.
- `deaths`: Total number of confirmed deaths with a positive test for COVID-19.
- `deaths-underlying`: Starting March 27, the NYC Department of Health and Mental Hygiene started releasing information on the number of fatalities that had underlying illnesses. Underlying illnesses include diabetes, lung disease, cancer, immunodeficiency, heart disease, hypertension, asthma, kidney disease, and GI/liver disease. This number only includes individuals with a positive test for COVID-19.
- `deaths-no-underlying`: Number of deaths that had no underlying illness and had a positive test for COVID-19.
- `deaths-pending-underlying`: Number of deaths under investigation to determine if they had an underlying illness with a positive test for COVID-19.
- `ever-hospitalized`: Total number of cases that have ever been hospitalized with a positive test for COVID-19. This number does not account for discharges or deaths and is usually updated once in the evening. It was first made available for March 24.

## Files

### borough.csv

Number of cases, deaths and hospitalizations by borough from the New York City Department of Health and Mental Hygiene.

- `timestamp`: Time of the update from the city’s health department in UTC.
- `type`: See [record types](#record-types).
- `queens`, `manhattan`, `brooklyn`, `bronx`, `staten_island`, `unknown` and `total`: Residency of patients, NOT the place of infection, hospitalization or fatality.

### gender.csv

Number of cases, deaths and hospitalizations by gender from the New York City Department of Health and Mental Hygiene.

- `timestamp`: Time of the update from the city’s health department in UTC.
- `type`: See [record types](#record-types).
- `female`, `male`, `unknown` and `total`: Gender of the patient.

### age.csv

Number of cases, deaths and hospitalizations from the New York City Department of Health and Mental Hygiene by five age groups: 0-17, 18-44, 45-64, 65-74 and 75+. Different age groupings were provided prior to March 22 and aren’t included in the data.

- `timestamp`:  Time of the update from the city’s health department in UTC.
- `type`: See [record types](#record-types).
- `ages_0_17`, `ages_18_44`, `ages_45_64`, `ages_65_74`, `ages_75_older`, `unknown` and `total`: Age groups provided by the city’s health department.

### nyc.csv

Total number of cases, deaths and hospitalizations from the New York City Department of Health and Mental Hygiene.

- `timestamp`: Time of the update from the city’s health department in UTC.
- `cases`: Total number of total positive cases.
- `deaths`: Total number of deaths with a positive test for COVID-19.
- `probable_deaths`: Probable deaths are cases when COVID-19 was listed as the cause of death on a death certificate, but there is no positive COVID-19 test. This data includes deaths without demographic data and was first made available for April 13.
- `ever_hospitalized`: Total number of cases that have been hospitalized. This number does not account for discharges or deaths and is usually updated once in the evening. It was first made available for March 24.

### zcta.csv

Number of tests and confirmed cases by [ZIP code tabulation area](https://www.census.gov/programs-surveys/geography/guidance/geo-areas/zctas.html) from the New York City Department of Health and Mental Hygiene.

- `timestamp`: Date on which the data was collected by the city’s health department in UTC.
- `zcta`: Five-digit id for the ZCTA from the 2010 Census.
- `positive`: Number of confirmed cases with a positive COVID-19 test.
- `total`: Number of individuals tested.


### hospitalized.csv

Number COVID-19 patients currently hospitalized in New York City. This data is requested from the mayor's office once per day and represents a conservative estimate.

- `timestamp`: Time of the update from the mayor’s office in UTC.
- `hospitalized`: Number of currently hospitalized COVID-19 patients as of the timestamp.
- `icu`: Number of ICU beds currently occupied by COVID-19 patients as of the timestamp.

### state.csv

Number of tests, positive cases, current hospitalizations, current ICU hospitalizations and patients who have been discharged statewide, as well as tests and positive cases for New York City from the governor’s office.

- `timestamp`: Time at which data was collected by the state in UTC. This is always midnight the day before the data is released.
- `nyc_tested`: Total number of people tested in New York City.
- `tested`: Total number of people tested statewide.
- `hospitalized`: Number of patients currently hospitalized.
- `icu`: Number of patients currently in ICUs.
- `discharged`: Total number of patients who have been discharged.
- `nyc_cases`: Total number of cases with positive tests in New York City.
- `cases`: Total number of cases with positive tests statewide.

### beds.csv

Number of beds and ICU beds at permanent hospitals in the city and state, and number of each currently available. This data comes from a state survey of hospitals and is requested from the governor's office once per day.

- `timestamp`: Date on which the data was collected by the state in UTC.
- `locality`: `nyc` for hospitals in the city and `state` for all hospitals in the state.
- `total`: Total number of beds at permanent hospitals.
- `total_available`: Number of all beds at permanent hospitals that are unoccupied.
- `icu`: Number of ICU beds at permanent hospitals.
- `icu_available`: Number of ICU beds at permanent hospitals that are unoccupied.

## License

In general, you may use the free data published by THE CITY under the following terms, which draw inspiration and specific language from ProPublica, among others.

- You can’t republish the raw data in its entirety, or otherwise distribute the data (in whole or in part) on a stand-alone basis.
- You can’t change the data except to update or correct it.
- You can’t charge people money to look at the data, or sell advertising specifically against it.
- You can’t sub-license or resell the data to others.
- If you use the data for publication, you must credit THE CITY and include a link to our site at [https://thecity.nyc](https://thecity.nyc).
- We do not guarantee the accuracy or completeness of the data. You acknowledge that the data may contain errors and omissions.
- We are not obligated to update the data, but in the event we do, you are solely responsible for checking our site for any updates.

If you have any questions, please contact us at [data@thecity.nyc](mailto:data@thecity.nyc).
