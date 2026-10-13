---
title: "Bulletin: Meta ads app ownership verification"
table_of_contents: false
x-zendesk:
  id: 5410285239313
  url: https://support.appsflyer.com/hc/en-us/articles/5410285239313-Bulletin-Meta-ads-app-ownership-verification
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 50
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: [Facebook, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-04-12T09:40:58Z'
  edited_at: '2023-11-26T12:48:41Z'
---
| **Bulletin date** | April 7, 2022 |
| --- | --- |
| **What's new** | CALLSTART::Note::<br /><br />#### Important!<br /><br />Beginning sometime in the first half of 2023, all app owners will be required to confirm ownership of any Android or iOS mobile app both for new and **existing** apps. If the app ownership has not been confirmed, advertisers will be unable to optimize their app ads for mobile app installs.<br /><br />CALLEND::<br /><br />Beginning April 7, 2022, app owners of new apps added to Meta ads (formerly Meta ads) will be required to confirm their ownership of the apps. This change applies to all Meta advertising platforms such as FB, IG, Messenger, FAN, etc, and to all operating systems.<br /><br />**If ownership isn’t confirmed, advertisers may experience loss of platform access or other app disruption, and won’t be able to:**<br /><br />* **Run Mobile App Install campaign objective**<br />* **Optimize their app ads’ delivery for mobile app installs** |
| **What do I need to do?** | Meta ads requires advertisers who add new apps or edit apps that were added after April 7, to confirm their app ownership. The first step is updating the  <br />app-ads.txt file on the website domain listed within your app store listing. Then, go to the Meta for Developers App Dashboard, enter your app ID, and confirm your ownership.  <br />Meta ads will verify that your app-ads.txt file exists at the domain URL provided and confirm app ownership.<br /><br />* **See [detailed instructions](https://www.facebook.com/business/help/441531361057663) for confirming app ownership.**<br />* **See the [troubleshooting guide](https://developers.facebook.com/docs/audience-network/optimization/best-practices/troubleshoot-app-ads) for issues with app-ads.txt.**<br />* **Learn more about the [required specifications for app-ads.txt](https://iabtechlab.com/wp-content/uploads/2019/03/app-ads.txt-v1.0-final-.pdf?fbclid=IwAR2U1W8QXLcH3OGdB-yLpkH6irqyCijwhYH-gf52BbsRHUu3hpnS4IDlWac).** |
| **FAQ** | * **Can I still advertise an app if I haven’t authenticated it?**  <br />  The only way to continue advertising unauthenticated apps submitted after April 7, is to add the associated app store link and not optimize for app install. App authentication only restricts the usage of app install optimization, not advertising overall.<br />* **Do I have to republish my SDK on Play Store or App Store after adding the app-ads.txt?**  <br />  Yes, an app owner would have to update their app store listing on the Play Store (Android) and the App Store (iOS) after adding app-ads.txt to their developer website, as the app store listing would need to be updated to the new developer website. This is only required if a developer website was not previously listed on the app store listing. Note: This is not a requirement on App Store or Play Store. Approval of an app store listing approval takes about 1 week. |