---
title: 'Bulletin: Engagement types'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-15T10:50:04Z'
  edited_at: '2026-08-13T13:34:31Z'
  id: 20161875390865
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/20161875390865-Bulletin-Engagement-types
---
<Table>
  <thead>
    <tr>
      <th>
        Section
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        **What's new**
      </td>
      <td>
        New fields have been added to the raw data reports.<ul><li>engagement\_type</li><li>contributor1\_engagement\_type</li><li>contributor2\_engagement\_type</li><li>contributor3\_engagement\_type</li></ul>These parameters can return the following values: preload, click\_to\_download, click\_to\_app, engaged\_click, engaged\_view, view, listening, or if not reported it will be empty<table><thead><tr><th></th><th></th></tr></thead><tbody><tr><td>Engagement type</td><td>Description</td></tr><tr><td>preload</td><td>The app is preloaded by the OEM at the factory or by the provider the first time the device is activated. Alternatively, a wizard prompts users to download the app when the device is first activated.</td></tr><tr><td>click\_to\_download</td><td>When the user engages with an ad, the app is automatically downloaded and installed on the device without redirecting to an app store.</td></tr><tr><td>click\_to\_app</td><td>An ad click, QR code scan, deep link, or any other click that redirects the user to the app or to the relevant app store to download the app.</td></tr><tr><td>engaged\_click</td><td>A click that keeps the user in the same context, engaging with the ad, and does NOT direct that user to the app store or to launch the app.</td></tr><tr><td>engaged\_view</td><td>An engaged view is when a meaningful view takes place. Some examples are when a user watches at least 10 seconds or more of a skippable video ad or a video completion</td></tr><tr><td>view</td><td>An ad view is when an ad is rendered, and an impression takes place. Some examples are banners, interstitials, or non-engaged videos.</td></tr><tr><td>listening</td><td>Listening is when a user listens to an audio ad, such as a podcast ad.</td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        **Effective date**
      </td>
      <td>
        January 17, 2024
      </td>
    </tr>
    <tr>
      <td>
        **What this impacts**
      </td>
      <td>
        <ul><li>Advertisers and agencies with access to raw data reports working with Ad networks who report these fields.<ul><li>Preload and click\_to\_app for deep links will be populated by AppsFlyer regardless of whether the Ad networks report the fields.</li></ul></li><li>The raw data reports it affects are: Data Locker, Pull API, Export Page, and Push API.<ul><li>These fields are not selected by default (with the exception of the select all in Push API), to use these fields you must manually select them in the raw data product.</li></ul></li></ul>
      </td>
    </tr>
  </tbody>
</Table>