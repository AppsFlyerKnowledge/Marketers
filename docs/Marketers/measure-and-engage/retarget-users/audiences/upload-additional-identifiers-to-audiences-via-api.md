---
title: Upload additional identifiers to Audiences via API
metadata:
  keywords:
    - Advertisers
    - Developers
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
  created_at: '2021-11-22T14:05:51Z'
  edited_at: '2026-10-05T06:59:12Z'
  id: 4411552670993
  locale: en-us
  section: Audiences
  section_id: 6551336428945
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4411552670993-Upload-additional-identifiers-to-Audiences-via-API
---
> **At a glance:** Use the Audiences Additional Identifiers API to bulk upload user identifiers from your internal systems (such as BI and CRM) to AppsFlyer Audiences, enabling broader audience communication to relevant partners based on these identifiers.

## About the API

The Audiences Additional Identifiers API can be used to add the following user identifiers from your internal systems to AppsFlyer Audiences:

* Up to 2 hashed email addresses
* Hashed telephone number
* Hashed E164 telephone number

You can then choose to send these identifiers to your Audiences partners (subject to your <Anchor target="_blank" href="/marketers/docs/audiences-user-identifier-policy">account-level user identifier policy</Anchor>), allowing them to more accurately identify your target audiences. Note that not all advertising partners support all identifiers.

### When should I use this API?

This API was designed to be used when you want to upload a large volume of identifier data. Typically, this means data collected over time (for example, hashed emails collected from all users of an app over the last 12 months). For real-time, individual updates of identifiers from specific devices, <Anchor target="_blank" href="/marketers/docs/audiences-configure-additional-identifiers-for-partner-audience-creation">configure additional identifiers</Anchor> in the AppsFlyer SDK or S2S-mobile API.

> 🚧 **Important!**
>
> **Encryption:** All additional identifier values **must** be encrypted with SHA256 hashing. Unencrypted identifiers will not be processed.
>
> **Timing:** To ensure accurate matching of identifiers, the Audiences Additional Identifiers API can be used as soon as **the day following** the reporting of key identifiers through the AppsFlyer SDK (UTC). For example, key identifiers reported on 3-January-2022 (UTC) can be updated through this API on 4-January-2022 (UTC) or later.

## Actions

* [Add/modify identifiers](/docs/upload-additional-identifiers-to-audiences-via-api#addmodify-identifiers-put)
* [Remove identifiers](/docs/upload-additional-identifiers-to-audiences-via-api#remove-identifiers-delete)

## Authentication

The request must include an HTTP header containing your account's <Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens">AppsFlyer V2.0 API token</Anchor>. Ask your account admin to obtain this token from the AppsFlyer dashboard.

## API Specifications and sample code

<div id="addmodify-identifiers-put" />

<Accordion title="Add/modify identifiers (PUT)">

<span id="01ECF4ZD0T03JBV8DDH25MM01W"></span>**API request URL**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| Parameter | Description | Mandatory |
| --- | --- | --- |
| `{app-id}` | App ID of the app from which the identifiers were collected (as it appears in the AppsFlyer dashboard) | Yes |

<span id="01ECF4ZD0TWPH3DXV2YKN7G9B0"></span>**API request body**

```json
{
  "key_type": "<key_type>",
  "action": "add",
  "data": [
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    },
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    }
  ]
}
```

| Parameter | Description | Mandatory |
| --- | --- | --- |
| `{key_type}` | The identifier used as the unique value to represent the user in each data row of the request.<br /><br />The value specified here applies to every row in the request.<br /><br />Possible values:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_id</li><li>imei</li><li>oaid</li></ul> | Yes |
| `{action}` | "add" | No<br /><br />Default value: "add" |
| `{key_value}` | Valid identifier value for the key\_type specified | Yes |
| \{identifiers\} | Object containing the names and values of the identifiers to add:<ul><li>\{hashed\_emails\}</li><li>\{phone\_number\_sha256\}</li><li>\{phone\_number\_e164\_sha256\}</li></ul> | Yes<ul><li>Must include a value for at least 1 of these 3 identifiers</li></ul> |
| `{hashed_emails}` | An array of up to 2 hashed email addresses<br /><br />Format:<ul><li>Lowercase</li><li>No white spaces</li><li>SHA256 hashed</li></ul>Example value before hashing: name@domain.com | No |
| `{phone_number_sha256}` | Phone number (see note below)<br /><br />Format:<ul><li>No symbols, letters, or leading zeroes</li><li>Include country code</li><li>SHA256 hashed</li></ul>Example value before hashing:<br /><br />442070313000 | No |
| `{phone_number_e164_sha256}` | Phone number in E164 format (see note below)<br /><br />Format<ul><li>E164 phone number</li><li>SHA256 hashed</li></ul>Example value before hashing:<br /><br />+442070313000 | No |

> 📘 **Notes**
>
> * Different advertising partners support different phone number formats. So, if you choose to add a phone number, sending both identifiers is recommended: *phone\_number\_sha256* and *phone\_number\_e164\_sha256*.
> * `customer_user_id` is the same identifier referred to elsewhere in this section as CUID (Customer User ID). When `key_type` is `customer_user_id`, use the account's CUID value as the `key_value`. See <Anchor target="_blank" href="/marketers/docs/audiences-user-identifier-policy">Audiences user identifier policy</Anchor> for more on this and other supported identifiers.

**Restrictions**

The following restrictions apply to the **Add/modify identifiers** request:

* Previously existing values (if any) will be overwritten by values sent in the request.
* The `{data}` object can include a maximum of 4,000 rows (key\_values) per request.

**Sample request to add identifiers**

```json
HTTP PUT
body:
{
  "key_type": "idfv",
  "action": "add",
  "data": [
    {
      "key_value": "CDDA802e-AAAA-BBBB-CCCC-DDDDDDDDDDDD",
      "identifiers": {
        "hashed_emails": [
          "34d31be18022626de6b311d6a76e791176d2691b6eef406f524d8f56364c187a",
          "d8c2aec999baad2464e521873ee4465caaf7ff6db8c8b4a25b09ca07694e4dee"
        ],
        "phone_number_sha256": "6c91c4c640f6ef0162833260db4f13dec0df2b683092f4dba7e874bef1acea37",
        "phone_number_e164_sha256": "f3d7e96c73fb0de1b66acfce541d7af758fbd4f3fa3af0ea4e10110000d3625e"
      }
    }
  ]
}
```

</Accordion>

<div id="remove-identifiers-delete" />

<Accordion title="Remove identifiers (PUT)">

**API request URL**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| Parameter | Description | Mandatory |
| --- | --- | --- |
| `{app-id}` | App ID of the app from which the identifiers were collected (as it appears in the AppsFlyer dashboard) | Yes |

**API request body**

```json
{
  "key_type": "<key_type>",
  "action": "remove",
  "data": [
    {
      "key_value": "<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    },
    {
      "key_value": "<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

| Parameter | Description | Mandatory |
| --- | --- | --- |
| `{key_type}` | The identifier used as the unique value to represent the user in each data row of the request.<br /><br />The value specified here applies to every row in the request.<br /><br />Possible values:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_id</li><li>imei</li><li>oaid</li></ul> | Yes |
| `{key_value}` | Valid identifier value for the key\_type specified | Yes |
| `{action}` | "remove" | No<br /><br />Default value: "add" |
| \{identifiers\} | An array containing the names of the identifiers for which values should be deleted:<ul><li>\{hashed\_emails\}</li><li>\{phone\_number\_sha256\}</li><li>\{phone\_number\_e164\_sha256\}</li></ul> | Yes<ul><li>Must include at least 1 of these 3 identifiers</li></ul> |

**Restrictions**

The `{data}` object can include a maximum of 4,000 rows (key\_values) per request.

**Sample request to remove identifiers**

```json
HTTP PUT
body:
{
  "key_type": "gaid",
  "action": "remove",
  "data": [
    {
      "key_value": "cdda802e-aaaa-bbbb-cccc-dddddddddddd",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

</Accordion>

<div id="responses" />

<Accordion title="Responses">

| Code | Message | Description |
| --- | --- | --- |
| 202 | Accepted for processing | Request will be applied during the next processing window. |
| 400 | Request body must have a valid key\_type | The following key\_types are supported:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>customer\_user\_id</li><li>imei</li><li>oaid</li></ul> |
| 400 | Request must have ‘data’ with at least 1 element | Data list can not be empty. |
| 400 | Request ‘data’ should not exceed the size of 4000 in a single request | Data list can include a maximum of 4,000 rows. |
| 400 | Request data has too many invalid ‘data’ elements | More than 10% of the data to modify is not valid according to the specification. |
| 404 | AppsFlyer - Page Not Found | Check that:<ul><li>The `{app-id}` as specified in the API request URL is correct.</li><li>The HTTP header contains the correct <Anchor target="_blank" href="/marketers/docs/managing-appsflyer-tokens">AppsFlyer V2.0 API token</Anchor>. Your account admin can obtain this token from the AppsFlyer dashboard.</li></ul> |

**Response examples**

```json
{
"message": "Accepted for processing",
"received": 1000,"invalid": 2,
"trace-id": "698ed323-c787-45b5-b792-463c67c94064"
}
```

```json
{
"error": "Request body must have a valid key_type",
"trace-id": "18a5f685-ea4d-4ca9-beab-a542a3786d12"
}
```

```json
{
"error": "Request must have 'data' with at least 1 element",
"trace-id": "c155a7fa-b573-4efe-9bfb-5ae7de40e7fd"
}
```

```json
{
"error": "Request 'data' should not exceeds the size of 4000 in a single request”,
"trace-id": "b325a7fa-b573-4efe-9bfb-5ae7de40e72c"
}
```

```json
{
"error": "Request data has too many invalid 'data' elements",
"valid": 2,
"invalid": 30,
"trace-id": "33551c1d-5682-405e-a959-c8729ca74735"
}
```

</Accordion>

<div id="rate-limitations" />

<Accordion title="Rate limitations">

* 5 requests per second
* 350 requests per minute

</Accordion>

<div data-zendesk-anchors="api-overview=about-the-api h_01HNZP1Y2MQ8W25SNP2XVNZ7WW=about-the-api h_01HNZP1Y2MJY56TMN6QH4BVRPA=when-should-i-use-this-api h_01HNZP1Y2MX414NJ49BCVW7KZC=important methods=actions h_01HNZP1Y2MS5V43XS008GG4S32=actions h_01HNZP1Y2MH2Y4P8ZT4SVM5GM2=authentication h_01HNZP1Y2MR0GCCA1916RMB6GJ=api-specifications-and-sample-code h_01HNZP1Y2M1N548KSMA6MQ601W=addmodify-identifiers-put h_01HNZP1Y2P2VVV4WT88D82QXJ4=notes h_01HNZP1Y2Q0FAQQE3MTZ8B3FFS=remove-identifiers-delete h_01HNZP1Y2QK2J8ERP1SQTYB20C=responses h_01HNZP1Y2Q1WZCN2TCEAS6HB2X=rate-limitations" />
