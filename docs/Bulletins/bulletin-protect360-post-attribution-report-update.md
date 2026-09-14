---
title: "Bulletin: Protect360 post-attribution report update"
excerpt: "Protect360 post-attribution reports now display the valid contributor (media source) for hijacked installs and in-app events to assist with reconciliation."
---
Protect360 post-attribution reports display the valid contributor (media source) for hijacked installs and in-app events. Meaning, the contributor that should have originally received attribution.

| | |
| --- | --- |
| **What's new** | Protect360 post-attribution reports display the valid contributor (media source) for hijacked installs and in-app events. Meaning, the contributor that should have originally received attribution. |
| **Effective Date** | November 23, 2020 |
| **Where** | Protect360 post-attribution raw data reports via:<br>- Export data (download) raw data reports<br>- Pull API raw data reports |
| **What** | - Until now, post-attribution reports did not display the valid contributor media source. The **contributor[1-3]** and **organic** fields displayed contributing media sources, but do not let you know which of them warranted attribution. <br>- Starting from November 23, 2020, the **rejected\_reason\_value** field value displays either **contributor[1-3]** or **organic**. - In Data Locker, this is the **validation\_reason\_value**.<br>- Advertisers can check the **contributor[1-3]** fields to see what the attributed media source should be and use this information for reconciliation. - If the contributor fields are not displayed in your report, they are available to be added from the **Export data** page. |

<Cards>
  <Card title="Post-attribution reports" href="https://support.appsflyer.com/hc/articles/360015179337#postattribution-reports">
    Learn more about post-attribution reports and how they are structured.
  </Card>
  <Card title="Pull API reports" href="https://support.appsflyer.com/hc/articles/360015179337#pull-api">
    Access raw data reports programmatically using the Pull API.
  </Card>
  <Card title="Rejected_reason_value" href="https://support.appsflyer.com/hc/articles/208387843-Raw-data-field-dictionary-V5-0-spec-#protect360::440536f1">
    View the raw data field dictionary specification for rejected reason values.
  </Card>
  <Card title="Contributor[1-3]" href="https://support.appsflyer.com/hc/articles/208387843-Raw-data-field-dictionary-V5-0-spec-#attribution::f1c497c7">
    View the raw data field dictionary specification for contributor fields.
  </Card>
  <Card title="What's new in AppsFlyer" href="https://support.appsflyer.com/hc/articles/360003083598">
    Stay up to date with the latest product updates and announcements.
  </Card>
</Cards>