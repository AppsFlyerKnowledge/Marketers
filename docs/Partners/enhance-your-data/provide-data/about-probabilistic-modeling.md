---
title: "About probabilistic modeling"
excerpt: "Learn how AppsFlyer uses probabilistic modeling as a privacy-preserving statistical method to attribute campaigns when deterministic signals are unavailable."
---
AppsFlyer uses probabilistic modeling as a privacy-preserving statistical method to report on how app developers’ marketing campaigns are performing. It produces aggregate campaign-level performance reports for app developers.

**Implementation characteristics**

- Uses statistics and is not based on unique IDs.
- It is a fallback method used when a referer or advertising IDs are unavailable. Deterministic attribution methods, i.e., clicks with referrer or ID matching, are given priority if they occur within the lookback window.

### When is probabilistic modeling used?

Except where otherwise configured by the customer, probabilistic modeling will apply in cases where deterministic data is unavailable, including:

- Web-to-app conversions
- Cross-device experiences (for example, a desktop ad followed by a mobile install)
- CTV, PC, or console environments where deterministic attribution isn’t possible