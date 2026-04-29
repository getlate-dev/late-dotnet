# Zernio.Model.BoostPostRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**PostId** | **string** | Zernio post ID (provide this or platformPostId) | [optional] 
**PlatformPostId** | **string** | Platform post ID (alternative to postId) | [optional] 
**AccountId** | **string** | Social account ID | 
**AdAccountId** | **string** | Platform ad account ID | 
**Name** | **string** |  | 
**Goal** | **string** | Available goals vary by platform. Meta (Facebook/Instagram) and TikTok support all 7. LinkedIn supports all except app_promotion. Twitter/X supports engagement, traffic, awareness, video_views, app_promotion. Pinterest and Google Ads support only engagement, traffic, awareness, video_views. | 
**Budget** | [**BoostPostRequestBudget**](BoostPostRequestBudget.md) |  | 
**Currency** | **string** |  | [optional] 
**Schedule** | [**BoostPostRequestSchedule**](BoostPostRequestSchedule.md) |  | [optional] 
**Targeting** | [**BoostPostRequestTargeting**](BoostPostRequestTargeting.md) |  | [optional] 
**BidStrategy** | **BidStrategy** | Meta bid strategy applied to the ad set. On TikTok, mapped to &#x60;bid_type&#x60; / &#x60;bid_price&#x60; / &#x60;deep_bid_type&#x60; automatically.  | [optional] 
**BidAmount** | **decimal** | Bid cap in WHOLE currency units (USD: 5 &#x3D; $5.00; JPY: 100 &#x3D; ¥100). Required when &#x60;bidStrategy&#x60; is &#x60;LOWEST_COST_WITH_BID_CAP&#x60; or &#x60;COST_CAP&#x60;. Backward-compat: providing &#x60;bidAmount&#x60; without &#x60;bidStrategy&#x60; is treated as &#x60;LOWEST_COST_WITH_BID_CAP&#x60;.  | [optional] 
**RoasAverageFloor** | **decimal** | Minimum ROAS as a decimal multiplier (e.g. 2.0 &#x3D; 2.0x ROAS). Required when &#x60;bidStrategy&#x60; is &#x60;LOWEST_COST_WITH_MIN_ROAS&#x60;. Sent to Meta as &#x60;bid_constraints.roas_average_floor&#x60; × 10000 (Meta uses fixed-point integers).  | [optional] 
**Tracking** | [**BoostPostRequestTracking**](BoostPostRequestTracking.md) |  | [optional] 
**SpecialAdCategories** | **List&lt;BoostPostRequest.SpecialAdCategoriesEnum&gt;** | Meta only. Required for housing, employment, credit, or political ads. | [optional] 
**LinkUrl** | **string** | TikTok-only. Custom destination URL for the Spark Ad. Without this, TikTok Spark Ads have no clickable destination — required for traffic / conversion objectives. Maps to &#x60;landing_page_url&#x60; on the creative entry of /v2/ad/create/ (TikTok SDK &#x60;AdcreateCreatives.landing_page_url&#x60;). Ignored on Meta / LinkedIn / Pinterest / X / Google (those infer the destination from the boosted post).  | [optional] 
**CallToAction** | **string** | TikTok-only. Call-to-action button label on the Spark Ad creative (e.g. &#x60;LEARN_MORE&#x60;, &#x60;SHOP_NOW&#x60;, &#x60;DOWNLOAD_NOW&#x60;, &#x60;SIGN_UP&#x60;, &#x60;WATCH_NOW&#x60;). Maps to &#x60;call_to_action&#x60; on the creative entry of /v2/ad/create/. Pass-through — the platform validates the value. See TikTok&#39;s \&quot;Enumeration - Call-to-Action\&quot; reference for the full list.  | [optional] 
**DsaBeneficiary** | **string** | Name of the legal entity benefiting from the ad. Required by Meta when targeting EU users (DSA Article 26). Not enforced at schema level; enforced server-side when targeting intersects EU member states.  | [optional] 
**DsaPayor** | **string** | Name of the legal entity paying for the ad. Required by Meta when targeting EU users (DSA Article 26). Note Meta API spelling: dsa_payor (not dsa_payer).  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

