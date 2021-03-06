# USI_social_impact
Repo for the USI social impact project done by the Part Timer team

******
DATA
******

All data used in this project is public and sourced as follows:

FDNY = https://data.cityofnewyork.us/Public-Safety/Incidents-Responded-to-by-Fire-Companies/tm6d-hbzd/data

NYC MapPLUTO (use 2015 MapPLUTO data, version '15v1' on this page): https://www1.nyc.gov/site/planning/data-maps/open-data/pluto-mappluto-archive.page

DOB COMPLAINTS: https://data.cityofnewyork.us/Housing-Development/DOB-Complaints-Received/eabe-havv

DOB VIOLATIONS: https://data.cityofnewyork.us/Housing-Development/DOB-Violations/3h2n-5cm9

DOB ECB VIOLATIONS: https://data.cityofnewyork.us/Housing-Development/DOB-ECB-Violations/6bgk-3dad

HISTORICAL DOB PERMITS: https://data.cityofnewyork.us/Housing-Development/Historical-DOB-Permit-Issuance/bty7-2jhb

NYC ZIPCODE SHAPEFILES: public, but saved in repo in /raw_data on CUSP server

PAD (used to assign zip codes to BIN): retreived from NYC.gov/CityPLanning but saved in /raw_data on CUSP server

ACS:

**************
PRE-PROCESSING
**************
Data must be integrated, cleaned, filtered, and scaled as appropriate. That is done through various pre-processing scripts and notebooks.

"Preprocessing_zipcode_output"
- Takes as input:
    - FDNY
    - NYC MapPLUTO
    - DOB COMPLAINTS
    - DOB VIOLATIONS
    - DOB ECB VIOLATIONS
    - HISTORICAL DOB PERMITS
    - NYC ZIPCODE SHAPEFILES
    - PAD
    
- Data directory "/raw_data" should be structured as indicated in notebook (how it's structured on CUSP server)

- Must also create a "/processed_data" folder in your root working directory (i.e. this repo on local machine)

- This script filters for select features from each data set, aggregates and scales values for these features to the zip code level, and integrateds them.

- NOTE: for processing efficiency, you only must run PLUTO data loading once and create a pickle in your local directory /processed_data/master_pluto.pickle  and then you can commment out those lines and subsequently load the pickle.

- OUTPUT: a sparse matrix of approx 187 zip codes with 1400+ feature fields
