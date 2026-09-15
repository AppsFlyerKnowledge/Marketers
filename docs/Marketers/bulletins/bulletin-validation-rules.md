---
title: "Bulletin: Validation Rules"
excerpt: "An overview of the updated layout, features, and raw data reporting changes for AppsFlyer Validation Rules."
---
| **What's new** | Validation Rules page has a new layout and increased functionality.<br>! |
| --- | --- |
| **Where** | - Validation Rules page <br>- Raw data reports<br>- Rejection postbacks |
| **Required actions** | - **Who:** Advertisers<br>- **What:**  - Familiarize yourself with the new layout and features.<br>  - **No action is required for existing rules; they are automatically migrated.**<br>  - Advertisers with the Protect360 Premium plan should use Protect360 fraud reports for installs, in-app events, and install postbacks, instead of the Targeting validation rules reports. |
| **Effective Date** | December 7, 2020 |
| **Highlights** | Starting on the effective date, the new layout and functionality becomes available.

Changes:

- **Rules list**: The rules page lists all the rules contained in your account.
- **Rule builder**:   - Multiple rule combinations are allowed.
  - Rules can be applied to single or multiple apps.
  - Rules can be applied to all sources of traffic: Organic, non-organic, agency, SRN, etc.
  - One rule builder for campaign targeting rules and Protect360 rules (additional options available for Protect360 customers).
  - Protect360 customers can also create rules to block in-app events.
  - New rule conditions are available.
  - New options for rules to either block installs or block attribution.
  - Installs/in-app events can be blocked by multiple rules.
- **Raw data reports**:


| Targeting validation rules reports | Where data is now available | |
| --- | --- | --- |
| | With Protect360 Premium plan | Without Protect360 Premium plan |
| Invalid installs | Protect360 installs raw data report | Protect360 installs raw data report |
| Invalid in-app events | Protect360 in-app events raw data report | - |
| Invalid install postbacks | Protect360 blocked install postback report | Protect360 blocked install postback report |

  - Raw data reports contain the rule name entered by the rule creator/editor as the blocked\_reason\_value; not the rule ID.
- **Postbacks**: Contain the rule name entered by the rule creator/editor as the blocked\_reason\_value; not the rule ID. |
| **What you must know** | - Ad networks and agencies need [permissions](https://support.appsflyer.com/hc/articles/4410395957521#permissions-tab) to access raw data reports.<br>- Ad networks and agencies of non-Protect360 customers are not able to access the Protect360 dashboards to view validation rule data.<br>- Rules with a **CTIT** condition, are changed during migration to **CTIT** AND **is\_preinstalled=no** AND **is\_deeplink=no**. |

<Cards>
  <Card title="Validation Rules for app owners" href="https://support.appsflyer.com/hc/articles/115004703926">
    Learn how to configure and manage validation rules for your applications.
  </Card>
  <Card title="What's new in AppsFlyer" href="https://support.appsflyer.com/hc/articles/360003083598">
    Stay up to date with the latest features and product updates across AppsFlyer.
  </Card>
</Cards>