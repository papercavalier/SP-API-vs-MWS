Dear Sirs,

We are contacting your team to provide feedback regarding the Pricing Functions of the New Seller Partner API as requested by your team on the MWS API deprecation announcement page. 

https://sellercentral.amazon.com/forums/t/important-notice-amazon-mws-products-section-and-selling-partner-catalog-items-v0-operations-to-be-deprecated-on-march-31-2022/862895

For the last month, we have conducted a thorough analysis of the new operations and have concluded that under the current specifications they will prove to be greatly detrimental to our ability to continue doing business as we are under the MWS Products API. 
Through the analysis below, we will present our user case, describe the restrictions in the new coming SP-API operations and provide suggestions of how those can be improved to minimise disruption and enhance our experience.

User Profile:
Paper Cavalier has been a seller on the Amazon platform for over 10 years. Our company sells books in all conditions.

 The underlying characteristic of this product category is a vast array of EANS to which sellers can carry in their inventories by virtue of sources such as distributors. As a reference only in the English language there are about 16 million titles published with ISBNs codes.  When considering the used sub-conditions, Books can be classified as a long tail which often describes a relatively low number of sales across a large number of products. The result of this is that the Inventory sizes of booksellers can be larger than in other product categories.

Our company develops tools in-house to integrate the MWS and SP-API we would be therefore categorised as Private Developers.

NEEDS:

Market analysis and listing decision making: Our company uses the MWS API to scout marketplaces and decide if it is worth listing products or not based on availability and price. 
Our goal is to minimise listing creations in crowded marketplaces or in marketplaces where we cannot be price competitive. This optimisation is necessary also since Amazon:
Charges sellers per listing created over certain limits on some marketplaces.
Amazon has listing creation quotas that we want to respect.

The main MWS API operation currently being used is the: GetLowestOfferListingsForASIN

Pricing: Our company uses the MWS API for reference pricing that allows us to create offers at the best prices without the need to use paid services such as Amazon SQS. (Subscriptions API)

Price trend analysis: Our company uses the MWS API to analyse price fluctuation with the goal of creating more competitive offerings for the benefit of Amazon’s customers.

Analysis Summary:
In order to understand the differences between the MWS Products API operation being used 
“GetLowestOfferListingsForASIN” and its corresponding one of the SP-API “GetItemOffers” we selected an ASIN (1740597419) for a book and compared responses qualitatively and in terms of throughput rates.

QUALITATIVE NOTES:

Qualitatively we can confirm the new SP-API “GetItemOffers” operation is superior in the range of results to the MWS-API “GetLowestOfferListingsForASIN”. 

SP-API vs MWS-API responses comparison for ASIN 1740597419 can be found in the link below:
https://drive.google.com/drive/folders/1vFxCFQVappmcGM1VelR5viS_tbD7N46q?usp=sharing

Short-comings:

The biggest shortcoming of the SP-API “GetItemOffers” is the mandatory requirement to specify the “condition” of an ASIN when creating the query. This situation is detrimental to product categories such as books where the catalogue depth contains the biggest a greater ratio of USED to NEW products constituting the vast majority of listings.

Improvement Suggestion: Eliminate the requirement to specify conditions from the SP-API  “GetItemOffers” operation.

THROUGHPUT ANALYSIS:

Perhaps the biggest shortcoming of the SP-API versus the MW Products API is the throughput returned by the new system for the pricing operation GetItemOffers.

Response throughput of the GetItemOffers operation is affected by the following factors:
1) Inferior rates: 
SP-API GetItemOffers: 5 requests per second (18000 per hour) vs MWS Products API GetLowestOfferListingsForASIN: 10 requests per second (36000 per hour)
2)SP-API GetItemOffers operation mandatory condition requirement:
This forces 2 requests instead of 1 to cover all conditions for a single ASIN which is relatively worse than the MWS API “GetLowestOfferListingsForASIN” operation.

Improvement Suggestion: 
Increase SP-API SP-API GetItemOffers from 5 to 10 requests per second to match the basic throughput of the MWS’s API GetLowestOfferListingsForASIN operation.
Eliminate the requirement to specify conditions from the SP-API  “GetItemOffers” operation.

PARTNER SPECIFIC RATE LIMITS:
In the Usage Plan section specific to the SP-API getItemOffers operations the documentation mentions there will be Selling Partner Specific Rates and Bursts. 

Link: https://github.com/amzn/selling-partner-api-docs/blob/main/references/product-pricing-api/productPricingV0.md#getitemoffers

We would like to understand how the application process will be handled regarding this possibility. Our company currently enjoys a preferential TPS in many accounts under the MWS API and we would like to extend or improve these rates once the migration to the new system SP API occurs.

FINAL COMMENT

We understand that the changes proposed will from March 31, 2022 impact third party developers as opposed to Private Sellers initially. We are however eager to address this matter as early as possible to request improvements that can bring us to the same or a better position than that previous of the current MWS API.

We thank you for the opportunity to provide you with feedback and the open communication approach your team is offering through Amazon’s Github site.

Should you have any questions please do not hesitate to contact us.

Sincerely,

Aitor Uria Saporiti
Director 
Paper Cavalier
aitor.uria@papercavalier.com
+44 770 912 0993

