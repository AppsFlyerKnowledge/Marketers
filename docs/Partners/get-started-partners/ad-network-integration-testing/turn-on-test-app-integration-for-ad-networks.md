---
title: "Turn on test app integration for ad networks"
excerpt: "Learn how ad networks can activate integration and grant permissions for iOS and Android test apps in AppsFlyer."
---
Ad networks performing integration testing must turn on app integration (activation).

## Test apps for ad networks (iOS and Android)

Ad networks after setting up integration and postbacks must test integration using AppsFlyer test apps. Before testing, the ad network must activate the app integration and enable additional ad network permissions as needed. The activation is performed once per app.

| Test app type | App name or ID |
| --- | --- |
| [Android](/docs/getting-started-onboarding-guide-for-ad-networks#part-2-test-using-advertiser-apps) | com.appsflyer.adNetworkTest |
| [iOS](/docs/ios-integration-testing-for-ad-networks) | id1543229303 |
| [SKAdNetwork](/docs/skan-integration-guide-for-ad-networks) | - id888707085<br />- id888707086<br />- id888707087 |

### Activation procedure

Use the procedure that follows to activate the integration for a given test app. Perform the procedure once per app.

**To activate integration and grant permissions to a test app**:

1. In AppsFlyer, select a test app from those listed in the previous table.
2. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations**.
3. Select your ad network.
4. **To activate integration with the app**:
   1. Go to the **Integration** tab.
   2. Turn on **Activate Partner**.
   3. Click **Save integration**.
5. **To grant permissions**:
   1. Go to the **Permissions** tab.
   2. Turn on **Configure integration**.
   3. Turn on **Configure in-app event postbacks.**
   4. Click **Save permissions**.