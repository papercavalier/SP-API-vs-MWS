## Rate limits

The API Gateway runs the API rate limit action to enforce the rate limit and burst limit schemes that are defined for the target API or operation.

Rate limit scheme
A rate limit scheme controls the rate of the API transactions. A rate limit scheme defines the maximum rate that is allowed in a specified time interval and the actions to take when the limit is exceeded.
Burst limit scheme
A burst limit scheme also defines the maximum rate that is allowed in a usually shorter interval. A burst limit scheme helps prevent usage spikes within a short time span that might damage infrastructure. The burst limit takes higher priority than the rate limit, when a message arrives within an interval, the message is first checked against the burst limit scheme. When the burst limit is exceeded, the request is rejected.
For example, an API has a rate limit of 10 calls/minute and a burst limit of 3 calls/second. When the third call arrives within the first second of a 1-minute interval, the burst limit is exceeded and the call is rejected, although the 10 calls/minute rate limit is not yet reached.

Operation |SP API|MWS
----|----|---
GetItemOffers|Rate = 5 Burst = 10|Rate = 5 items per second, 10 requests max, ~~200 requests per hour~~ 
GetPricing| Rate = 10 Burst = 20, up to 20 asins| 10 items per seconds, 20 requests max, 36000 per hour
GetCompetitivePricing|Rate = 10 Burst = 20, up to 20 asins|10 items every second, 20 requests max, 36000 per hour
GetListingOffers|Rate = 5 Burst = 10|5 items per second, 10 requests max, 200 requests per hour

### Missing important operations in SP API such as 

GetLowestOfferListingsForASIN
Returns pricing information for the lowest-price active offer listings for up to 20 products, based on ASIN where condition is optional

Throttling

|Maximum request quota|	Restore rate|	Hourly request quota|
---|---|---
20 requests	|10 items every second|	36000 requests per hour

### GetLowestOfferListingsForSKU
Returns pricing information for the lowest-price active offer listings for up to 20 products, based on SellerSKU

Throttling
|Maximum request quota|	Restore rate	|Hourly request quota|
|---|---|---|
20 requests	|10 items every second	|36000 requests per hour
