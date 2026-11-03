---
title: 'Bulletin: Retargeting support for CTV, PC, and console platforms'
metadata:
  keywords:
    - Marketers
    - CTV Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2026-07-07T14:08:17Z'
  edited_at: '2026-08-12T08:37:22Z'
  id: 48515925079313
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/48515925079313-Bulletin-Retargeting-support-for-CTV-PC-and-console-platforms
---
| Section | Details |
| --- | --- |
| **What's new** | AppsFlyer now supports retargeting measurement, re-engagement and re-attribution, for extended (non-mobile) platforms: CTV, PC, and Console. Previously, these platforms supported UA attribution only.<br /><br />Retargeting for extended platforms includes two conversion types:<ul><li>**Re-engagement** credits campaigns that bring an existing, already-installed user back into the app.</li><li>**Re-attribution** (retargeting reinstall) credits campaigns that drive a lapsed user to reinstall and reopen the app. See <Anchor target="_blank" href="/marketers/id/docs/measure-reinstalls#reattribution">measuring re-attribution</Anchor> for more detail.</li></ul>This closes a key gap for advertisers running lifecycle marketing, where re-engagement and re-attribution are needed to correctly credit campaigns that reactivate users, drive repeat consumption, and reduce churn. It also improves cohort and LTV accuracy. Previously, without retargeting support, later app activity was anchored to the original install date, which distorted cohorts, payback, and LTV analysis. For background on how AppsFlyer measures extended platforms generally, see <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, and console platform attribution concepts</Anchor>. |
| **Effective date** | 1 August, 2026 |
| **What you should do** | There are three configuration layers: the app, the media source or integration, and the attribution link.<ol><li>In the <Anchor target="_blank" href="/marketers/id/docs/app-settings#pengaturan-atribusi">app's settings</Anchor>, turn on the **Re-engagement attribution** toggle. This is the master switch for the app. If it's off, you can't enable re-engagement on any media source for that app.</li><li>In the **Integration** tab of the **Active integrations** page for each partner or media source you want to run retargeting with, turn on **Reinstall attribution** to enable re-attribution credit, and **Re-engagement attribution** to enable re-engagement credit. Turn on **Re-engagement view-through attribution** too if you also want view-through credit, otherwise leave it off for click-through only.</li><li>For non-SRN networks, add `af_campaign_type=retargeting` to the attribution link. To add this parameter automatically, turn on **Enable retargeting settings** in the **Attribution link** tab of the **Active integrations** page. See the <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide">Retargeting attribution guide</Anchor> and <Anchor target="_blank" href="/marketers/id/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV, PC, and console platform direct attribution links</Anchor> for the link creation flow. Use this link in your campaigns.</li></ol>**<span id="h_01KZTHWRSZJW2W0JCDCWCK3P5P"></span>Note**<br />Roku, currently the only self-reporting network (SRN) available for these platforms, supports re-engagement only. It doesn't support re-attribution, and there's no attribution link to configure. For Roku, any claim is eligible for retargeting as long as the toggles are on. |
| **What you should know** | Keep the following in mind when measuring retargeting on extended platforms:<ul><li>**Supported platforms:** Retargeting for extended platforms applies to any platform that isn't Android, iOS, Windows Phone, or website. In practice, this means CTV, PC, and Console apps.</li><li>**Scope:** This feature covers non-mobile platforms only (CTV, PC, Console). Cross-platform retargeting into mobile isn't supported. For example, a CTV ad driving a mobile app install is still not supported. However, web ads leading to PC app installs are supported.</li><li>**SRN limitation:** Roku, the only SRN available for these platforms today, supports re-engagement only, not reinstall or re-attribution. This may not hold for other SRNs added in the future.</li><li>**Optional windows:** The re-engagement window (default 30 days) determines the period during which in-app events are primarily attributed to the re-engagement conversion. The inactivity window (default 7 days) determines how long a user must be inactive to be eligible for retargeting. These windows work the same as on mobile. See the <Anchor target="_blank" href="/marketers/id/docs/retargeting-attribution-guide#jendela-inklusi">Retargeting attribution guide</Anchor> and <Anchor target="_blank" href="/marketers/id/docs/set-retargeting-inactivity-window">Set retargeting inactivity window</Anchor>.</li><li>**Where results show up:** My Dashboards and Data Locker advanced reports only. There's no new retargeting raw data report in the classic Data Locker reports. For platform-specific dashboard behavior, see Overview dashboard, user acquisition and retargeting LTV.</li></ul> |