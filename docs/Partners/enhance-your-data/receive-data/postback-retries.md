---
title: "Postback retries"
excerpt: "Learn how postback retries work in AppsFlyer and how integrated partners can configure their postback mechanisms."
x-zendesk:
  id: 360001376085
  url: https://support.appsflyer.com/hc/en-us/articles/360001376085-Postback-retries
  locale: en-us
  category: Partners
  category_id: 6550456653457
  section: Receive data
  section_id: 6551235995281
  position: 2
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution, Ad Networks]
  labels: [Advertisers, Ad Networks, Partners]
  promoted: false
  comments_disabled: true
  created_at: '2018-08-06T04:59:54Z'
  edited_at: '2023-02-15T13:15:04Z'
---
## Introduction

Postbacks to partners are a critical part of the integration between AppsFlyer and our partners. Since any system can experience momentary issues in its responsiveness, AppsFlyer is able to retry failed postbacks.

## Important information

<Accordion title="When does AppsFlyer retry a failed postback?">

A postback is retried when the response indicates an error on the receiving server-side 5XX errors.

</Accordion>

<Accordion title="How often does AppsFlyer retry a failed postback?">

The first failed postback is retried up to four additional times in 15-minute intervals. In total, a single postback can be sent up to five times.

</Accordion>

<Accordion title="Can retried postbacks be identified in postback reports?">

The raw data Postback report: "Postback Retry". The first postback sent has a blank value in this column. Any retried postback contains the value TRUE in this column.

</Accordion>

<Accordion title="How can a partner identify the total eventual failed postbacks in the Postback report?">

A postback that has four TRUE values listed in the "Postback Retry" column and also contains error codes in the Postback HTTP Response Code is a postback that has entirely failed to have been sent to the partner.

</Accordion>

<Accordion title="Is there anything special a partner should consider about retried postbacks?">

If the postback has reached your system and has been processed successfully, but there was an error or delay in sending a response—this is considered a failed postback, and retries are sent after 15 minutes. This can cause duplication on the partner's end. The partner must implement a deduplication mechanism on their end.

</Accordion>

<Accordion title="Are postback retries automatically enabled for all partners?">

No. If a partner wants to retry failed postbacks, they should reach out to their PDM to enable this feature.

</Accordion>
