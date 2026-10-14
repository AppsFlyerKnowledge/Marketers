---
title: "Bulletin: Supporting the new Amazon DSP EU consent policy"
table_of_contents: false
x-zendesk:
  id: 45664244736529
  url: https://support.appsflyer.com/hc/en-us/articles/45664244736529-Bulletin-Supporting-the-new-Amazon-DSP-EU-consent-policy
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 0
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: []
  promoted: false
  comments_disabled: false
  created_at: '2026-04-12T09:11:36Z'
  edited_at: '2026-05-12T16:05:37Z'
---
| Section | Details |
| --- | --- |
| **What's new** | As part of Amazon's enforcement of the Digital Markets Act (DMA), Amazon Ads is updating their EU consent policy. AppsFlyer is making the necessary changes to support Amazon's policy requirements while ensuring that advertisers maximize the value of their Amazon Ads marketing channels. |
| **Effective date** | <ul><li>Effective enforcement date on Amazon - June 30, 2026</li><li>Effective support date on AppsFlyer - May 18, 2026</li></ul> |
| **What you need to know** | **Relevant integrations and audience:** All advertisers with apps that are integrated with Amazon Ads via the `amazondsp_int` SRN integration and have advertising activity in the EU (including UK and Switzerland).<br /><br />**Required actions:** Ensure that you pass valid DMA consent signals to AppsFlyer for any event (app open or in-app event) for users in the EU, UK, or Switzerland.<br /><br />The consent signals can be one of the following:<ol><li>**Manual consent:** The only required field is `ad_user_data_enabled` as part of the manual consent array. The other fields required for Google's DMA consent are not relevant for Amazon.</li><li>**TCF consent:** Send the full TCF consent information as created by your CMP, and make sure to include the Amazon Ads vendor ID (`793`) in the list of consented vendors.</li><li>**GPP consent strings:** Amazon supports GPP consent strings, but this is not currently supported by AppsFlyer.</li></ol>**See also**<ul><li>[How to send DMA consent via AppsFlyer's SDK](https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance)</li><li>[How to send DMA consent via AppsFlyer's S2S](https://dev.appsflyer.com/hc/reference/s2s-events-api3-post) (search for `consent_data`)</li></ul> |