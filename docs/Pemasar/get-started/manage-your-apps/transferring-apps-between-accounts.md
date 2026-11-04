---
title: Transferring apps between accounts
metadata:
  keywords:
    - Account
    - Advertisers
    - Agencies
    - moving apps
    - move app
    - app transfer
    - transferring apps
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2018-07-24T07:56:37Z'
  edited_at: '2023-06-26T11:40:21Z'
  id: 360001336005
  locale: id
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/id/articles/360001336005
---
> **At a glance:** Transfer apps between AppsFlyer accounts by following the steps described in this article (for admins of both the sender and receiver accounts).

![5638-Transfering-an-app-NEW1.gif](https://files.readme.io/f4288a79bbd96e8cf828cf0ca9ae9ef994400f702cd66108d2861e3a405c4d79-360010967257.gif)

<div id="app-transfer-process" />

<div id="prerequisites" />

## App transfer between accounts

In order to transfer an app between AppsFlyer accounts, both the sending and receiving app owners (as represented by their AppsFlyer account admins) must complete the necessary transfer prerequisites and agree to the transfer.

**App transfer process**

The following is an overview of the app transfer process:

* The sender requests that AppsFlyer transfer the selected apps and enters the receiver admin's email address.
* The receiver is notified and agrees to receive the apps.
* Both sender and receiver admins receive notice of the pending transfer (both by email and on the **My apps** page).
  * While the transfer is pending, either admin can delete the app transfer request (cancel the transfer).
* After verifying that the sides have completed the transfer prerequisites, AppsFlyer transfers the apps.
  * If a prerequisite is incomplete, AppsFlyer contacts the relevant party to ensure completion.
  * Incomplete prerequisites usually relate to pending financial, commercial, or legal matters; or to the requested transfer of apps comprising more than 30% of an account's traffic over the last 90 days.

<div id="app-transfer-scope" />

<Accordion title="App transfer scope">

The following table details which app features and settings are transferred. Note that the sender can, at its discretion, delete certain settings and configuration information before the transfer.

<table><thead><tr><th>Item</th><th>Transferred/<br/>not transferred</th><th>Details/discretionary considerations</th></tr></thead><tbody><tr><td>App settings </td><td><p>Transferred</p></td><td><p><strong>Discretion:</strong> Sender can delete Firebase/GCM server key before transfer. </p></td></tr><tr><td rowspan="2">Integrated partners</td><td>Transferred</td><td><p><span>Integration, cost, and revenue configurations (including cost and revenue data)</span></p><p><strong>Discretion:</strong> If the receiver doesn't need integrated partners to be transferred, the sender should deactivate them and delete their configurations and credentials (including cost and ad revenue configurations).</p></td></tr><tr><td>Not transferred</td><td><p>Ad network and agency permissions</p><p>Twitter configurations and credentials</p></td></tr><tr><td>Link management</td><td>Not transferred</td><td><p>App is removed, but links remain.</p><p><strong>Discretion:</strong> The sender can delete obsolete links before transfer.</p></td></tr><tr><td>OneLink</td><td>Not transferred</td><td><p>OneLink continues to work as-is.</p><p><strong>Discretion:</strong> If the receiver needs OneLinks to be transferred, the sender should notify their CSM or <a href="mailto:hello@appsflyer.com">hello@appsflyer.com</a>.</p></td></tr><tr><td>Push API</td><td>Transferred</td><td><p><strong>Discretion:</strong></p><ul><li>If the receiver doesn't need Push API configurations (endpoints) to be transferred, the sender should delete the settings. Otherwise, data will continue to be delivered to sender-defined endpoints.</li><li>Alternatively, the receiver can change the settings on receipt to ensure the sender doesn't receive user-level data. </li></ul></td></tr><tr><td>Smart Banners</td><td>Not transferred</td><td><p>Smart Banner creatives remain.</p><p><strong>Discretion:</strong> If the receiver doesn't need creatives to be transferred, the sender should delete them.</p></td></tr><tr><td>Agencies</td><td>Not transferred</td><td>Agencies lose access to the app.</td></tr><tr><td>Audiences</td><td>Not transferred</td><td>Audiences are deleted.</td></tr><tr><td>Cost ingestion</td><td>N/A</td><td>Historical cost ingestion files are not accessible to the receiver. This does not impact cost history. </td></tr><tr><td>Data Locker</td><td>Not transferred</td><td>App is removed from Data Locker configuration, and the sender account stops receiving app data. </td></tr><tr><td>Historical data</td><td>Transferred</td><td> </td></tr><tr><td>Live alerts</td><td>Not transferred</td><td>App is removed from sender's alerts. Alert templates remain.</td></tr><tr><td>PBA brand bundles</td><td>Not transferred</td><td>Bundle is no longer available to the sender if any of its related apps are transferred. The receiver can't access PBA data.</td></tr><tr><td>Protect360 data</td><td>Transferred</td><td> </td></tr><tr><td>Raw &amp; aggregate data</td><td>Transferred</td><td> </td></tr><tr><td>SDK dev key</td><td>Transferred</td><td> </td></tr><tr><td>Validation rules</td><td>Transferred</td><td> </td></tr></tbody></table>

</Accordion>

## Transfer procedures

To request the transfer of one or more apps to another AppsFlyer account, start the process, and you'll be guided by the wizard in the user interface.

<div id="sender" />

<Accordion title="Sender">

**To submit a transfer request**:

1. Contact the receiver admin:
   1. Review and agree on the [app transfer scope](/docs/transferring-apps-between-accounts#app-transfer-scope). Make sure that you both understand what is and isn't transferred and that you both are properly prepared.
   2. Request that the receiver provides you with the Admin email address they use in AppsFlyer.
2. Do one of the following:
   * To transfer a single app: Go to **My apps** > Available apps > Open app action menu (...) > Select **Transfer app**.
   * To transfer 2 or more apps: Go to **My apps** > Open page action menu (...) > Select **Transfer apps**.
3. Choose the app or apps to transfer.
4. Click **Next**.
5. Enter the receiver Admin's email address.
6. Klik **Berikutnya**.
7. Read and sign the terms and conditions.
   * You and the receiver are notified (via email) that the request has been submitted successfully.
   * You are notified (by popup) if the request requires handling by AppsFlyer.
   * Apps appear on your **My apps** page as pending transfer to `<receiver email>`. At this stage, it is still possible to delete the request.[![App_transfer_sender_side.JPG](https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg)](https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg)

</Accordion>

<div id="receiver" />

<Accordion title="Receiver">

1. Contact the sender admin to review and agree on the [app transfer scope](/docs/transferring-apps-between-accounts#app-transfer-scope). Make sure that you both understand what is and isn't transferred and that you both are properly prepared.
2. You will receive an email notification that the sender has initiated the transfer request.
3. On the **My apps** page, click **Review request**. A request can include one or more apps.  
   [![App_transfer_receiver_side.JPG](https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg)](https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg)
4. Review and approve or reject each request.
5. Read and, if acceptable, sign the terms and conditions.
6. You and the sender are notified by email that the request has been accepted.
7. Transferred apps appear on your **My apps** page.

<div id="delete-transfer-request" />

<Accordion title="Delete transfer request">

Before the transfer is finalized, an app transfer process can be deleted (canceled) by either the sender or receiver admin.

**To delete an app transfer request:**

* **Sender admin**: Go to **My apps** > **Pending transfer to [email]** section > Click **Delete request**.  
  Both the sender and receiver admins are notified (email).
* **Receiver admin**: Go to **My apps** > **Apps pending transfer** section > Click **Reject**.  
  Both the sender and receiver admins are notified (email).

</Accordion>

</Accordion>

## Batasan

The following limitations apply to the app transfer process:

* CTV apps cannot be transferred.

<div data-zendesk-anchors="h_01EDBXVWAB5VBWT3XFK21KPV6W=receiver limitations=batasan" />
