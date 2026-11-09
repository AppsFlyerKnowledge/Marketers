---
title: '[Beta] Agent Hub overview'
metadata:
  keywords:
    - Advertisers
    - Beta feature
    - Marketers
    - Agent Hub
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agent Hub
  created_at: '2025-11-16T10:18:23Z'
  edited_at: '2026-10-26T09:09:52Z'
  id: 40967933109649
  locale: en-us
  section: AI
  section_id: 36348470056081
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/40967933109649--Beta-Agent-Hub-overview
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **At a glance:** Agent Hub is AppsFlyer's centralized platform for managing AI-driven agents that proactively deliver actionable marketing insights directly into your workflow. These agents constantly analyze your data to deliver valuable outputs and recommend actionable steps, all within your team's collaborative environment.

<Embed title="[Beta] Agent Hub overview" typeOfEmbed="youtube" url="https://www.youtube.com/embed/LEuqdVEXBD0" providerUrl="https://www.youtube.com" />

## About Agent Hub

Each agent takes on a marketing job end to end: it works through your data, reaches its findings, and delivers them where your team works. Agent Hub gives you access to a variety of AppsFlyer-built agents designed to help you optimize marketing activity and uncover growth opportunities, plus Custom Agent, which takes on a job you define yourself. Every agent operates with integrity to support your team's decision-making.

## Agent Hub page

Agent Hub page is made up of two tabs: **My Agents** and **Activity**. Use these tabs to manage agents and review completed agent runs.

Use **My Agents** to set up, deploy, and manage agents. Use **Activity** to review completed outputs, see previous runs, provide feedback, and analyze run reasoning with AI Assistant.

<Accordion title="My Agents">

The **My Agents** tab shows the agents available to your account.

Use this tab to:

* View available agents.
* Set up and deploy agents.
* Manage deployed agents.
* Monitor the latest run status from the agent card.

#### Prerequisites and permissions

Some Agent Hub capabilities require additional setup, depending on the notification channels you use.

##### Slack (optional)

Slack setup is required only if you want to receive agent output in Slack.

* Approval of the AppsFlyer Slack app by your organization. To do this:
  * Go to the Agent hub and select the agent you want to use.
  * Click **Connect to Slack** within the agent configuration card.

For agents that send output to Slack, you must first create a dedicated Slack channel within your organization and invite the AppsFlyer Agent Hub Slack app to that channel before the agent setup. The name of the channel is required as part of the agent setup.

To invite an app to a channel:

1. In the Slack channel you want to receive the notifications to, write: **/invite**
2. Choose **Add Apps to this channel.**

<Image align="center" alt="Add Apps to this channel option in the Slack channel details menu" src="https://files.readme.io/6f4f06ff2a6871c38ab74347b05356b5482a859b3f40b02f01273abd3a10ee84-40967906089745.png" width="624px" />

Select **AppsFlyer Agent Hub** -> **Add.**

<Image align="center" alt="AppsFlyer Agent Hub app selected in the Slack app directory with the Add button" src="https://files.readme.io/6290174c2950340f7766abb94f0080dbbcbd954cc44896a0f0ec1155fdd00524-40967906092049.png" width="624px" />

* The following roles have automatic full access:
  * Admin
  * Marketing manager
  * Team manager
  * Marketing lead

* **Other roles:** Require the AI Tools capability enabled through <Anchor target="_blank" href="/marketers/vi/docs/user-management">User Management</Anchor>.

##### Email (optional)

* Emails can only be sent to email addresses that are connected to an AppsFlyer account.
* Users must be subscribed to the AppsFlyer mailing list. <Anchor target="_blank" href="/marketers/vi/docs/notifications#what-notifications-can-i-receive">See here for more information</Anchor>.

Note: In each agent, you can configure up to 5 email addresses.

#### Set up an agent

Agents can be set up and deployed to run on a schedule or manually. You can also configure where agent output is delivered, such as Slack or Email.

You can monitor the status of the latest run directly from the agent card in the **My Agents** tab. To view completed outputs and historical runs, click the **Activity** tab.

Follow the steps below to set up and deploy an agent.

1. Log in to AppsFlyer.
2. From the left-hand menu, go to **Agent Hub.**
3. On the agent you want to set up and deploy, click **Deploy**.
4. On the following page, configure the required agent settings.
5. Add your email address or connect your Slack workspace if relevant.
   1. Make sure that the Slack channel has been set up. [See prerequisites](#prerequisites-and-permissions).
6. Select a run schedule (currently based on UTC; additional time zones will be added soon).
7. Click **Deploy Agent**.

The agent appears under **My Agents**. See **Prebuilt agents** and **Custom Agent** below for the full list of available agents, and what each one does.

</Accordion>

<Accordion title="Activity tab">

**Activity** tab shows completed agent run outputs. It appears when your account has at least one agent with completed outputs.

Use this tab to review recent agent activity, view previous outputs, provide feedback, and ask AI Assistant questions about a specific run.

The Activity tab includes two sections:

| Section | Description |
| --- | --- |
| Latest activity | Shows the latest completed run for each agent instance. |
| Previous runs | Shows completed runs from the last 30 days. |

You can filter activity by:

* App
* Agent instance

Note: The agent filter is based on the specific agent instance, not the agent type.

#### View activity output

To view activity output:

1. Go to **Agent Hub**.
2. Click the **Activity** tab.
3. Select the relevant app or agent instance filters.
4. Click a run to expand it.

The expanded run shows the same output sent by Slack or email.

From the expanded run, you can:

* Copy the output.
* Provide positive or negative feedback.
* Add written feedback.
* Click **Analyze activity** to ask AI Assistant questions about the run.

#### Analyze activity with AI Assistant

Use **Analyze activity** to ask AI Assistant questions about a specific completed agent run.

**Analyze activity** is available for all agents. AI Assistant opens in the context of the selected run. It can help you understand how the agent reached its output, what data it used, and which factors it considered or ruled out.

This isn't a general chat with the agent. AI Assistant answers questions about the selected run only. It doesn't perform new agent work, access data outside the run, or make predictions.

To ask AI Assistant questions about a run:

1. Go to **Agent Hub**.
2. Click the **Activity** tab.
3. Click a run to expand it.
4. Click **Analyze activity**.
5. Select a suggested question or enter your own question.

For example, you can ask:

* Walk me through your reasoning.
* What data was this based on?
* Why was this finding prioritized?
* What factors did the agent consider?
* What factors did the agent rule out?

##### Supported and unsupported questions

| You can ask about | You can't ask about |
| --- | --- |
| How the agent reached its output | Data that wasn't included in the run |
| What data the agent used for the run | New analysis that wasn't part of the run |
| Why findings were prioritized or ruled out | Forward-looking predictions |
| The context and reasoning of the selected run | General optimization recommendations outside the run context |

#### Notes

Keep the following in mind when using the **Activity** tab and **Analyze activity**:

* AI Assistant must be enabled for the account. If AI Assistant is disabled, **Analyze activity** isn't available. See <Anchor target="_blank" href="/marketers/vi/docs/account-settings#agent-hub">Account Settings</Anchor>.
* Activity history includes completed runs from the last 30 days only.
* Deleting an agent also deletes its previous activity, including outputs, findings, and reasoning data. This action can't be undone.
* AI Assistant answers questions about the selected run only. It doesn't perform new analysis, access data outside the run, or make predictions.

</Accordion>

## Agent types

Agent Hub includes two kinds of agents: Custom Agent, which you configure yourself for a job you define, and ready-to-use agents you deploy as they are.

<div id="h_01M3PDTFQDFQNMHTWKP23JV1A8" />

<Accordion title="[Closed beta] Custom Agent">

While ready-to-use agents in Agent Hub carry out specific, predefined tasks, Custom Agent executes a job you tailor to your specific requirements. Write the task in plain language, pick the app, review the plan the agent drafts, and choose how and when you want results delivered. The agent then does the work end to end, on demand or on a schedule, and sends you the output.

It analyzes the data, executes the specified task, and delivers the requested results. That could be a ranked list, a weekly performance summary, a root-cause investigation, a recommendation with the evidence behind it, or a complex ad hoc analysis. The output takes whatever shape the job needs.

You brief it the way you'd brief an analyst on your team, and it works the same way: it confirms what it understood, shows you how it plans to approach the job and how it defines each term, and only runs once you've agreed.

#### Create a Custom Agent

Three steps: define the agent, review the plan, then configure and deploy.

##### Step 1: Define the agent

1. In AppsFlyer, go to **Agent Hub** in the left-hand menu.
2. On the Custom Agent card, click **Create**.
3. Under **Select your app**, select the app. One app per agent.
4. (Optional) Set **Geo** and **Media source** filters. Leave them empty to include everything.
5. In **Task**, describe the job, or click a ready-to-use prompt and edit it to suit your needs.
6. Click **Generate plan**.

##### Step 2: Review the agent plan

The agent turns your task into a plan and shows it to you before running anything. This is where you catch a misread task or a definition that doesn't match how your team measures.

| Plan section | What to check |
| --- | --- |
| Goal | One-line restatement of the job. |
| Agent plan | How the agent will carry out the job. |
| Definitions | Every metric, window, and threshold from your task, spelled out: what "Day-7 retention" means, what "significant decline" means, which media sources are in scope. Edit anything that differs from your own definitions. |
| Filters | The app, geo, and media source the agent will apply. |

From here:

* **Edit** changes any field, then **Save changes**.
* **Start over** returns you to the task.
* **Accept plan** moves you on.

##### Step 3: Configure and deploy

1. Enter an **Agent name**.
2. Under **Select how you want to receive the results**, select **Slack**, **Email**, or both.
   * Slack: click **Connect to Slack** if the workspace isn't connected yet, then select the channel.
   * Email: up to five addresses of AppsFlyer users.
3. Under **Run schedule**, select one of the options.
4. Click **Deploy agent**.

Schedules run in UTC.

The agent appears under **My Agents**. The card shows the latest run status. Completed runs are in **Activity**, filterable by app and agent name.

<div id="h_01M3PDTFQESQY349XK0SNH5NB8" />

<Accordion title="What data Custom Agent works on">

Custom Agent has two data sources, event-level and aggregated data, and picks between them based on the task; you don't need to specify. For some tasks, the agent uses both sources in a single run. In those rare cases, the same metric can show slightly different values across the two parts of a run. To understand which source the agent used during a run, explore the agent's reasoning using the **Analyze activity** feature.

**Event-level data.** Raw events across the funnel, from engagement to in-app activity. This is what makes Custom Agent different from a dashboard: you can define your own metrics and ratios, work at the individual-user level, and trace event sequences.

| Included | Details |
| --- | --- |
| Engagements | Clicks and impressions |
| Installs and re-engagements | Conversions |
| Sessions | App open events |
| In-app events | Including in-app purchase revenue |
| Dimensions | Media source, campaign, geo down to city, device, OS version, app version, ad, site ID, and other raw-event fields |
| Data timeframe | Last 30 days |

**Activity and Cohort data (aggregated).** All data points available in My Dashboards, including cost.

| Included | Details |
| --- | --- |
| Metrics | Installs, conversions, first visits, sessions, event count, unique users, active users, revenue, net revenue, average revenue per user (ARPU), revenue per unique user, count per unique user, retention rate |
| In-app events, conversions, uninstalls, sessions | Count, unique users, revenue, net revenue, first event count |
| Cost metrics | Spend (cost), eCPI, ROAS, ROI |
| Dimensions | Media source, channel, campaign ID and name, ad set ID and name, ad ID and name, site ID, agency, keywords, sub\_param\_1, engagement category and type and destination, unified app ID, platform, install app store, app version and OS version and country code (conversion), aggregated event type (conversion, session, in-app, uninstall), event name, conversion name and type, monetization type, is-attributed, is-organic, is-primary-attribution, event date (Cohort only), event date (conversion), days post conversion, customer currency |
| Data timeframe | Three years for Activity, two years for Cohort |

Aggregated data is in USD and your account currency. Cohorted aggregated data has daily granularity.

**Current limitations.** These limitations are temporary and will evolve as Custom Agent moves out of beta.

* Engagement and cost live in different sources. Clicks and impressions exist only in event-level data; cost exists only in aggregated data. The agent can't join the two, so metrics that combine them, such as CPC, CPM, CTR, IPM, and CPA, return no results. Cost-based metrics that don't need engagement data (spend, eCPI, ROAS, ROI) work as expected.
* Missing data: data generated by Audiences, SKAdNetwork, SSOT, Protect360, Creative, and Incrementality; ad revenue and subscription revenue (revenue covers in-app purchases only).
* Custom metrics or dimensions you've defined in your dashboards aren't included.
* Aggregated dimensions include data only from June 2025 onward for platform, sub\_param\_1, engagement destination, engagement type, and source (organic vs. non-organic).
* When there's no data, the agent shows 0, not N/A.
* "First visits" and "re-visits" are available only for web apps.

> 📘 **Note**
>
> Discrepancies can occur between raw event figures and dashboard data. Event-level figures (raw data) and aggregated (dashboard) figures won't always match; small gaps between the two are expected. Aggregated figures should match My Dashboards for the same app and dates.

</Accordion>

<div id="h_01M3PDTFQEF8ZPV4PP04YGNGBK" />

<Accordion title="Write a good task">

The plan the agent drafts is only as good as the brief. Include as much of this as applies:

1. **The job.** What you want done, in plain language. Verbs help: compare, rank, flag, find, recommend, summarize.
2. **Timeframe.** A defined window, for example "the last full week" or "last 14 days versus the prior 14." Leave out today; its data is still partial.
3. **Scope.** The geo, media source, campaign, or platform that matters. You can also set geo and media source as filters above the task box.
4. **Metrics and thresholds.** Name your KPIs and how you define them. "A drop of more than 10% versus the prior week counts as significant" gives the agent a rule it can apply.
5. **Output you want.** If it matters, say so: "a table sorted by spend," "a short summary with the top three findings," or "flag only, no narrative."
6. **Why.** One line of context helps the agent decide what to prioritize.

See **Prerequisites and permissions** above for setup details.

</Accordion>

<div id="h_01M3PDTFQE6GP95M541FYHG15N" />

<Accordion title="Review and refine a run">

Completed runs appear in **Activity** with the same content sent to Slack or email. From a run, you can copy the output, give a thumbs up or down, add written feedback, and open [Analyze activity](#analyze-activity-with-ai-assistant) to ask AI Assistant how the agent got to its result.

If a run comes back empty or off-target, read the reasoning before changing the task. In [Analyze activity](#analyze-activity-with-ai-assistant), ask what data the agent used, why it reached that result, and what to change in the plan. Rewriting the task blind usually produces a different wrong answer. Then edit the plan or task and run the agent again.

If the reasoning also comes back empty, you might have requested data that doesn't yet exist. See **Limitations** above, revise the prompt, and try again.

> 📘 **Note**
>
> You can't return to your original prompt once you save and deploy an agent. You can only edit the approved agent plan.

See [Agent Hub page](#agent-hub-page) and [Analyze activity with AI Assistant](#analyze-activity-with-ai-assistant) above for more detail.

</Accordion>

<div id="h_01M3PDTFQE2XA949N4GPBSHVKY" />

<Accordion title="Manage a Custom Agent">

From the agent card under **My Agents**, you can run the agent now, edit its configuration (name, delivery, schedule), or delete it.

Deleting an agent also deletes its history, including outputs and reasoning. This action can't be undone.

</Accordion>

<div id="h_01M3PDTFQEENY4TB2QY7M1MPN9" />

<Accordion title="Good to know">

* One app per agent. Create a separate agent for each app.
* Activity keeps runs from the last 30 days.

</Accordion>

</Accordion>

<div id="h_01M3PDTFQEDCZ7AJFC1FCTHERZ" />

<Accordion title="Ready-to-use agents">

Ready-to-use agents are ready to deploy as they are: pick one, configure it, and let it run on your data. The table below lists what each agent does at a glance. Expand a section for the full detail before you deploy.

<div id="h_01M3PDTFQET68PRA9CN49CQ8Q7" />

<Accordion title="Spot Creative Opportunities">

**Job.** Finds the creatives that are performing best for you and tells you where they aren't running yet. The agent evaluates creative performance across all your partners over the past 30 days, ranks the winners, and then checks each partner to see which of those winners are missing. You get a list of concrete placements to add, with the numbers behind each.

**What it works on.** Creative-level spend and ROAS across partners, over the past 30 days. Requires Creative optimization.

**What a run delivers.** Top-performing creatives with their spend and ROAS, plus, for each partner, which of these creatives aren't currently running and the case for adding them. Delivered to Slack or email.

**Cadence.** Configurable via the standard schedule options or on demand.

</Accordion>

<div id="h_01M3PDTFQE2WB2SNWBCS81C2DE" />

<Accordion title="Custom Executive Summaries">

**Job.** Writes the performance update you'd otherwise assemble by hand for managers and stakeholders. The agent reads your aggregated analytics, identifies the trends, top performers, and changes that matter for the period, and turns them into a summary with recommendations, ready to forward.

**What it works on.** Aggregated analytics data across your apps and media sources. No premium subscription required.

**What a run delivers.** A written summary: headline trends, top and bottom performers, notable shifts, and recommended next steps. Delivered to Slack or email.

**Cadence.** Configurable via the standard schedule options or on demand.

</Accordion>

<div id="h_01M3PDTFQEB9MKH44X5XX4AGDT" />

<Accordion title="Deep Research Analysis">

**Job.** Runs a weekly investigation into what changed and why. Every Monday, the agent compares the two most recent complete weeks (Monday to Sunday) and digs through raw event-level data, across partners, geos, OS versions, and SDK versions, to find shifts that aggregated dashboards can't show, including setup problems that look like performance changes.

**What it works on.** Raw, mature event-level data. The agent deliberately excludes the current week to avoid partial or immature data. For example, on Monday, January 26, it compares January 12–18 against January 5–11. No premium subscription required.

**What a run delivers.** A written report of meaningful week-over-week shifts, what's driving them, and setup issues uncovered along the way. Delivered to Slack or email.

**Cadence.** Weekly, on Mondays or on demand.

</Accordion>

<div id="h_01M3PDTFQEPFMS38RWXT923VX7" />

<Accordion title="Detect Performance Anomalies">

**Job.** Watches your key KPIs every day and tells you when something moves that shouldn't have. The agent compares each metric to its expected range, flags significant positive or negative anomalies, and explains what changed and where: a CPI spike on one partner, an IPM drop in a geo, or a campaign that fell off a cliff.

**What it works on.** Daily KPI data across partners, campaigns, and geos. No premium subscription required.

**What a run delivers.** Story-style alerts: which metric moved, by how much, on which partner, campaign, or geo, and the likely reason. Delivered to Slack or email.

**Cadence.** Configurable via the standard schedule options or on demand.

</Accordion>

<div id="h_01M3PDTFQEFHYR29GN1XMRM16N" />

<Accordion title="Detect Configuration Issues">

**Job.** Audits your measurement setup and alerts you to gaps that quietly degrade data quality. The agent checks for inactive integrations in SKAdNetwork and Cost, disabled view-through attribution via probabilistic modeling, and other configuration problems, so you catch them before they distort a campaign read.

**What it works on.** Integration and configuration status across your apps and partners. No premium subscription required.

**What a run delivers.** Alerts listing each issue found, where it is, and how to remediate it. Delivered to Slack or email.

**Cadence.** Configurable via the standard schedule options or on demand.

</Accordion>

<div id="h_01M3PDTFQEP6E7D4TF5G4PX1KV" />

<Accordion title="Monitor App Releases">

**Job.** Keeps you informed about your own app's releases without waiting on the dev team. The agent watches iOS and Android app store releases, alerts you when a version goes live, tracks rollout progress, and calls out the marketing-relevant changes: new features, changed in-app behavior, and events added or removed. That lets you align UA campaigns with what's actually in the app.

**What it works on.** App store release data and in-app event definitions for your apps. No premium subscription required.

**What a run delivers.** Release alerts with version, rollout status, and a summary of marketing-relevant changes. Delivered to Slack or email.

**Cadence.** Configurable via the standard schedule options or on demand.

</Accordion>

<div id="h_01M3PDTFQEEKJQTRKEC9GK4TE6" />

<Accordion title="Optimize Anti-Fraud Strategy (Protect360)">

**Job.** Looks for early signs of fraud in your traffic and tells you what to do about it. The agent scans your Protect360 data for emerging patterns, reports key findings, and recommends actions that cut fraud exposure without sacrificing performance.

**What it works on.** Protect360 data. Requires Protect360 and Protect360 closed beta features.

**What a run delivers.** Findings and recommendations inside the Protect360 dashboard.

**Cadence.** Weekly, on Mondays, or on demand.

</Accordion>

<div id="h_01M57AQ8G83P5H1JDJ4FM9ETCV" />

<Accordion title="Measure UA Incrementality">

**Job.** The **Measure UA Incrementality** agent guides you through the full incrementality-testing lifecycle so you don't have to be an expert to run it. It defines what to test, explains what your experiment results mean, and recommends concrete marketing actions — turning a steep, specialist learning curve into a guided workflow aimed to measure the causal impact of your paid UA spend: which installs or events happened because of your ads, versus growth you'd have captured anyway.

**What it works on.** Installs, in-app events, revenue and cost data from the last 90 days; All Incrementality for UA experiment data.

**What a run delivers.** A structured report in three parts: (1) your current UA state and analysis of any active or completed experiments, (2) a sequenced testing plan that defines what to test next and why it matters for your budget, and (3) recommended marketing actions — grow, hold, cut, or re-test.

**Cadence.** Runs on a schedule, weekly by default. You can increase it to as often as daily, or trigger it ad-hoc for a fresh read whenever you need one.

**Set up.** Requires an Incrementality for UA premium product subscription. Launch the agent from the Agent Hub and select an app, country, and success metric, then set your cadence (or run it ad-hoc); The agent inherits any existing Incrementality for UA geo design policy.

**Good to know.** The agent recommends — it never moves budget or launches an experiment on its own, you approve and act. Agents are app, country and event specific. For example, your Android and iOS apps would require two separate agents. As with any AI output, always validate before acting.

</Accordion>

<div id="h_01M3PDTFQEP2RQW39AD8127J19" />

<Accordion title="Web health check">

**Job.** Audits how your web app collects events and attributes conversions to marketing sources. The report shows what's working, flags issues that could make attribution inaccurate, and recommends improvements to your implementation.

**What it works on.** Your selected web app's attribution settings and recent SDK or server-to-server data. Checks cover data collection, events and revenue, campaign links, referrers, identity, and cross-platform setup. The default analysis window is seven days.

**What a run delivers.** One report with two sections: what was checked and looks good, and recommended improvements. Findings include supporting numbers, a recommended fix, and a green, yellow, or red status based on impact.

**Cadence.** Configurable via the standard schedule options or on demand.

</Accordion>

<div id="h_01M5VP47MCYYQVP89CJN9KZ4BP" />

<Accordion title="[Closed beta] Optimize Apple Ads Share of Voice">

**Job.** Keeps your Apple Ads Share of Voice (SoV) on your key keywords inside the range you set, without overpaying. SoV, also called impression share, is the percentage of eligible searches for a keyword where your ad appeared. When a keyword is off target, the agent recommends a bid change: raise the maximum cost-per-tap (max CPT) bid to recover share, or lower it to stop overpaying.

**How the agent checks your SoV.** Apple reports SoV with a one-day delay, but the auction changes during the day. To close the gap, the agent estimates your SoV every hour from today's delivery data. It calibrates the estimate against Apple's official SoV from the day before. You hear about changes within hours.

**What it works on.** Hourly keyword-level Apple Ads data (impressions, taps, spend, and current max CPT bid) and Apple's daily impression share report. The agent pulls both through your Apple Ads connection in **Cost Settings** and uses the last 30 days as history. Requires ROI360.

**What a run delivers.** For each keyword and geo outside the target range, a run delivers:

* Apple's latest SoV range and whether the keyword is above or below target.
* The recommended bid change in %.
* The exact current and recommended max CPT bid for each campaign and ad group where the keyword runs.

Keywords that are on target or have no recommendation yet are listed at the end. Delivered to Slack or email, and to the **Activity** tab.

**Apply a recommendation.** In the **Activity** tab, each bid change appears as a card. Click **Apply** to send the recommended bid to Apple Ads, edit the bid and then click **Apply**, or click **Reject**. Nothing changes in Apple Ads until you apply a recommendation.

**Cadence.** The run schedule options are:

* **On trigger:** The agent sends a message only when there's a new or changed recommendation. How often it checks depends on how the agent checks your SoV. See **How the agent checks your SoV** in this section.
* **No schedule:** The agent runs only when you run it manually.

**Set up. To deploy the agent:**

1. In **Cost Settings**, connect Apple Ads with the account that runs your keywords.

   > 📘 **Note**
   >
   > Connect Apple Ads with **Read & Write** permissions and a non-agency account. Read & Write lets you apply bid changes directly from Agent Hub. With Read only access, you get recommendations but can't apply them. You need to change bids manually in Apple Ads.

2. In **Agent Hub**, on the **Optimize Apple Ads Share of Voice** card, click **Deploy Agent**.
3. Enter an **Agent Name**, or keep the prefilled name.
4. Under **Select your iOS app**, select the app. One app per agent.
5. Under **Keywords**, enter at least one and up to three keywords, as they're set up in your Apple Ads campaigns.
6. Under **Apple Ads geo**, select up to five geos.
7. Under **Target Share of Voice range**, select the range, for example 81-90%.
8. Under **Select how you want to receive the results**, select **Slack**, **Email**, or both.
9. Under **Run Schedule**, select **On trigger** or **No schedule**.
10. Click **Deploy Agent**.

**No recommendation yet.** A keyword and geo can show this status in two cases:

* There isn't enough data. For example, the keyword has low search volume and Apple doesn't report SoV for it, or the keyword doesn't run in this geo.
* The bid changed recently. The agent waits to see the effect of the change before it recommends again.

**Limitations.** Keep these limitations in mind:

* **First run is the next day.** After you deploy a new agent, it backfills 30 days of history the next morning (UTC). The agent starts running only after the backfill is done.
* **Apple Ads connection.** The Apple Ads connection in **Cost Settings** must be a non-agency account. Applying bid changes requires Read & Write permissions.
* **Automated bidding isn't supported.** If a campaign uses automated bidding on the Apple Ads side, its keywords have no manual max CPT bid. The agent can't recommend or apply a bid change for them.
* **Use single-geo campaigns.** Apple Ads sets one bid per keyword per ad group, for all countries the campaign targets. If a campaign targets several countries, a bid change for one geo also changes it for the others. The recommendation might not be accurate.
* **Scope per agent.** One app, up to three keywords, and up to five geos. Create more agents for more keywords or geos.

**Good to know.** The agent never changes a bid on its own. You approve each change. As with any AI output, validate recommendations before you apply them.

</Accordion>

</Accordion>

<Accordion title="Can I create my own agents?">

Yes. Custom Agent lets you define the job you want done. See **Custom Agent** above.

</Accordion>

<Accordion title="Is Agent Hub available to all account types?">

No. Agent Hub is currently available only to advertisers.

</Accordion>

<Accordion title="Are all agents available to everyone?">

Agent availability varies based on your AppsFlyer subscription and access to premium products. Contact your CSM for specific details.

</Accordion>

<Accordion title="Can admins disable Agent Hub for the account?">

Yes. Admins can manage Agent Hub availability in **Account settings > AI capabilities**.

By default, Agent Hub is available for the account.

If an admin disables Agent Hub:

* All users lose access to Agent Hub.
* All existing agents are permanently deleted and can't be restored.
* Any active agent runs stop.

If an admin enables Agent Hub again later, users can access it again, but they must create and deploy agents from scratch.

See <Anchor target="_blank" href="/marketers/vi/docs/account-settings#agent-hub">Account settings</Anchor> for more information.

</Accordion>

<Accordion title="Where can I get notifications sent to?">

You can receive notifications via email or Slack. Email notifications require you to subscribe to AI capabilities notifications in the Notification Center.

</Accordion>

<Accordion title="Why am I not receiving Agent Hub email notifications?">

If you completed the email notification prerequisites but still don't receive Agent Hub emails, you might have previously unsubscribed from AppsFlyer emails. Contact AppsFlyer Support for assistance.

</Accordion>

<Accordion title="Does AppsFlyer train AI models on my data?">

No. AppsFlyer doesn't use your data to train any AI models. AI can produce inaccurate or incomplete results, so review outputs before acting on them.

</Accordion>

<div data-zendesk-anchors="h_01KA62R2NX6YEFMVG0SN0Y7NQ9=about-agent-hub h_01KQF6P3ED1KB47THJP8J3KAE5=agent-hub-page h_01KQF8YAEDQW52YMK3W4FE2KE1=prerequisites-and-permissions h_01KQF8H9A6FPB3VVBWAAXM257W=slack-optional h_01KQF8HEEMRBFK1K54VH2YDPSC=email-optional h_01KQF8T91KTZ01YKJD8JT6G0ZJ=set-up-an-agent h_01KQF6P3EJMJDMF0BWWXQA091K=view-activity-output h_01KQF6P3EMCX0HQKPVQ89S9VGF=analyze-activity-with-ai-assistant h_01KQF6P3EPWHV7J742F3S4Q0GY=supported-and-unsupported-questions h_01KQF7NTQYDGA17KCCMTNYY72H=notes h_01M3PDTFQDAEVRHJYK4ZJXQ3DH=agent-types h_01M3PDTFQEJA8GAE579P1AZG0E=create-a-custom-agent h_01M3PDTFQECPBKDEXMQMPZJTCS=step-1-define-the-agent h_01M3PDTFQEF9QCN15FKMRST3GW=step-2-review-the-agent-plan h_01M3PDTFQE7FN9GPTJ5GEKSNVG=step-3-configure-and-deploy h_01M3PDTFQEZJGPZ0AY4ZWRDR8D=note h_01M3PDTFQENS64JZYT2Y56QMXQ=note-1 h_01M5VP47MCS7HM339EW9AT6NGG=note-2" />
