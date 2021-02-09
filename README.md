# Project-1
Boot Camp Project # 1

DATA SOURCES
1. Census data
"Annual Estimates of the Resident Population for Counties: April 1, 2010 to July 1, 2019"
The raw data is available at:
https://www2.census.gov/programs-surveys/popest/datasets/2010-2019/counties/totals/co-est2019-alldata.csv

There are more columns in this .CSV than will fit across the screen, starting with:
SUMLEV	REGION	DIVISION	STATE	COUNTY	STNAME	CTYNAME	CENSUS2010POP...
but for our purposes, the only other column we need is eleven columns later: POPESTIMATE2019
and we don't need SUMLEV, REGION, or DIVISION, so what's required for this analysis is
a dataframe drawn from co-est2019-alldata.csv structured as follows:

FIPS STATE	COUNTY	STNAME	CTYNAME	CENSUS2010POP POPESTIMATE2019
01000  1	0	Alabama	Alabama	4779736 4903185
01001   1	1	Autaga	Alabama	54571 55869

where the five-digit FIPS code for each county is derived from STATE and COUNTY by
formatting STATE as a two-digit string, e.g. "01",
and concatening it with COUNTY as a three-digit string, e.g. "001",
giving 01001 for Autaga County, Alabama.

More information on methodology is available here:
https://www.census.gov/data/tables/time-series/demo/popest/2010s-counties-total.html



2. COVID-19 cases
cases and deaths from COVID-19 per county from the New York Times, updated daily.
The raw data is available at:
https://github.com/nytimes/covid-19-data/blob/master/us-counties.csv

The following is from the ReadMe accompanying the raw data:

date,county,state,fips,cases,deaths
2020-01-21,Snohomish,Washington,53061,1,0

That ReadMe, including more information on methodology and attribution, is here:
https://github.com/nytimes/covid-19-data/blob/master/README.md



3. Mask-use survey
Survey conducted by Dynata for the New York Times to gain 250,000 responses nationwide.
The raw survey data is available at:
https://github.com/nytimes/covid-19-data/blob/bde13b021e99c6b4a63fb66a6144e889cc635e31/mask-use/mask-use-by-county.csv

The following is from the ReadMe accompanying the raw survey data:

    COUNTYFP,NEVER,RARELY,SOMETIMES,FREQUENTLY,ALWAYS
    01001,0.053,0.074,0.134,0.295,0.444
    01003,0.083,0.059,0.098,0.323,0.436
    01005,0.067,0.121,0.12,0.201,0.491

    COUNTYFP: The county FIPS code (1).
    NEVER: The estimated share of people in this county who would say never in response to the question “How often do you wear a mask in public when you expect to be within six feet of another person?”
    RARELY: The estimated share of people in this county who would say rarely
    SOMETIMES: The estimated share of people in this county who would say sometimes
    FREQUENTLY: The estimated share of people in this county who would say frequently
    ALWAYS: The estimated share of people in this county who would say always

That ReadMe, including more information on methodology and attribution, is here:
https://github.com/nytimes/covid-19-data/blob/bde13b021e99c6b4a63fb66a6144e889cc635e31/mask-use/README.md


--

(1) The last three digits of a FIPS code refer to county. The first one or two digits refer to state. More information on FIPS codes is available at:
https://transition.fcc.gov/oet/info/maps/census/fips/fips.txt#:~:text=FIPS%20codes%20are%20numbers%20which,to%20which%20the%20county%20belongs.
and
https://en.wikipedia.org/wiki/FIPS_county_code