---
title: Set up the Lookback windows task
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2025-08-18T11:38:51Z'
  edited_at: '2026-10-13T00:15:26Z'
  id: 38191154658193
  locale: ko
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/ko/articles/38191154658193
---
## Set Lookback Windows

> **At a glance:** Set attribution windows for on-site and off-site campaigns to determine how far back user engagements can be matched to conversions.

Lookback windows define the maximum time between a user engagement (click or view) and the resulting conversion for attribution purposes. Each collaboration can set a custom lookback window duration. Media partners, such as Google Ads or Meta Ads, usually apply different rules for configuring these windows. This article explains how to configure lookback windows for both collaborators and Google and Meta.

## Prerequisites

Before a collaborator who is not the collaboration owner can set up the Lookback Windows task, the owner must first assign it to them. For more information, see Assign configuration tasks.

## Open the Lookback windows task

The Lookback windows task in the **Measurement settings** page is where you configure the lookback windows of <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaign-measurement">on-site and off-site campaigns</Anchor>.

To open the Lookback windows task, follow these steps:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Data Clean Room**.
2. On the **Data Collaboration Platform** page, select the collaboration you want to set.
3. At the bottom of the collaboration page, click **Set up measurement.**
   * If the link is grayed out, set up the collaboration's <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources">data sources</Anchor> and <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiences</Anchor>.
4. On the **Measurement Setting** page, click the **Lookback windows** task pane to open the **Lookback windows** dialog.

   > 📘 **Note**
   >
   > If the **Lookback windows** pane is grayed out, ask the collaboration owner to assign you the Lookback windows task.


## Set the collaboration lookback window

To set the collaboration lookback window, follow these steps:

1. If you are setting up a <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">combined on-site and off-site campaign</Anchor> in the **Lookback Windows** dialog, expand the <Image alt="AppsFlyer.png" src="https://files.readme.io/2536fe45ebde303e110c7b90cb3b2a95fc28672a5fa095efff485cdebbd466df-38392816916369.png" width="2.61%" /> **CMN Attribution** pane. Otherwise, skip to the next step.
2. In the **Click-through** or **View-through lookback window** sliders, drag the pointer to choose the window duration in days.
3. Click **Save**.

## Set the Meta Ads lookback window

If you are running an off-site campaign with Meta Ads, the Lookback windows task will include settings dedicated to the Meta Ads. You can set click-through and view-through attribution windows separately, according to the Meta Ads predefined window durations.

1. In the **Lookback windows** panel, expand the <Image alt="Meta.png" src="https://files.readme.io/4023aa4c9446f22aa46063ab349fc038d974638aeefcbb3288e04663896ec788-38392832989585.png" width="3.22%" /> **Meta Ads** panel.
2. Select the **Click-through** and **View-through** attribution windows from the following options:
   * **1 day**
   * **7 days**
   * **28 days**

## Google Ads lookback window

If you are running an off-site campaign with Google Ads, the Lookback windows task will include a link to the Google Ads platform.

1. In the **Lookback windows** dialog, scroll to the <Image alt="Google-ads.png" src="https://files.readme.io/afa0e2cd15ea4214eba625da397dccd04118b564450c59993fd0e668c31f023b-38392832994321.png" width="2.86%" /> **Google Ads** pane.
2. Click the **arrow icon** to open the relevant Conversion Action settings page on the Google Ads platform.
3. Update the lookback window settings as needed within Google Ads.

<div data-zendesk-anchors="h_01K3G9Q0G79BDATM6T80T6F6TX=set-lookback-windows h_01K3G9Q0G7XSM1VS4VF9VCTWD0=prerequisites h_01K3G9Q0G7FM4MMR6CVWM4ATRA=open-the-lookback-windows-task h_01K3G9Q0G7DQRCX9FH9Q3N17N3=note h_01K3G9Q0G7X7FY6C0H4DQYSP3F=set-the-collaboration-lookback-window h_01K3G9Q0G71ADFQ9QHBXJBTEAA=set-the-meta-ads-lookback-window h_01K3G9Q0G7HEFS65XA6YD0V6YD=google-ads-lookback-window" />
