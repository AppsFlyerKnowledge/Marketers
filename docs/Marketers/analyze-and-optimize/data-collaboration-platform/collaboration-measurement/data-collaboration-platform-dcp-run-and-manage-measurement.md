---
title: "Data collaboration platform (DCP) - Run and manage measurement"
excerpt: "After you configure on-site or off-site measurement, run it as either a live measurement or a historical measurement. Choose the mode that best matches your goal: measure performance continuously or validate results for a defined period."
x-zendesk:
  id: 44427723216017
  url: https://support.appsflyer.com/hc/en-us/articles/44427723216017-Data-collaboration-platform-DCP-Run-and-manage-measurement
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Collaboration measurement
  section_id: 38034865098641
  position: 4
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-yael-sharabi, Marketers, Data Management]
  labels: []
  promoted: false
  comments_disabled: true
  created_at: '2026-03-04T10:59:23Z'
  edited_at: '2026-03-15T17:18:01Z'
---
## About the measurement run modes

After you’ve [configured the on-site or off-site measurement](/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configure-onsite-campaign-measurement), you’re ready to choose how to run the measurement.

You have two run modes available:

* **Live measurement**: Ongoing measurement that updates at regular intervals, so you can monitor performance continuously as new data is added on the live dashboard.
* **Historical measurement**: A one-time measurement over a specific date range that you can view and analyze on a historical dashboard.

### Live vs. historical measurements



| Topic | Historical measurement | Live measurement |
| --- | --- | --- |
| When it runs | **On-demand** (manual) execution | **Automated** daily execution |
| Data source | Uses **historical data uploads** | Requires **SDK/ETL setup** and runs at predefined time intervals |
| Supported source types | [Append](/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method) and [Overwrite (snapshot)](/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method) | [Append-type custom sources](/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method) |
| Time frame selection | Select a **start and end date** (from available data) | Select a **start date only** (the platform calculates the historical time frame on activation and continues accumulating data) |
| How many per measurement | Multiple | One |



### Choose the measurement you need

Use the guidance below to decide which measurement fits your goal.

**Choose live measurement if you want**

* Ongoing measurement that continues updating as new data arrives
* A dashboard you can use to monitor performance continuously
* A setup intended for longer-term, always-on measurement (not a one-time analysis)

**Choose historical measurement if you want**

* Run a one-time measurement for a specific date range.
* Analyze performance after a campaign ends.
* Run a what-if analysis by changing the lookback window to see how it affects attribution.

**Tip:** If you’re testing your setup or validating a specific period first, start with **historical measurement**. When you’re ready for ongoing monitoring, switch to **live measurement** for continuous updates.

## Run a live measurement

**Before you begin:**  [Configure the on-site or off-site measurement campaign in the Measurement settings page](/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configure-onsite-campaign-measurement).

1. In the **Measurement settings** page, click **Run now**.

   If **Run now** is disabled, your measurement tasks are incomplete. Complete all required setup tasks to run the measurement.
2. In the **Prepare to run** dialog, select **Live dashboard**.

   CALLSTART::Note::

   #### Note

   * If the measurement uses [Overwrite](/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method) sources, only the **Historical dashboard** is available. **Live dashboard** requires **Append-type** sources (or AppsFlyer SDK in-app events) to refresh automatically.
   * Only **one live measurement** can run at a time in a collaboration. If you start a new live measurement while another one is already running, you’ll be prompted to pause the existing one.CALLEND::
3. Rename the dashboard or keep the default name.
4. Select the **measurement start date**. The default is today’s date, but you can select a past date from the date picker. (You can only select dates that exist in your data sources.)
5. Click **Start** to begin the live measurement. You’ll be redirected to the collaboration measurement page.
6. On the collaboration measurement page, after the automatic validation checks complete successfully, click **Run now**.

## Run a historical measurement

**Before you begin:**  [Configure the on-site or off-site measurement campaign in the Measurement settings page](/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configure-onsite-campaign-measurement).

1. In **Measurement settings**, click **Run now**.  
   If **Run now** is disabled, your measurement tasks are incomplete. Complete all required setup tasks to run the measurement.
2. In the **Prepare to run** dialog, select **Historical Dashboard**.
3. Rename the dashboard or keep the default name.
4. Select the **measurement date range** (you can only select dates that exist in your data sources):
   * Set the **start date**.
   * Set the **end date**.
5. Click **Start** to begin the historical measurement. You’ll be redirected to the collaboration measurement page.
6. On the collaboration measurement page, after the automatic validation checks complete successfully, click **Run now**.

## Manage measurements

After you set up and run your measurement, manage it from the measurement panel of the collaboration measurement page. You can pause or restart live measurement, adjust dates, re-run historical measurements, or duplicate a measurement to create a new run.

### The Collaboration measurement page

[![](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)

#### Legend

* **A** - The measurement panel
* **B** - The selected measurement
* **C** - The Shared toggle
* **D** - The options menu.

### Pause or restart live measurement

1. Open the collaboration measurement page.
2. Select the **Live dashboard** from the measurement panel ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#the-collaboration-measurement-page)).
3. Open the options menu ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#the-collaboration-measurement-page)) and click **Measurement settings**.
4. In the **Measurement settings** page, do one of the following:
   * To **pause** live attribution, turn off **Activate measurement**, then confirm in the **Pause measurement?** dialog.
   * To **restart** live attribution, turn on **Activate measurement**.

### Change measurement start and end dates

You can change:

* The **start date** for a live measurement, or
* The **start and end dates** for a historical measurement.

To change the measurement start and end dates, follow these steps:

1. Open the collaboration measurement page.
2. Select the measurement from the measurement panel ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#the-collaboration-measurement-page)).
3. Open the options menu ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#the-collaboration-measurement-page)) and click **Measurement settings**.
4. In the **Measurement settings** page, click the pen icon.
5. Click the start or end date.
6. Select the new date from the date picker.

### Re-run a historical measurement

Re-running a historical measurement recalculates attribution using the latest data. The current results are replaced with the new results.

1. Open the collaboration measurement page.
2. Select the measurement from the measurement panel ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#the-collaboration-measurement-page)).
3. Open the options menu ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#the-collaboration-measurement-page)) and click **Re-run**.
4. In the prompt message, click **Re-run**.
5. On the collaboration measurement page, after the automatic validation checks complete successfully, click **Run now**.

### Duplicate a live or historical measurement

Duplicating creates a new measurement based on an existing setup. You can update the settings and run it as a new measurement.

1. Open the collaboration measurement page.
2. Select the measurement from the measurement panel ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#the-collaboration-measurement-page)).
3. Open the options menu ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#the-collaboration-measurement-page)) and click **Duplicate**.
4. In the duplicated **Measurement settings** page, customize the measurement to your needs.

### Share a dashboard

You can share a dashboard with your collaborators by turning on the **Shared** toggle. When **Shared** is ON, the dashboard (and its measurement results) is available to other users in the collaboration.

What collaborators can do, when **Shared** is ON, depends on whether they’re **assigned** to the dashboard.

* **Assigned users can:**
  * Open and **view the dashboard**
  * Open the **Measurement settings** and **edit only the tasks assigned to them.**

* **Assigned users can’t:**
  * Turn **Shared** on/off (share or unshare)
  * **Re-run** the measurement

* **Users who aren’t assigned** have more limited access, even if the dashboard is shared (for example, they may not see the results summary and can’t re-run or share).

To share a dashboard:

1. Open the collaboration measurement page and select the **dashboard** you want to share from the measurement panel ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#the-collaboration-measurement-page)).
2. Turn on **Shared** ([C](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#the-collaboration-measurement-page)). The dashboard will be available in your collaborator measurement page.
3. Turn off **Shared** to stop sharing. When sharing is turned off, only you (and users with the right permissions) can access the dashboard.