## Parameters requested for producs operations

Operation|Description|SP API required|MWS required
----|----|----|----
GetItemOffers|Marketplaceid|yes|yes
| |Condition|yes|yes
| |Asin|yes|yes
| |Customer type (customer/business)|no|n/a
GetPricing|Marketplaceid|yes|yes
| |Itemtype(Sku/asin)|yes|yes (Asin list)
| |SKU up to 20|no|n/a
| |Asin up to 20|no|n/a
| |Condition|no|no|
| |Offertype (B2C or B2B)|no|n/a
GetCompetitivepricing|Marketplaceid|yes|yes
| |Itemtype(Sku/asin)|yes|yes (Asin list)
| |SKU up to 20|no|n/a
| |Asin up to 20|no|n/a
| |Customer type (customer/business)|no|n/a
GetListingoffers|Marketplaceid|yes|yes
| |Condition|yes|yes
| |Seller SKU|yes|yes
| |Customer type (customer/business)|no|n/a


Missing from SP API products:
GetLowestOfferListingsForSKU
Returns pricing information for the lowest-price active offer listings for up to 20 products, based on SellerSKU.

Request parameters

Name|Required|
|---|---|
MarketplaceId	|Yes
SellerSKUList| Yes	Maximum: 20 SellerSKU values.
ItemCondition	|No	

GetLowestOfferListingsForASIN
Returns pricing information for the lowest-price active offer listings for up to 20 products, based on ASIN.

Name|Required|
|---|---|
MarketplaceId	|Yes
AsinList| Yes	Maximum: 20 Asin values.
ItemCondition	|No






