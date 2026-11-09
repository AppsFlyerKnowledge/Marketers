---
title: Data Collaboration Platform (DCP) - Enrich sources with ID5
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2026-01-08T07:53:48Z'
  edited_at: '2026-10-01T00:07:45Z'
  id: 42626850533137
  locale: ja
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ja/articles/42626850533137
---
> **At a glance:** Enrich your first-party data with ID5 identifiers to unify fragmented user data and improve match rates with activation partners, resulting in larger audiences.

## About ID5 enrichment

AppsFlyer’s Data Collaboration Platform integrates with ID5, a leading identity solution provider for the open web. ID5 connects disparate identifiers such as IP addresses, hashed emails (HEM), and mobile advertising IDs (MAIDs) into a unified, privacy-first ID. This increases match rates across collaborators’ datasets, enabling more users to be recognized, joined, and activated in audiences. This guide explains how ID5 enrichment works in DCP, how to set it up, and how to use it for collaborations and activation.

**ID5 enrichment helps you:**

* Increase match rates between your first-party data and media partners or collaborators
* Maximize target audience size
* Bridge identifiers such as HEM, MAID, and IP + timestamp into a unified identity
* Future-proof your activation as third-party cookies phase out

**Common use cases include:**

* **Brand first-party data enrichment** - A brand uploads its first-party data source to DCP and enriches it with ID5 IDs using their ID5 connection.
* **Retailer-brand collaboration** - A retailer collaborates with a brand and shares access to their ID5 subscription. Within the secure collaboration scope, the brand enriches its customer data using the retailer’s ID5 connection, improving match rates without requiring its own direct ID5 account.
* **Partner activation** - Enriched sources can be sent to supported activation partners to increase match rates, meaning more users from your data can be matched and included in the audiences on the partner side.

## How ID5 works

DCP uses the returned ID5 IDs to enrich your source, resulting in a new enriched source available for segmentation and activation.

**Two supported enrichment flows:**

| Flow | Description | When to use |
| --- | --- | --- |
| Tagged flow | The data owner already applies ID5’s site tagging on their domain, so their uploaded data already contains an ID5 ID column. | When you manage ID5 tagging directly on your site and want to use DCP without further enrichment. |
| Server-to-server (S2S) enrichment flow | AppsFlyer sends your selected data source to ID5, ID5 enriches it with ID5 IDs, and returns it to DCP as an enriched source. | When your source does not include an ID5 column or when you want AppsFlyer to handle enrichment automatically. |

## Get started with ID5 enrichment

This section describes how to create an ID5 connection in DCP and use it for enrichment.

**Prerequisites:**

* An AppsFlyer account with DCP permissions
* An ID5 token (provided by your ID5 account manager)
* A source containing at least one of the supported identifiers: HEM, MAID, or IP + timestamp

<div id="create-an-id5-connection" />

<Accordion title="Create an ID5 connection">

To use ID5 enrichment, first create a **Data & Identity** connection in DCP.

1. Access the Data Collaboration Platform by clicking **Collaborate** > **Data Clean Room**, in the AppsFlyer side menu.

   <Image align="center" alt="Click Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="33.49%" />
2. Go to **Manage connections** (on the upper-right).
3. Under the **Data & Identity** tab, select **+ New connection**.

   **<Image alt="+New connection.png" src="https://files.readme.io/815ec20e84d85da413dfe9c9358b54d772461e1eeb3dff3ff7c5c31ced1088ac-42729247721873.png" width="72.63%" />**
4. Select **ID5.**

   **<Image alt="Select ID5.png" src="https://files.readme.io/a0c53243318fa7eed48ac5886ff5f3272bec0e6fd83a41117d53473757ab16d7-42729260095633.png" width="66.76%" />**
5. Enter your ID5 token (if relevant).
6. Click **Save**.

Once saved, the connection becomes available for your sources and collaborations (subject to permissions).

</Accordion>

<div id="enrich-a-source-with-id5" />

<Accordion title="Enrich a source with ID5">

You can enrich your sources using the S2S flow.

**To enrich a source:**

1. Access the Data Collaboration Platform by clicking **Collaborate** > **Data Clean Room**, in the AppsFlyer side menu.
2. Go to the **Sources** tab and hover over the relevant source.
3. From the action menu, select **Enrich**.

   <Image align="center" alt="Enrich.png" src="https://files.readme.io/51c3f33da62d84ec9214e178e3bbaef15d6a03a32827ad393166db0dcd9a70fd-42729376739473.png" width="245px" />
4. Click **Start enrichment**.
5. After the enrichment flow is done, you will have a new source that is connected to the original source with the addition of ID5 IDs.  
   **Note:** If the original source is ever deleted, the new source will also be deleted.

</Accordion>

<div id="grant-id5-permissions-in-a-collaboration" />

<Accordion title="Grant ID5 permissions in a collaboration">

Collaboration owners can allow collaborators to use an ID5 connection in a collaboration (subject to the commercial agreement with ID5).

**To grant ID5 permissions to a collaborator:**

1. Access the Data Collaboration Platform by clicking **Collaborate** > **Data Clean Room** in the AppsFlyer side menu.
2. In the **Collaborations** tab, open an existing collaboration or <Anchor target="_blank" href="/marketers/ja/docs/data-collaboration-platform-dcp-create-a-collaboration">create a new one</Anchor>.
3. Click **Collaboration with “your collaborator”.**

   **<Image alt="Update collaboration policy.png" src="https://files.readme.io/25d707c47bed9f5f60cd1ba521c4b48f41afbb0e36949f0ffa35cecf9a932ddc-42838633495313.png" width="58.95%" />**
4. Click **Edit collaboration policy**.

   <Image align="center" alt="Click Edit collaboration policy.png" src="https://files.readme.io/07aab2a3165d26779e94f62eb8487893bc725dfa3ad4c406de576480e2ed6c13-42838633497489.png" width="80.3%" />
5. Click **Access permissions**.

   **<Image alt="Click Access permissions.png" src="https://files.readme.io/b239775d71e1fa1dcc23537e73e35b80bff0184c9ee2aa213f644d90251284f3-42838633499281.png" width="78.62%" />**
6. Enable **ID5 connection**.

   <Image align="center" alt="ID5 permissions.png" src="https://files.readme.io/f2831ec4f775b51ef419da33444198de6aabfde3b27d83cc9af623eaed4a865c-42789059643793.png" width="79.6%" />
7. Click **Save**.

Collaborators can then associate their own sources with the collaboration and enrich them using the partner’s ID5 connection.

</Accordion>

## Traits and limitations

This section outlines some key traits and limitations.

| Trait / Limitation | Description |
| --- | --- |
| First enrichment and daily updates | The first enrichment run begins immediately and typically completes within several hours.<br /><br />After the initial run, enrichment continues daily at a fixed processing time, ensuring fresh identity mappings.<br /><br />You can pause enrichment at any time to stop daily updates. |
| Source dependency | If the original source is deleted, the enriched source is automatically deleted. |
| Activation scope | In a collaboration, an advertiser can use enriched data for activation but cannot download or query it. |
| Status restrictions | You can enrich only sources in **Active** status. |
| Enrichment latency | Sources in **Waiting** or **Processing** continue enrichment but become usable only after reaching **Active** status. |
| Retention window | ID5 stores mappings for 14–90 days, depending on activity. |
| Identifier requirement | If the source lacks HEM, MAID, or IP + timestamp, enrichment is disabled. |
| Connection conflicts | A collaboration can include only one ID5 connection. If both parties have their own ID5 connections, neither connection can be used within the collaboration. In this case, each party must enrich their data separately in their own environment, and only the resulting enriched sources can then be used in the collaboration. |

<div data-zendesk-anchors="h_01KD7VPW5NX5QHVPJWX5YCGXAH=about-id5-enrichment h_01KD7VPW5NW24X53QQE2ZVDA2N=how-id5-works h_01KD7VPW5P0FEEAET9RXVPSECY=get-started-with-id5-enrichment h_01KD80FBKDHB6HKTTMXFDPGH5E=create-an-id5-connection h_01KD80FBKE4Q8TMNW7WFCN4QGC=enrich-a-source-with-id5 h_01KD80FBKE6TB00E8PZCFWST6M=grant-id5-permissions-in-a-collaboration h_01KD7VPW5P5XV61Z3X2CWZ7GV9=traits-and-limitations" />
