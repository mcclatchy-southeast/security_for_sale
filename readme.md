
# Security for Sale

Following the collapse of the housing market in the Great Recession, a small contingent of hedge funds and private equity firms bought up scores of single-family homes as part of a new real estate investment strategy.

Instead of flipping these properties, investors held onto them, making money from rental payments and fees and growing equity as the value of the properties recovered. They also created rental-backed securities, a new financial instrument that sold bond holders the promise of future rental income.

Read our three-day series into how the growth of the single-family rental industry is affecting tenants, neighborhoods and communities in **Security for Sale** in one of our three partner publications:

 - [The News & Observer](http://www.newsobserver.com/securityforsale)
 - [The Charlotte Observer](http://www.charlotteobserver.com/securityforsale)
 - [The Herald Sun](http://www.heraldsun.com/securityforsale)

Have questions? Spot an error in our data? Contact Tyler Dukes at [mtdukes@newsobserver.com](mailto:mtdukes@newsobserver.com).

*Note: This repo will be updated periodically with new data and resources.*

## How we did this story
Tracking the single-family rental companies and their purchases is tricky.

Although there are just a handful of national corporations buying on a large scale in Charlotte and Triangle, they use a myriad of subsidiaries and holding companies to conduct their business. There's also variation – misspellings, mixed punctuation and the link – in how these subsidiaries are recorded in property records managed by each of the state's 100 counties.

"This has been such an opaque issue for decades now that we have really, really bad data flowing around in the public sphere about how active these types of investment funds are," David Szakonyi, an assistant professor of political science at Georgetown University and co-founder of the Anti-Corruption Data Collective.

So in the winter of 2021, reporters at The News & Observer and The Charlotte Observer set about creating the most authoritative dataset possible of investment buyers across the state – particularly the single-family homes that have long been key to middle-class American wealth.

Reporters first manually scoured property records in Wake and Mecklenburg counties to create a database of parent companies and their most common subsidiaries, which can often be linked by naming convention, corporate mailing address and company officials. They used that list to create a machine learning model to find other name variations.

Data from other researchers examining the growth of the single-family rental industry, including the UNC-Charlotte Urban Institute and Massachusetts Institute of Technology researcher Maya Abood, was used to add more names. North Carolina court data on eviction proceedings, state utility data and corporate registration data from the nonprofit OpenCorporates helped, too. The Anti-Corruption Data Collective supplied additional property transaction data through a research agreement with the real estate tech firm Zillow.

Almost all subsidiaries identified by the N&O and Observer's reporting were matched – either with statistical software or manually – to corporate registrations filed with the N.C. Secretary of State's Office to verify connections with their parent companies.

The list of investor subsidiaries was then matched using statistical software with property owner names recorded by the [North Carolina OneMap](https://www.nconemap.gov/), a state project through the N.C. Geographic Information Coordinating Council to collect and publish property parcel information from all 100 counties.

Properties were removed from the count if their zoning, land use or building description did not align with [the U.S. Census Bureau definition of a single-family home](https://www.census.gov/construction/chars/definitions/#s). Companies with fewer than 100 properties in their portfolios were not included in the analysis.

The OneMap data was last accessed on April 20, although the property records may lag by several months depending on the county.

The reporting identified nearly 40,000 individual properties owned by subsidiaries of about 20 parent companies.

Szakonyi, who reviewed the N&O and Observer’s analysis, called the analysis the "best exercise I've ever seen trying to identify properties owned by large institutional investments."

The N&O and the Observer are making both the investor subsidiary list and the database of corporate investor-owned properties available publicly for all uses.

*The Pulitzer Center contributed to this project by awarding The Charlotte Observer and The News & Observer [a data journalism grant](https://pulitzercenter.org/grants-fellowships/opportunities-journalists/data-journalism-grants).*

## Data

## Data dictionary/field layout

## Interactives
Interactive motion graphics in the Security for Sale series were created by David Newcomb. [Read more about how he preprocessed the data to and created the maps here](https://github.com/mcclatchy/data-security-for-sale/tree/main).