---
title: "Data Collaboration Platform (DCP) sharing permissions"
excerpt: "Define the DCP collaboration permissions that determine how your collaborator can use your shared data."
x-zendesk:
  id: 42009477902353
  url: https://support.appsflyer.com/hc/en-us/articles/42009477902353-Data-Collaboration-Platform-DCP-sharing-permissions
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Data Collaboration Platform
  section_id: 26230608274065
  position: 8
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-yael-sharabi, Marketers, Audience Activation]
  labels: [Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2025-12-17T10:36:33Z'
  edited_at: '2026-05-19T12:27:23Z'
---
This article describes the permissions available when sharing data in a Data Collaboration Platform (DCP) collaboration. Sharing permissions are defined by the **Collaboration policy** you set when [creating a collaboration](/docs/data-collaboration-platform-dcp-create-a-collaboration) and specify what collaborators can do with your data and which resources or activation partners they can use. In addition to this default policy, custom data permissions can also be set per source. The Collaboration policy defines the:

- [Data permissions](#data-permissions)
- [Access permissions](#access-permissions)

## Data permissions

The data permissions you select define how your collaborator can use your associated data and apply to all sources you associate with the collaboration. Permissions can also be modified individually per source.

![Data permissions Dec 2025.png](https://files.readme.io/1e33caebbe4a8ff14fe84be6ba7f50b82a5fe7c268ba186db0250c7084718d54-42009477892241.png)

### Data permissions include:

| Permission | Description |
| --- | --- |
| **Make visible to collaborator** | Allows the collaborator to view and use the sources you associate with the collaboration, according to the other permissions you grant. When disabled, your sources will only be visible to you. |
| **Query data** | Allows the collaborator to query the data and create aggregated reports. You can specify whether the collaborator:<br />- **Can query only intersecting data** (Overlapping dataset) - Refers to the common users of both parties.<br />  <br />  **Note:** When this option is selected, the source size is not available. <br />- **Can query all data** (Universal dataset) - Refers to all data you associate with the collaboration. |
| **Build audiences** | Allows the collaborator to use the data when building their [audiences](/docs/data-collaboration-platform-dcp-add-connections). You can specify whether the collaborator:<br />- **Can use only intersecting data** (Overlapping dataset) - Refers to the common users of both parties.<br />  <br />  **Note:** When this option is selected, the source size is not available.<br />- **Can use all data** (Universal dataset) - Refers to all data you associate with the collaboration. |
| **Partner connections** | Allows the collaborator to send the audiences created from your sources to partner connections for activation. When enabling this option, you can grant export permission for:<br />- **All connected partners**\- When selecting this option, you can also **Allow future partner connections**, which automatically allows audience export to all media partners that AppsFlyer DCP partners with.<br />- **Specific partners only**  - When selecting specific partners, you can further specify whether you allow your collaborator to use only their activation connections or yours (e.g., only their Meta connection or your Meta connection).<br />  - If you select your connections, you’ll need to choose which of your connected accounts the collaborator can use (e.g., only your Meta connection A but none of your other Meta connections).<br />**Important notes:**<br />- When your collaborators are ready to [activate audiences](/docs/data-collaboration-platform-dcp-build-and-activate-audiences#send-audience-for-activation) based on your sources, only the partner connections that you granted permissions for will be available to them.<br />- If you haven’t granted the collaborator permission to publish or export audiences, then when they attempt to activate an audience, the activation request is sent to you to complete. |
| **File export** | Allows the collaborator to export audience files to their cloud bucket. |

## Access permissions

The access permissions define the resources your collaborator can access. This includes the option to grant your collaborator access to your [Data & Identity (data resolution) connections](/docs/data-collaboration-platform-dcp-add-connections#create-data-identity-connections), enabling them to use these connections to enrich their sources.

> 📘 Note
>
> To grant access, the relevant Data & Identity connection must be active.

## Traits and limitations

This section outlines some key traits and limitations of DCP permissions.

| Trait or limitation | Details |
| --- | --- |
| **Audience behavior** | - If an audience is built from a single source → the source’s partner permissions determine which activation partners are available.<br />- If an audience is built from multiple sources with different partner permissions →<br />  <br />  The lowest common denominator applies.<br />  <br />  **Example:** Source A allows all partners, Source B allows only Meta → Only Meta will be available for activation. |
| **Changes in permissions** | **Removing activation permissions entirely:**<br />- Any existing audience using the affected source will expire.<br />- New audiences using the source will behave as today (require new activation permissions).<br />**Removing a specific partner:**<br />- If an existing audience is connected only to that removed partner → the audience will expire.<br />- If the audience is connected to multiple partners →<br />  <br />  The audience remains active, but activation with the removed partner will no longer be available. |