---
title: 'Bulletin: Minimum time between sessions'
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2021-01-03T11:28:55Z'
  edited_at: '2023-11-26T12:53:54Z'
  id: 360016827858
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360016827858-Bulletin-Minimum-time-between-sessions
---
<table><tbody><tr><td><p><strong>What's new</strong></p></td><td>Change in the calculation of the sessions metric</td></tr><tr><td><strong>Effective Date</strong> </td><td><span>February 15, 2021</span></td></tr><tr><td><p><strong>What's changing</strong></p><p><strong><img alt="Information_icon.png" src="https://files.readme.io/2fc0f0d0337ac9902e20f69605e25331e17a370008c72ae52a79e09d916dba21-360015660197.png"/></strong></p></td><td><p><span>The sessions metric is calculated by counting sessions reported by the SDK in the app.</span></p><p><span>Starting on the Effective Date, after the first 5 sessions, the sessions metric is calculated taking into account a minimum time between sessions timer. This means that some sessions aren't counted as illustrated in the example that follows. </span></p><p><span>The timer has a default duration of 10 minutes and the possible values are: </span><span></span></p><ul><li><span>1-60 minutes</span></li><li><span> 1-24 hours</span></li></ul><p><span><img alt="MinimumTimeBetweenSessions_us-en.jpg" src="https://files.readme.io/12bc7191a11dda474f57055a6cf5ce6bb69b3772ad33a2a0c7bfabc51e4c07ce-360015918477.jpg"/></span></p><br/><p><strong>Example: Sessions counting with a minimum time between sessions of 10 minutes.</strong></p><p><span>In this example, the sessions reporting times are stated as minutes elapsed since 00:00</span></p><table><tbody><tr><th>Example</th><th>Session reporting times</th><th>Number of sessions counted</th><th>Sessions disregarded</th></tr><tr><td>A</td><td><span>0, 10, 20, 30</span></td><td>4</td><td>None</td></tr><tr><td>B</td><td><span>0,</span> 1, 9, <span>11</span></td><td>2</td><td>1, 9</td></tr><tr><td>C</td><td><span>0</span>, <span>10</span>, 15, <span>21</span></td><td>3</td><td>15</td></tr></tbody></table><p><strong>Impact of the change</strong></p><ul><li>Expect a reduction in the sessions metric starting from the Effective Date in the Analytics tools and sessions raw data available to clients having Data Locker. <span></span></li><li>Ad network partners, if you consume the session event via postbacks expect a reduction due to this change. </li></ul></td></tr><tr><td><strong>What's staying the same</strong></td><td><p><span>Implementation of this change (using the default setting of 10 minutes) won't affect any of the following metrics:</span><span></span></p><ul><li>Metrics:<ul><li><span>Daily active users (DAU)</span></li><li><span>Monthly active users (MAU)</span></li><li><span>Retention</span></li><li><span>Loyal users using the default setting of 3 app opens</span></li></ul></li><li><span>Re-engagement conversions</span></li><li><span>Historical data (sessions) recorded before the Effective Date</span><span></span></li></ul><p><span>However, going forward consider that if the Minimum time between sessions is increased to more than one hour, and users don't open the app many times a day, then some retention metrics can be impacted. This is especially true in the case of apps where users typically open the app once a day. </span></p></td></tr><tr><td><p><strong>[Optional] Setting change</strong></p><p><strong><img alt="Action_icon.png" src="https://files.readme.io/f6066b9dee413eea63c6a0bf04b627e3cef6a6fb21a6ca23634e615d3be1950d-360015730138.png"/></strong></p></td><td><p><span>If needed, you can change the default setting of 10 minutes, to one that suits your users’ behavior and interaction style with the app.</span></p><p><strong>To change the minimum time between sessions duration:</strong></p><ol><li>In AppsFlyer. go to <strong>Configuration</strong> &gt; <strong>App settings</strong>.</li><li>Set <strong>Minimum time between sessions.</strong> </li><li>Click <strong>Save settings.</strong> <br/>The change takes effect within an hour. </li></ol></td></tr></tbody></table>