---
title: "Postback retries"
excerpt: "Learn how postback retries work in AppsFlyer and how integrated partners can configure their postback mechanisms."
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