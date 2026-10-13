---
title: "Transferring apps between accounts"
excerpt: "Transfer apps between AppsFlyer accounts by following the steps described in this article (for admins of both the sender and receiver accounts)."
x-zendesk:
  id: 360001336005
  url: https://support.appsflyer.com/hc/en-us/articles/360001336005-Transferring-apps-between-accounts
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Manage your apps
  section_id: 6551015977105
  position: 3
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials, Agencies]
  labels: [Account, Advertisers, Agencies, moving apps, move app, app transfer, transferring apps, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2018-07-24T07:56:37Z'
  edited_at: '2026-09-22T10:53:22Z'
---
![App transfer process animation showing the transfer wizard steps](https://files.readme.io/f4288a79bbd96e8cf828cf0ca9ae9ef994400f702cd66108d2861e3a405c4d79-360010967257.gif)

## App transfer between accounts

In order to transfer an app between AppsFlyer accounts, both the sending and receiving app owners (as represented by their AppsFlyer account admins) must complete the necessary transfer prerequisites and agree to the transfer.

### Prerequisites

* Make sure you have emails of both the sender and the receiver's account (owner)
* Both accounts are active. Suspended accounts can't send or receive apps.
* Neither account has unpaid invoices
* Transferring apps between accounts can only be done by an [account owner](/docs/user-management#account-owner). It can't be performed by an admin role.
* App transfer must be to an account with a Growth or Enterprise plan. [Learn more](/docs/account-management-plans-payments-and-billing#appsflyer-plans)

### App transfer process

The following is an overview of the app transfer process:

1. The sender requests that AppsFlyer transfer the selected apps and enters the receiver admin's email address.
2. The receiver is notified and agrees to receive the apps.
3. Both sender and receiver admins receive notice of the pending transfer (by email and on the **My apps** page).   
   **Note:** While the transfer is pending, either admin can delete the app transfer request (cancel the transfer).
4. AppsFlyer transfers the apps. If a prerequisite is incomplete, AppsFlyer contacts the relevant party to ensure completion.

<Accordion title="App transfer scope">

The following table details which app features and settings are transferred. Note that the sender can, at its discretion, delete certain settings and configuration information before the transfer.

<table><thead><tr><th>Item</th><th>Transferred/<br/>not transferred</th><th>Details/discretionary considerations</th></tr></thead><tbody><tr><td>App settings </td><td>Transferred</td><td><strong>Discretion:</strong> Sender can delete Firebase/GCM server key before transfer. </td></tr><tr><td rowspan="2">Integrated partners</td><td>Transferred</td><td><p>Integration, cost, and revenue configurations (including cost and revenue data)</p><p> </p><p><strong>Discretion:</strong> If the receiver doesn't need integrated partners to be transferred, the sender should deactivate them and delete their configurations and credentials (including cost and ad revenue configurations).</p></td></tr><tr><td>Not transferred</td><td><p>Ad network and agency permissions</p><p>Twitter configurations and credentials</p></td></tr><tr><td>Link management</td><td>Not transferred</td><td><p>OneLink templates and links are not transferred automatically but can be transferred by your CSM. </p><p><strong>To transfer templates and links: </strong>Contact your CSM or send message to <a href="mailto:hello@appsflyer.com">hello@appsflyer.com</a>. <br/><strong>Note:</strong> Bulk links are automatically transferred along with the template.</p><ul><li>The sender can delete obsolete links before transfer.</li><li>OneLink API tokens are not transferable between accounts. You'll need to use a <a href="./managing-appsflyer-tokens">token</a> from your new account.</li></ul><p>The domain redirect allowlist also isn't transferred automatically. If the receiving account's allowlist doesn't already include the transferred app's domains, links using those domains will break after the transfer. Make sure to <a href="./set-up-your-domain-redirect-allowlist">set up the domain redirect allowlist</a> in the receiving account before or immediately after the transfer.</p></td></tr><tr><td>Push API</td><td>Transferred</td><td><p><strong>Discretion:</strong></p><ul><li>If the receiver doesn't need Push API configurations (endpoints) to be transferred, the sender should delete the settings. Otherwise, data will continue to be delivered to sender-defined endpoints.</li><li>Alternatively, the receiver can change the settings on receipt to ensure the sender doesn't receive user-level data. </li></ul></td></tr><tr><td>Smart Banners</td><td>Not transferred</td><td>Banners, Banner groups, creatives, websites are not transferred. </td></tr><tr><td>Smart Script</td><td>Not transferred</td><td>Smart Scrips that created within the AppsFlyer UI will not be available in the new account. </td></tr><tr><td>Agencies</td><td>Not transferred</td><td>Agencies lose access to the app.</td></tr><tr><td>Audiences</td><td>Not transferred</td><td>Audiences are deleted.</td></tr><tr><td>Cost import</td><td>N/A</td><td>Historical cost import files are not accessible to the receiver. This does not impact cost history. </td></tr><tr><td>Data Locker</td><td>Not transferred</td><td>App is removed from Data Locker configuration, and the sender account stops receiving app data. </td></tr><tr><td>Historical data</td><td>Transferred</td><td> </td></tr><tr><td>PBA brand bundles</td><td>Not transferred</td><td><p>Bundle is no longer available to the sender if any of its related apps are transferred. The receiver can't access PBA data.</p><p>This means that if the client needs to keep using PBA in their new account, they need to delete their web bundle before the app transfer is completed, otherwise they won't be able to create the same web bundle in their new account.</p></td></tr><tr><td>Protect360 data</td><td>Transferred</td><td><p>If an app is transferred from an account without a Protect360 asset to one that has one: </p><ul><li>Fraud detection starts only after the transfer is complete.</li><li>If the receiving account has the asset only for part of the time, fraud data is available starting from the asset's start date only, and not retroactively.</li><li>No fraud detection occurs during the transfer process.</li></ul></td></tr><tr><td>Raw &amp; aggregate data</td><td>Transferred</td><td> </td></tr><tr><td>SDK dev key</td><td>Transferred</td><td> </td></tr><tr><td>Validation rules</td><td>Transferred</td><td> </td></tr></tbody></table>

</Accordion>

## Transfer procedures

To request the transfer of one or more apps to another AppsFlyer account, start the process, and you'll be guided by the wizard in the user interface.

<Accordion title="Sender">

**To submit a transfer request**:

1. Contact the receiver admin:
   1. Review and agree on the [app transfer scope](/docs/transferring-apps-between-accounts#app-transfer-scope). Make sure that you both understand what is and isn't transferred and that you both are properly prepared.
   2. Request that the receiver provides you with the Admin email address they use in AppsFlyer.
2. Do one of the following**:**
   * To transfer one app: From the top menu bar > **My Apps** > Open app action menu (...) > Select **Transfer app**.
   * To transfer 2 or more apps**:** From the top menu bar > **My Apps** > Open app action menu (...) > Select **Transfer app**.
3. Choose the app or apps to transfer.
4. Click **Next**.
5. Enter the receiver Admin's email address.
6. Click **Next**.
7. Read and sign the terms and conditions.
   * You and the receiver are notified (via email) that the request has been submitted successfully.
   * You are notified (by popup) if the request requires handling by AppsFlyer.
   * Apps appear on your **My apps** page as pending transfer to `<receiver email>`. At this stage, it is still possible to delete the request.

     ![Sender's My apps page showing an app listed as pending transfer, with a Delete request option](https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg)

</Accordion>

<Accordion title="Receiver">

1. Contact the sender admin to review and agree on the [app transfer scope](/docs/transferring-apps-between-accounts#app-transfer-scope). Make sure that you both understand what is and isn't transferred and that you both are properly prepared.
2. You will receive an email notification that the sender has initiated the transfer request.
3. On the **My apps** page, click **Review request**. A request can include one or more apps.

   ![Receiver's My apps page showing a pending app transfer request with a Review request option](https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg)
4. Review and approve or reject each request.
5. Read and, if acceptable, sign the terms and conditions.
6. You and the sender are notified by email that the request has been accepted.
7. Transferred apps appear on your **My apps** page.

</Accordion>

<Accordion title="Delete transfer request">

Before the transfer is finalized, an app transfer process can be deleted (canceled) by either the sender or receiver admin.

**To delete an app transfer request:**

* **Sender admin**: From the top menu bar > **My Apps** > **Pending transfer to [email]** section > Click **Delete request**.   
  Both the sender and receiver admins are notified (email).
* **Receiver admin**:
* From the top menu bar > **My Apps** > **Apps pending transfer** section > Click **Reject**.   
  Both the sender and receiver admins are notified (email).

</Accordion>
