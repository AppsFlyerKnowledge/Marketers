---
title: Adobe Experience Platform (AEP) integration with AppsFlyer Data Locker
excerpt: >-
  Set up an integrated solution with Adobe Experience Platform (AEP) to send
  raw-level event data to the Adobe data lake. AEP is the data layer for all
  customers centralizing data in Adobe, a customer data platform that captures
  customer journeys provides and lets you analyze them.
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2023-03-19T06:54:23Z'
  edited_at: '2023-10-26T12:33:46Z'
  id: 13856826626321
  locale: en-us
  section: Adobe
  section_id: 6551419728657
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/13856826626321-Adobe-Experience-Platform-AEP-integration-with-AppsFlyer-Data-Locker
---
## Overview

The Data Locker—AEP integration enables you to use AppsFlyer data within the Adobe Experience Platform. The integration uses the out-of-the-Box (OOTB) component, backed by the real-time customer data platform (RTCDP). In order to upload AppsFlyer data into Adobe Experience Platform (AEP), customers should first configure a Data Locker bucket (GCS and AWS) connection and then configure AEP to load the data from the bucket into an existing or new dataset unit.

## Setting up the integration

<span id="prerequisites"></span>**Prerequisites**:

* A [Data Locker](/docs/data-locker) subscription
* An [Experience Platform](https://business.adobe.com/products/experience-platform/adobe-experience-platform.html) account with Admin permissions

**To set up the integration**:

1. <span id="step-1-aws-create-an-aws-iam-user-with-bucket-access"></span>Create a bucket with permissions for Data Locker. Follow the instructions for [GCS](/docs/data-locker-cloud-service-setup#gcs-storage) or [AWS](/docs/data-locker-cloud-service-setup#aws-storage) storage.
2. Set up Data Locker. Follow the [Data Locker setup instructions](/docs/data-locker-for-marketers#set-up-data-locker), and when you select your GCS or AWS bucket, make sure you select **Make this connection compatible with Adobe Experience Platform**.
3. Configure the Data Locker schema in AEP.
   1. Login to AEP using your admin credentials.
   2. Create an Adobe XDM [experience event class](https://experienceleague.adobe.com/docs/experience-platform/xdm/classes/experienceevent.html?lang=en#).
   3. Add a new field group for AppsFlyer fields.
   4. Create the first field as an object field called AppsFlyer.  
      This is the parent field. All other fields that are created are children to this object field.
   5. Add the other Data Locker schema fields. If you are using Adobe CJA, mark customer\_user\_id as business identifier.
4. Configure the bucket source in AEP.
   1. In AEP, add a bucket connector (the same AWS or GCS bucket you used in Data Locker).
   2. Complete the required authentication details.
   3. Click **Connect to source**.
5. Configure the data flow in AEP.
   1. In **AEP Select data**, select the relevant AppsFlyer Data Locker reports from the bucket folder list.
   2. Set:
      * Data format as Delimited.
      * Delimiter as ",".
      * Compression type as Gzip.
   3. Click **Next**.
   4. In **Dataflow details**, complete the dataset and data flow details.
   5. Click **Next**.
   6. In **Scheduling**, set the frequency to 60 minutes.
   7. Repeat for each desired Data Locker report.

> 📘 **See also**
>
> * [Adobe Launch SDK Extension](/docs/adobe-launch-sdk-extension?query=adobe)
> * [Adobe Air plugin](/docs/adobe-air-plugin?query=adobe)

<div data-zendesk-anchors="h_01HDNYXDFCQQBNBB6ZQQTJS189=overview h_01HDNYXDFCEVVDS5RANQMP6K3G=setting-up-the-integration h_01HDNZ1AS5YTK6N26PD7S7C0XF=see-also" />
