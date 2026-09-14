---
title: "Integrating Google Ads auto-tagging (gclid) campaign data into PBA"
excerpt: "Enrich PBA data with auto-tagging gclid campaign information by connecting your Google Ads account to AppsFlyer."
---
Connect your Google Ads account (1 or more) to your brand bundle. Google Ads campaign data improves dashboard analytics capabilities and further enriches raw data reports.

* If the **gclid** is present on a web visit URL, PBA gets the following data from Google using GCLID. Note! The GCLID solution is not officially supported by Google Ads, which may deprecate the parameter in the future.
* The integration enriches the following fields. Field availability depends on the PBA dashboard and raw data reports.
  * Campaign name and campaign ID
  * Adset name and adset ID
  * Ad group name and ad group ID
* The data provided by integration takes priority and overwrites campaign name data extracted from UTM fields. Campaign and campaign ID are available in raw data reports.
* If you have multiple Google Ads accounts, make sure that you connect the accounts that run campaigns bringing traffic to your website.

**Website Attribution dashboard with campaign hierarchy populated**

![PBAWebSite.png](https://files.readme.io/46004298b827d3f4eaa4adae9fb2a8676867e6b5dde44a7ff087fe1bda07f054-4403138621713.png)

Campaign and ad hierarchy data is available in dashboards and raw data as follows:

* **Dashboards**
  * **Website Attribution:** Campaign > Adset > Ad levels supported.
  * **Web-Assisted Installs:** Campaign level
* **Raw-data:**
  * **Web-to-App:** web_googleads_campaign_id, web_googleads_campaign_name

**To connect to Google Ads:**

1. In AppsFlyer, from the side menu, select **Settings** > **Brand Bundles**
2. Go to **Google Ads integration** tab.
3. Click **Connect account.** The Google Ads sign-in page opens.
4. Sign in to the Google Ads account. Complete the process to give AppsFlyer access.

**Manage Google Ads connections**

On the Google Ads integration page, the following actions are available:

* Delete connection
* Enable/disable the connection

### PBA—Google Ads status messages

| Status | Meaning | Remarks/action required |
| --- | --- | --- |
| Active | The connection is live and pulling data | N/A |
| Inactive | The connection was disabled manually | Enable the connection to begin pulling data again |
| Never synced | The setup is complete | The setup is complete. It may take up to 24 hours for AppsFlyer to get data from Google Ads for the first time. If the message persists for more than 24 hours contact AppsFlyer support. |
| No data | The connection was successful | Google Ads did not return any data to our query. Ensure that you connect all the relevant Google Ads accounts to PBA. |
| No response | We can't contact Google Ads servers | At present, we can't connect to the Google Ads servers. If the status persists for more than 24 hours contact AppsFlyer support. |
| Invalid credentials | AppsFlyer can't get the data as the credentials are not valid. | Ensure that the correct credentials are set in the Google Ads integration page. Try to connect again using the most recent credentials. If the problem persists contact AppsFlyer support. |
| General error | | If this status persists for more than 24 hours contact AppsFlyer support |