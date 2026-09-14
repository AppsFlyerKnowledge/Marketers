---
title: "Adobe Experience Platform (AEP) integration with AppsFlyer Data Locker"
excerpt: "Set up an integrated solution with Adobe Experience Platform (AEP) to send raw-level event data from AppsFlyer Data Locker to the Adobe data lake."
---
The Data Locker—AEP integration enables you to use AppsFlyer data within the Adobe Experience Platform. The integration uses the out-of-the-Box (OOTB) component, backed by the real-time customer data platform (RTCDP). In order to upload AppsFlyer data into Adobe Experience Platform (AEP), customers should first configure a Data Locker bucket (GCS and AWS) connection and then configure AEP to load the data from the bucket into an existing or new dataset unit.

## Setting up the integration

**Prerequisites**:

- A [Data Locker](https://support.appsflyer.com/hc/sections/6550945728657-Data-Locker%20Adobe) subscription
- An [Experience Platform](https://business.adobe.com/products/experience-platform/adobe-experience-platform.html) account with Admin permissions

**To set up the integration**:

1. Create a bucket with permissions for Data Locker. Follow the instructions for [GCS](https://support.appsflyer.com/hc/articles/360017603577#gcs-storage) or [AWS](https://support.appsflyer.com/hc/articles/360017603577#aws-storage) storage.
2. Set up Data Locker. Follow the [Data Locker setup instructions](/docs/data-locker-for-marketers#set-up-data-locker), and when you select your GCS or AWS bucket, make sure you select **Make this connection compatible with Adobe Experience Platform**.
3. Configure the Data Locker schema in AEP.
   1. Login to AEP using your admin credentials.
   2. Create an Adobe XDM [experience event class](https://experienceleague.adobe.com/docs/experience-platform/xdm/classes/experienceevent.html?lang=en#).
   3. Add a new field group for AppsFlyer fields.
   4. Create the first field as an object field called AppsFlyer.
      This is the parent field. All other fields that are created are children to this object field.
   5. Add the other Data Locker schema fields. If you are using Adobe CJA, mark customer_user_id as business identifier.
4. Configure the bucket source in AEP.
   1. In AEP, add a bucket connector (the same AWS or GCS bucket you used in Data Locker).
   2. Complete the required authentication details.
   3. Click **Connect to source**.
5. Configure the data flow in AEP.
   1. In **AEP Select data**, select the relevant AppsFlyer Data Locker reports from the bucket folder list.
   2. Set:
      - Data format as Delimited.
      - Delimiter as ",".
      - Compression type as Gzip.
   3. Click **Next**.
   4. In **Dataflow details**, complete the dataset and data flow details.
   5. Click **Next**.
   6. In **Scheduling**, set the frequency to 60 minutes.
   7. Repeat for each desired Data Locker report.

<Cards>
  <Card title="Adobe Launch SDK Extension" href="https://support.appsflyer.com/hc/articles/360000939097-Adobe-launch-SDK-extension?query=adobe">
    Learn how to integrate the Adobe Launch SDK Extension with AppsFlyer.
  </Card>
  <Card title="Adobe Air plugin" href="/docs/adobe-air-plugin">
    Learn how to integrate the Adobe AIR plugin with AppsFlyer.
  </Card>
</Cards>