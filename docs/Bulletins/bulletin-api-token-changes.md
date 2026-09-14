---
title: "Bulletin: API token changes"
excerpt: "Important update regarding the deprecation of API V1 tokens and the transition to secure JWT-based API V2 tokens."
---
To provide a more secure and reliable experience for API usage, the API V1 token, which was included in the API URLs, was deprecated in favor of the API V2 token, which is a JWT-based token that is passed in the header for bearer authorization. API V1 token and the APIs that use them are no longer available as of September 18, 2023.

### Effective date
September 18, 2023

### Prerequisites
Only an admin can [retrieve the API V2 token](https://support.appsflyer.com/hc/articles/360004562377#retrieving-api-tokens) from the AppsFlyer dashboard.

### Who needs to update the API token?
Both advertisers and agencies who are still using API token V1 need to update their tokens.

### How to find API V1 tokens
Use the [Audit log](https://support.appsflyer.com/hc/articles/360007971697) to filter out any API V1 tokens still in use. You can then download the data to a CSV file:
1. Go to the [Audit log dashboard](https://hq1.appsflyer.com/audit-reader/dashboard).
2. Type "API Token V1" in the search bar.
3. In the **Service** filter, select only **API calls**, and filter the results.
4. Click the Download icon from the top-right of the page.
   
Your CSV file is downloaded and includes your app ID, the service used, and the API call URL.

### Action required
**Update the following APIs for the API V2 token:**
1. Go to the [API token page](https://hq1.appsflyer.com/account/api-tokens). 
2. Under API token V2.0, click the **Copy to clipboard** icon.
3. For each of the following APIs:
   - [Master API V2](https://dev.appsflyer.com/hc/reference/master_api_get)
   - [Aggregate Pull API V2](https://dev.appsflyer.com/hc/reference/overview-11)
   - [Raw Data Pull API V2](https://dev.appsflyer.com/hc/reference/overview-5)
   1. Replace the API V1 URL with the URL in the above documentation.
   2. Paste the token you copied into the Bearer authentication header.
      
      <Image src="https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png" alt="token_v2_bearer.png" />
   3. For the **OpenDSR API**, paste the token into the request bearer header: 
      
      `'Authorization': 'Bearer %AuthTokenV2%'`

### About the API tokens
**Learn more about the API tokens:**
- [Managing API tokens](https://support.appsflyer.com/hc/articles/360004562377-Managing-API-tokens)
- [Master API](https://support.appsflyer.com/hc/articles/213223166)
- [Aggregate Pull API](https://support.appsflyer.com/hc/articles/207034346)
- [Raw data](https://support.appsflyer.com/hc/articles/360007530258)
- [OpenDSR API](https://support.appsflyer.com/hc/articles/11332840660625#gdpr-request-format)