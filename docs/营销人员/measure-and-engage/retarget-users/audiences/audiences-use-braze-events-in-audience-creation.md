---
title: Audiences - Use Braze events in audience creation
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-17T09:55:26Z'
  edited_at: '2026-10-13T01:40:37Z'
  id: 4411130243217
  locale: zh-cn
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/zh-cn/articles/4411130243217
---
> **At a glance:** Send Braze message engagement events to AppsFlyer Audiences and use them to add precision to your audience definitions.

By setting up an incoming connection between your Braze account and AppsFlyer Audiences, you bring your Braze message engagement event data into Audiences. You can then use this data in <Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#规则组合说明">rulesets</Anchor> when defining audiences.

> 🚧 **Important**
>
> **Prerequisites**
>
> * Both the Braze and AppsFlyer SDKs must be integrated into your app.
> * You must subscribe to the **Currents** feature in Braze.

## Set up the Braze incoming connection

There are 3 main steps for setting up the Braze incoming connection:

1. [Set up the AppsFlyer SDK](/docs/audiences-use-braze-events-in-audience-creation#set-up-the-appsflyer-sdk)
2. [Create an incoming connection in AppsFlyer](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer)
3. [Create a Current in Braze](/docs/audiences-use-braze-events-in-audience-creation#create-a-current-in-braze)

<Accordion title="Set up the AppsFlyer SDK">

To create an incoming connection from Braze, the AppsFlyer SDK in your apps must be configured to pass each user's **Braze External ID** to AppsFlyer. You can do this using either:

* Braze External ID parameter
* CUID field

#### **Using a Braze External ID parameter**

You can configure a dedicated parameter to pass the Braze External ID to AppsFlyer using the `setPartnerData` function of the AppsFlyer SDK. Usage examples follow:

<Tabs>
<Tab title="Android">

```java
Map<String, Object> brazeData = new HashMap<>();
brazeData.put("external_user_id", "some-braze-external-id-value");
AppsFlyerLib.getInstance().setPartnerData("braze_int", brazeData);
```

</Tab>

<Tab title="iOS">

```objectivec
NSDictionary *brazeInfo = @{
@"external_user_id":@"some-braze-external-id-value"
};
[[AppsFlyerLib shared] setPartnerDataWithPartnerId:@"braze_int"
partnerInfo:brazeInfo];
```

</Tab>
</Tabs>

#### **Using the CUID field**

There is no need to configure a dedicated parameter for the Braze External ID if:

* You have configured the SDK to send AppsFlyer a <Anchor target="_blank" href="/marketers/zh/docs/customer-user-id-field-cuid">CUID</Anchor> for each user
* The CUID has the same value as the Braze External ID

In this case, you can simply select the **CUID option** as the SDK parameter when [creating your incoming Braze connection](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer).

</Accordion>

<Accordion title="Create an incoming Braze connection in AppsFlyer">

**Follow these steps to create an incoming connection in AppsFlyer:**

1. In AppsFlyer, from the side menu, select **Engage** > **Audiences**
2. In the Audiences page, go to **Connections > Incoming** **tab**.
3. Click the **New incoming connection** button.
4. Select Braze from the list of available partners.
5. Click the **Save** button to create the connection.  
   The **Connection credentials** dialog opens.
6. Copy the connection credentials to use when setting up the connection to AppsFlyer Audiences in the Braze platform:
   * Access key ID
   * Secret access key
   * Bucket name
   * Folder path
7. Select the SDK parameter you are using to send the Braze External ID:
   * Braze External ID
   * CUID

</Accordion>

<Accordion title="Create a Current in Braze">

**Follow these steps to create a Current in Braze:**

1. Go to the **Integration** section of the left-side menu bar.
2. Click **Currents.**
3. Click the **Create Current** button.
4. Select **Amazon S3 Data Export.**
5. In the **Create Currents Integration** section:
   1. Enter a name for the Current (for example, AppsFlyer Audiences).
   2. Enter the email of someone on your team that Braze will notify in case of issues with the credentials for the Current.
6. In the **Credentials** section:
   1. Keep the option for **AWS Secret Access Key** selected (this is the default value).
   2. Enter the credentials you copied from AppsFlyer in the appropriate fields.
   3. Keep the **Enable Encryption** option unchecked.
7. Under **General Settings**, keep **Include events from anonymous users** checked.
8. In the **Message Engagement Events** section, select the events you want Braze to send to AppsFlyer. See the list of supported events [below](/docs/audiences-use-braze-events-in-audience-creation#supported-events).
9. In the Customer Behavior and User Events section, keep the **Track Customer Behavior and User Events** option turned off.
10. Click the **Launch Current** button to save the configuration and start sending Braze message engagement events to Audiences.

#### supported events

> 📘 **Note**
>
> **Supported Braze events**
>
> * Subscription Group State Change
> * Email Click
> * Email Open
> * Email Send
> * Email Delivery
> * Email Mark as Spam
> * Email Unsubscribe
> * Email Bounce
> * Email Soft Bounce
> * Push Open
> * Push Send
> * Push Bounce
> * iOS Foreground Push
> * SMS/MMS Send

</Accordion>

## Using Braze data in Audiences

Once the Braze incoming connection is set up, the engagement events you've defined will appear as options in the <Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#ruleset-filters">ruleset filters</Anchor> for defining audiences.

<Image align="center" alt="audiences_braze_ruleset.png" src="https://files.readme.io/766a5ec25de3cf82c1411ce25864a5c8ce6c77ac338c20699e61be1c45ae3d98-33375723752337.png" />

**Note:** It takes approximately 24 hours for the Braze message engagement events to be available in AppsFlyer after you launch the current in Braze.

<div data-zendesk-anchors="h_01HKW0BS5H1ANWAJZTVBWDQHJH=set-up-the-braze-incoming-connection h_01HKW0BS5HGB2RYGWNXT1M163C=using-a-braze-external-id-parameter h_01HKW0BS5HQJZRR60VKBCWGHQB=using-the-cuid-field h_01HKW0BS5JM8A9XFVX22KWFE3H=supported-events h_01HKW0BS5JTZQ71HFE305ZT1CS=using-braze-data-in-audiences" />
