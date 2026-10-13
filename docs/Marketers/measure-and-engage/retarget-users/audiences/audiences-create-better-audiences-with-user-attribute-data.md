---
title: "Audiences - Create better audiences with user attribute data"
excerpt: "Enrich your ability to segment users into relevant groups by adding your data about their characteristics into Audiences."
x-zendesk:
  id: 360009775517
  url: https://support.appsflyer.com/hc/en-us/articles/360009775517-Audiences-Create-better-audiences-with-user-attribute-data
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Audiences
  section_id: 6551336428945
  position: 8
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-neama-benhabib, Marketers, Audience Segmentation]
  labels: [Advertisers, Premium, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2020-06-11T06:13:55Z'
  edited_at: '2026-10-05T06:49:12Z'
---
**At a glance:** Enrich your ability to segment users into relevant groups by adding your data about their characteristics into Audiences.

[![UserAttributionNavigationXL3_us-en.png](https://files.readme.io/d308c590f656a155845af5c181322a3876d2e4dd7df458f4899861954dbd4de7-33375683032465.png)](https://files.readme.io/d308c590f656a155845af5c181322a3876d2e4dd7df458f4899861954dbd4de7-33375683032465.png)

## About user attributes

User attributes, unlike event-based data, are general characteristics that your users share with you. They can be static, like gender, age, birthday, and country; or dynamic, like the user score in a game.

User attribute data is:

* Updated using CSV file import or JSON via API.
* Stored in a hashed form.
* Available for use in any audience ruleset

User attribute data is **not shared with advertising partners.**

User attributes are housed at either the app-level or account-level as described in this article. If using app-level attributes, the account user requires [app permission](/docs/user-management#background) to manage and use the attributes.

The following scenario provides a detailed explanation of user attributes.

### Scenario—app marketer requirements

You, the app marketer, are busy with the following:

* Maintaining 2 gaming apps: game\_a and game\_b.
* Launching game\_c
* Targeting current app users with these user attributes:
  * Favorite sport: Cricket
  * Current game score: 15 or more in one of the current games

The table contains user-attribute data from your CRM. Audience rulesets need access to this data.   
![UserAttributuesExample_us-en.png](https://files.readme.io/6f86d8659ef089ac82bb8401b4af650fbc590d2293ac93de30e6f9b4fc2ceb86-33375683035281.png)

**Use CRM data in rulesets**

In Audiences, create user attributes (favorite sport and game score). This gives ruleset access to CRM data.

#### Scenario user attributes

| Name | Format | Level |
| --- | --- | --- |
| Game score | **Number**: Lets you set rules like '*ScoreGameB is greater than 29'*. | **App-level**: User's score is recorded for each game played.<br /><br />Meaning: ScoreGameA, ScoreGameB. |
| Favorite sport | **String:** Lets you set rules like '*whose favorite sport is tennis'.*<br /><br />Note! Values are case-sensitive. | **Account-level**: User's favorite sport is the same regardless of the app.<br /><br />Note! A user can have only 1 value associated with account-level attributes. |

**User attributes in rulesets**

User attributes act as filters in Audiences rulesets. This example uses criteria (favorite sport and game score) set by the marketer.

[![UserAttributedExample.jpg](https://files.readme.io/296ab5e13abedd5f11c7d445ec9bf4a9b62295c18ad783228d6ccb9b631be74f-33375704836625.jpg)](https://files.readme.io/296ab5e13abedd5f11c7d445ec9bf4a9b62295c18ad783228d6ccb9b631be74f-33375704836625.jpg)

## Implement user attributes

Set up, add, manage, and delete user attributes.

### Set up

**Prerequisite**:

To manage app-level attributes, an account user must have app permission.

**To set up user attributes follow these procedures:**

1. [Add user attributes.](/docs/audiences-create-better-audiences-with-user-attribute-data#add)
2. [Do one of the following](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)
   * [Import user-attribute data by CSV.](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)
   * [Import user-attribute data by API.](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)
3. [Implement user attributes in rulesets.](/docs/audiences-guide#user-attributes)

### Add

**To add user attributes:**

1. In AppsFlyer, from the side menu, select **Engage** > **Audiences**.
2. Click the User Attributes tab.
3. Click **Add user attribute**.

   ![UserAttributeAdd.png](https://files.readme.io/6c7f25bb23d47e67aaef34264029daa9ab058f08e218a441ab9dde8240b0b384-33375683046033.png)
4. Complete the fields. Field characteristics are listed in the table that follows.
   * **Attribute name**
   * **Format**
   * **Level**
5. Click **Save**.

| Field | Characteristics |
| --- | --- |
| Attribute name | * English characters only<br />* No punctuation or special characters<br />* Same name cannot be used at both the app- and account-level<br />* Same name **can** be used at the app-level; for example, above scenario use of ScoreGameA and ScoreGameB |
| Format | * Text: Test if the attribute value **is** or **is not equal** to a specified rule value. Example: Is cricket or is not cricket.<br />* Number: Test if the attribute value is greater than, less than, or equal to a specified rule value. Example: Score greater than 15 |
| Level | * Account-level: An attribute has no connection to the app.  <br />  Example: gender, favorite sport<br />* App-level: An attribute is app-related. Select the apps associated with the attribute. |

**User attribute fields**

### Manage

To manage user attributes, go to **Audiences** > **User attributes** tab.

[![AudiencesUserAttributes_us-en.png](https://files.readme.io/6baee58e9cd9b2b39bc8facf0af72abe71a4bd1cd2f844f49467fbaeb7252cd7-33375704844049.png)](https://files.readme.io/6baee58e9cd9b2b39bc8facf0af72abe71a4bd1cd2f844f49467fbaeb7252cd7-33375704844049.png)

| Function | Description |
| --- | --- |
| Search and filter | By attribute name, app name, and attribute level. |
| Sort by | Click a column header to sort table rows. |
| Import data | * [Import data by CSV](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)<br />* [Import data by API](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api) |
| Change API import key | **To change the API import key:**<br /><br />1. Click **Import data**.<br />2. Select **API**.<br />3. Click **Refresh import key***.*<br /><br />**Note!** If scripts have embedded keys, make sure to update them with the new key. |

Manage user attributes

### Delete

![AppsFlyerAdmin_us-en.png](https://files.readme.io/167bf558ccdf30670d9dc4b6ea824318a886cba7ac2fdf928010e8a0c9d35d4f-33375683048849.png) Only an admin user can delete an attribute.

**To delete an attribute that is part of a ruleset:**

1. Remove the attribute from the ruleset.
2. Delete the attribute.

## Import data

### Import field specifications

| Field | Content | Format | Add data  <br />by CSV | Remove data by CSV |
| --- | --- | --- | --- | --- |
| device\_id | Includes 1 of these user IDs:<br /><br />* IDFA<br />* GAID | Text | Either **device\_id** or **customer\_id** is mandatory | Either **device\_id** or **customer\_id** is mandatory<br /><br />To remove existing data, don't send |
| customer\_id | [Customer user ID](/docs/customer-user-id-field-cuid) | Text | Either **device\_id** or **customer\_id** is mandatory | Either **device\_id** or **customer\_id** is mandatory<br /><br />To remove existing data, don't send |
| app\_id | **App-level attribute:** App ID as it displays in the dashboard.<br /><br />For iOS apps, include the prefix *ID*.<br /><br />**Account-level attribute**: Always populate with * | Text | Mandatory | Mandatory |
| attribute\_key | User-attribute name, exactly as it displays on the user-attributes tab. | Text | Mandatory | Mandatory |
| attribute\_value | Assigned value<br /><br />[*See limitations](/docs/audiences-create-better-audiences-with-user-attribute-data#limitations) | Text or number | Mandatory | Don't send |

User-attribute field list

### Import data by CSV

User-attribute data is added or removed via a CSV file. The figure and example CSV file that follows, match the scenario describing the feature in this article.

[User-attribute-example.csv](https://support.appsflyer.com/hc/article_attachments/360012423857)

![FileForAttributes.png](https://files.readme.io/2a9075ab7f900648aeebe3b5fca807c6b931ba5295f35708ee6c48d345f681b9-33375704847633.png)

**CSV file requirements**

* No header row
* Contains all the columns listed in the preceding table.

> 📘 **Note**
>
> This CSV format is for importing user attribute data. If you're importing audience segments instead, see [Import audience segments from internal systems](/docs/audiences-import-audience-segments-from-internal-systems), which uses a different CSV format that requires a header row.

**To import a CSV file:**

1. Go to **Audiences** > **User attributes** tab.
2. Click **Import data**.
3. Select **CSV**.
4. Selecteither:
   * **Add data**
   * **Remove data**
5. Choose a CSV file to import.
6. Click **Upload**; an upload status message will appear.

**Note:** When importing user attributes, all known devices associated with a customer ID are also assigned the attribute. For example, if a user imported 10 devices (by customer\_id) to attribute “Game score”, and one of the customer\_ids is associated with 2 devices (i.e. 2 GAIDs with the same CUID), then this import will contain 11 user attribute records.

### Import data by API

This import method requires a request URL and JSON with user-attribute data.

1. In the dashboard, get the prepared API request calls and JSON template.
2. Populate the JSON template with your data according to the [field specifications](/docs/audiences-create-better-audiences-with-user-attribute-data#import-field-specifications).

**To generate the API request URL and JSON template:**

1. Click **Import data.**
2. Select **API.**
3. Select an action:  
   * Update user-attributes: Overwrite or add.
   * Remove user-attributes.
   * Remove user data: Removes all data relating to a specific user. User is identified by their AppsFlyer ID.
   * Remove app data: Removes all data at the app level.
4. Copy the generated API request URL.
5. Copy the generated API request body.
6. Prepare the JSON (with its user-attribute data) using the specified JSON format. For account-level attributes set "app\_ids": ["*"]
7. Prepare the API call based on the URL and request body.
8. Send the request programmatically.

**Example request and JSON**

```
https://hq1.appsflyer.com/api/user-attributes-import-api/set-user-data
{
  "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
  "attributes_values": [
    {
      "device_id": "",
      "customer_id": "",
      "app_ids": [],
      "attributes": [
        {
          "attribute_key": "",
          "attribute_value": ""
        }
      ]
    }
  ]
}
```

> 📘 **Note**
>
> You must authenticate the request using an Authorization Bearer Header with an [API token V2.0](/docs/managing-appsflyer-tokens#v20-token%E2%80%94advertiser-apis)

**Example with multiple device IDs, attribute keys, and attribute values**

```
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "2222222",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 5
                }
                ,
                {
                    "attribute_key": "favorite_sport",
                    "attribute_value": "cricket"
                }
            ]
        }
        ,
        {
            "device_id": "555555-d1d1-d1d1-555-fffffffff",
            "customer_id": "111111",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "order",
                    "attribute_value": 7
                }
                ,
                {
                    "attribute_key": "number",
                    "attribute_value": 8
                }
            ]
        }]
}
```

**Example with a single device ID and multiple attribute keys and values**

```
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "12345678",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 90
                }
                ,
                {
                    "attribute_key": "favorite-sport",
                    "attribute_value": "cricket"
                }
                ,
                {
                    "attribute_key": "orderNumber",
                    "attribute_value": 93
                }
                ,
                {
                    "attribute_key": "netPromoterScore",
                    "attribute_value": 94
                }
            ]
        }
    ]
}
```

**Note:** When importing user attributes, all known devices associated with a customer ID are also assigned the attribute. For example, if a user imported 10 devices (by customer\_id) to attribute “Game score”, and one of the customer\_ids is associated with 2 devices (i.e. 2 GAIDs with the same CUID), then this import will contain 11 user attribute records. CSV import limitations

### Limitations

#### General limitations

* Only integer (whole) numbers are supported in CSV/API import data. Float type (decimal) numbers are not supported. **Example:** A "score" attribute value can be 90, but not 90.5.
* User-attribute data can't be printed or downloaded.
* #### Attribute value limitations:

  * No commas, dots, or other special characters inside attribute values.
  * There is a length limitation of 40 characters for a string attribute value.
  * Attribute values can't start with 0.

#### API import limitations

* Maximum 350 API requests per minute, 10K devices for flat payload (10K devices with one attribute, 5K devices with 2 attributes, etc.)
* Both `device_id` and `customer_id`keys are mandatory for every import call. If you want to import attributes with only one of these identifiers, the call has to include the “header” of the other identifier with an empty string. For example, if you want to import attributes per `device_id` and no `customer_id`, the call should look like this:

```
"attributes_values": [
{
"device_id": "39e123.......",
"customer_id": "",
```

#### CSV import limitations

* When adding user attribute values, there is a maximum of 10 million rows per CSV file.