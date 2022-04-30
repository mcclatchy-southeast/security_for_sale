

# Security for Sale

Following the collapse of the housing market in the Great Recession, a small contingent of hedge funds and private equity firms bought up scores of single-family homes as part of a new real estate investment strategy.

Instead of flipping these properties, investors held onto them, making money from rental payments and fees and growing equity as the value of the properties recovered. They also created rental-backed securities, a new financial instrument that sold bond holders the promise of future rental income.

Read our three-day series beginning May 1, 2022, into how the growth of the single-family rental industry is affecting tenants, neighborhoods and communities in **Security for Sale** in one of our three partner publications:

 - [The News & Observer](http://www.newsobserver.com/securityforsale)
 - [The Charlotte Observer](http://www.charlotteobserver.com/securityforsale)
 - [The Herald Sun](http://www.heraldsun.com/securityforsale)

*Note: This repo will be updated periodically with new data and resources.*

## How we did this story
Tracking the single-family rental companies and their purchases is tricky.

Although there are just a handful of national corporations buying on a large scale in Charlotte and Triangle, they use a myriad of subsidiaries and holding companies to conduct their business. There's also variation – misspellings, mixed punctuation and the link – in how these subsidiaries are recorded in property records managed by each of the state's 100 counties.

"This has been such an opaque issue for decades now that we have really, really bad data flowing around in the public sphere about how active these types of investment funds are," David Szakonyi, an assistant professor of political science at Georgetown University and co-founder of the Anti-Corruption Data Collective.

So in the winter of 2021, reporters at The News & Observer and The Charlotte Observer set about creating the most authoritative dataset possible of investment buyers across the state – particularly the single-family homes that have long been key to middle-class American wealth.

Reporters first manually scoured property records in Wake and Mecklenburg counties to create a database of parent companies and their most common subsidiaries, which can often be linked by naming convention, corporate mailing address and company officials. They used that list to create a machine learning model to find other name variations.

Data from other researchers examining the growth of the single-family rental industry, including the UNC-Charlotte Urban Institute and Massachusetts Institute of Technology researcher Maya Abood, was used to add more names. North Carolina court data on eviction proceedings, state utility data and corporate registration data from the nonprofit OpenCorporates helped, too. The Anti-Corruption Data Collective supplied additional property transaction data through a research agreement with the real estate tech firm Zillow.

Almost all subsidiaries identified by the N&O and Observer's reporting were matched – either with statistical software or manually – to corporate registrations [filed with the N.C. Secretary of State's Office](https://www.sosnc.gov/online_services/search/by_title/_Business_Registration) to verify connections with their parent companies.

The list of investor subsidiaries was then matched using statistical software with property owner names recorded by the [North Carolina OneMap](https://www.nconemap.gov/), a state project through the N.C. Geographic Information Coordinating Council to collect and publish property parcel information from all 100 counties.

Properties were removed from the count if their zoning, land use or building description did not align with [the U.S. Census Bureau definition of a single-family home](https://www.census.gov/construction/chars/definitions/#s). Companies with fewer than 100 properties in their portfolios were not included in the analysis.

The OneMap data was last accessed on April 20, although the property records may lag by several months depending on the county.

The reporting identified nearly 40,000 individual properties owned by subsidiaries of about 20 parent companies.

Szakonyi, who reviewed the N&O and Observer’s analysis, called the analysis the "best exercise I've ever seen trying to identify properties owned by large institutional investments."

The N&O and the Observer are making both the investor subsidiary list and the database of corporate investor-owned properties available publicly for all uses.

*The Pulitzer Center contributed to this project by awarding The Charlotte Observer and The News & Observer [a data journalism grant](https://pulitzercenter.org/grants-fellowships/opportunities-journalists/data-journalism-grants).*

## Data
The following files [can be downloaded](https://github.com/mcclatchy-southeast/security_for_sale/tree/main/data) from the `data` directory in this repo. File names are appended with a timestamp indicating when they were generated, in the format `YYYYMMDDHHMM`.

Use of this data is granted to researchers, policymakers and the public under [an MIT License](https://github.com/mcclatchy-southeast/security_for_sale/blob/main/LICENSE).

Please cite/credit/attribute all uses to: `The News & Observer/The Charlotte Observer` or `an analysis by The News & Observer and The Charlotte Observer`. And if our data makes it into your work, let us know!

Have questions? Spot an error in our data? Contact Tyler Dukes at [mtdukes@newsobserver.com](mailto:mtdukes@newsobserver.com).

### corporate_landlord_lookup
 A comma-separated value file containing the lookup table that ties subsidiaries (the buying entities listed on property records) with the associated parent company, based on property mailing address, corporate registration records and other sources. Wherever possible, this table also includes North Carolina corporate registration information. Subsidiaries are excluded from this list of their parent companies own fewer than 100 properties across the state.

### corporate_sfr_properties
A comma-separated value file containing selected data from the [NC OneMap parcel file](https://www.nconemap.gov/pages/parcels), joined against the corporate subsidiary lookup table to identify properties owned by large corporate landlords. Properties were excluded from this file if they're land and building use codes did not meet the [U.S. Census Bureau definition of single-family properties](https://www.census.gov/construction/chars/definitions/#s) (i.e. multi-family dwellings or commercial properties).

## Data dictionary/field layout

### corporate_landlord_lookup

| field|description|
|:--|:--|
| owner | owner name obtained from property records |
| investor_label_lvl1 | first-level label to denote whether the owner is a corporate landlord/institutional investor |
| investor_label_lvl2 | second-level label to specify the parent company tied to the property owner |
| sos_name | standardized subsidiary name matched to the N.C. Secretary of State's [corporation registration database](https://www.sosnc.gov/online_services/search/by_title/_Business_Registration) |
| sos_id | ID number provided by the corporation registration database |
| registry_url | direct link to the subsidiary's corporation registration page |

###  corporate_sfr_properties
Many of the fields here are drawn directly from the N.C. OneMap parcel file. For more on the field layout of that file, [consult its own data dictionary](https://nconemap.maps.arcgis.com/sharing/rest/content/items/5cdbfd254c7140108919a68f0113caba/data). 
| field|description|
|:--|:--|
| sf_id | unique ID generated by the N&O/Observer reporter team after importing N.C. OneMap data |
| parcel_identification1 | local (county) parcel number for the parcel record *Provided by N.C. OneMap as* `PARNO` |
| county | county name *Provided by N.C. OneMap as* `CNTYNAME` |
| owner_raw | primary surface owner name *Provided by N.C. OneMap as* `OWNNAME`|
| owner_clean | cleaned name of owner, removing extraneous spaces, all punctuation and common misspellings |
| sos_name | standardized subsidiary name matched to the N.C. Secretary of State's [corporation registration database](https://www.sosnc.gov/online_services/search/by_title/_Business_Registration) |
| investor_label_lvl2 | second-level label to specify the parent company tied to the property owner |
| mailing_address | generated field using the OneMap's `MAILADD`, `MUNIT`, `MCITY`, `MSTATE` and `MZIP` fields  |
| mailing_zip | mailing zip code *Provided by N.C. OneMap as* `MZIP`|
| site_address | full site address as a single field *Provided by N.C. OneMap as* `SITEADD` |
| site_city | site address city name *Provided by N.C. OneMap as* `SCITY` |
| site_zip | zip code of the site address; If maintained and available, this supports physical address delivery and the vehicle tax system. *Provided by N.C. OneMap as* `SZIP` |
| type_use1 | local assessment parcel use description of primary land use, such as residential, agriculture, forestry, commercial, etc; in some cases where this field was null for Cabarrus, Union, Mecklenburg, Iredell and Hoke counties N&O/Observer reporters matched parcels with corresponding type/use data from each county directly to improve accuracy *Provided by N.C. OneMap as* `PARUSEDESC` |
| type_use2 | code for the primary use of structure(s) or activity on a parcel such as single-family residential, retail, manufacturing, agricultural, etc *Provided by N.C. OneMap as* `PARUSEDSC2`|
| type_use_source | notes if the source of the type/use column was the NC OneMap or a match with original county data |
| deeded_acreage | record or recorded area as a numeric field in acres, formerly indicated as deed acres *Provided by N.C. OneMap as* `RECAREANO` |
| land_value | value of the land on the parcel in dollars *Provided by N.C. OneMap as* `LANDVAL` |
| total_value | total value of the parcel in dollars *Provided by N.C. OneMap as* `PARVAL` |
| year_built | year built of the primary building on the parcel *Provided by N.C. OneMap as* `STRUCTYEAR` |
| sale_date | date of the last sale if available, as a date field *Provided by N.C. OneMap as* `SALEDATE` |
| sos_id | ID number provided by the corporation registration database |
| registry_url | direct link to the subsidiary's corporation registration page |
| lat | latitude calculated from the centroid of the NC OneMap parcel |
| lng | longitude calculated from the centroid of the NC OneMap parcel |

## Interactives
Interactive motion graphics in the Security for Sale series were created by David Newcomb. [Read more about how he preprocessed the data to and created the maps here](https://github.com/mcclatchy/data-security-for-sale/tree/main).