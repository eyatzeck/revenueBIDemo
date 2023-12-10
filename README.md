# revenueBIDemo
Sample tableau dashboard

Most of the work for the dashboard is done in Tableau, but this repo stores the base data and supporting code where needed.

Initial data notes:

Sales pipeline of completed and projected deals, one row per deal (not a transcript of all stages for all deals).  345 total records.

__Data dictionary:__
 * *account_name* - the customer.  "Strickland Propane, Global Phone Network,"

* *deal_name* -- code name for deal.  May be named after the customer, e.g. "Strickland Propane 1" and "Strickland Propane 2" -- not always logical, probably as the result of data masking for the exercise.  Hornet 1, 2, 3, and 4 are not in chronological order of expected close date.

* *sales_rep* -- who is in charge of the deal?

* *close_date* -- target or actual close date for the deal.  All values are in 2014, and the series of deals within each account for the year follows a logical sequence (Hornet seems to have lost some deals but now they are trying again, with those rows labeled "new customer.")

* *stage* -- which stage the deal is in.  Valid values and count of deals in each stage

| Stage  |Count of deals   |
|---|---|
|15% = Prospect|113|
|50% = Engaged|98|
|70% = In Negotiation|21|
|90% = Signature Stage|8|
|Closed Lost|62|
|Closed Won|43|	
|Grand Total|345|

* *bookings* -- a number in six figures representing something quantitative related to the deal.

* *service*-- name of service being sold, e.g. "residential EE" or "web engagement"  Five records are missing the service value.  Need to ask a question about that.  Valid values:

|Service|Count deals|
|---|---|
|Behavioral DR|17|
|Commercial EE|23|
|Competitive Markets|49|
|Mobile|7|
|Residential EE|177|
|Thermostats|24|
|Web Engagement|43|
|(blank)|5|

* *region* -- geographical subdivision of the company - e.g. Hornet Annuals has US East and US Midwest regions with separate associated sales attempts.  Valid values:  APAC, EMEA, LatAm, US East, US Midwest, US South, US West

* *customer_type* -- They have a column entitled "customer type" which seem to be about the status of the customer/region/service combination.  One customer may have multiple customer types.  Hornet Annuals is an example of a company that has multiple regions and multiple services, with different customer types associated.  Valid values are:   Expansion, New Customer, Renewal Only

There is only one record per deal, so it isn't a transcript of every stage and how long it took to get there.

All close dates are in 2014, presumably with the closed ones in the past and the open ones in the future