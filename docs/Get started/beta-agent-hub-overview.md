---
title: "[Beta] Agent Hub overview"
excerpt: "Agent Hub is AppsFlyer's centralized platform for managing AI-driven agents that proactively deliver actionable marketing insights directly into your workflow."
---
Agent Hub is AppsFlyer’s centralized platform for managing AI-driven agents that proactively deliver actionable marketing insights directly into your workflow. These agents constantly analyze your data to deliver valuable outputs and recommend actionable steps, all within your team's collaborative environment.

<Embed title="Agent Hub | Product tour" typeOfEmbed="youtube" url="https://www.youtube.com/embed/LEuqdVEXBD0" />

## About Agent Hub

Agent Hub provides access to a variety of AppsFlyer-developed agents designed to help marketers optimize marketing activity and uncover growth opportunities. Each agent utilizes AppsFlyer’s data to deliver targeted insights and recommendations while operating with integrity to support your team’s decision-making capabilities.

## Agent Hub page

Agent Hub page is made up of two tabs: **My Agents** and **Activity**. Use these tabs to manage agents and review completed agent runs.

Use **My Agents** to set up, deploy, and manage agents. Use **Activity** to review completed outputs, see previous runs, provide feedback, and analyze run reasoning with AI Assistant.

### My Agents

The **My Agents** tab shows the agents available to your account.

Use this tab to:

- View available agents.
- Set up and deploy agents.
- Manage deployed agents.
- Monitor the latest run status from the agent card.

#### Prerequisites and permissions

- Some Agent Hub capabilities require additional setup, depending on the notification channels you use.

##### Slack (optional)

Slack setup is required only if you want to receive agent output in Slack.

- Approval of the AppsFlyer Slack app by your organization. To do this:
  - Go to the Agent hub and select the agent you want to use.
  - Click **Connect to Slack** within the agent configuration card.

For agents that send output to Slack, you must first create a dedicated Slack channel within your organization and invite the AppsFlyer Agent Hub Slack app to that channel before the agent setup. The name of the channel is required as part of the agent setup.

To invite an app to a channel:

1. In the Slack channel you want to receive the notifications to, write: **/invite**
2. Choose **Add Apps to this channel.**
3. Select **AppsFlyer Agent Hub** -> **Add.**

- The following roles have automatic full access:
  - Admin
  - Marketing manager
  - Team manager
  - Marketing lead

- **Other roles:** Require the AI Tools capability enabled through [User Management](/docs/user-management).

##### Email (optional)

- Emails can only be sent to email addresses that are connected to an AppsFlyer account.
- Users must be subscribed to the AppsFlyer mailing list. [See here for more information](/docs/notifications#what-notifications-can-i-receive).

> 📘 Note
>
> In each agent, you can configure up to 5 email addresses.

#### Set up an agent

Agents can be set up and deployed to run on a schedule or manually. You can also configure where agent output is delivered, such as Slack or Email.

You can monitor the status of the latest run directly from the agent card in the **My Agents** tab. To view completed outputs and historical runs, click the **Activity** tab.

Follow the steps below to set up and deploy an agent.

1. Log in to AppsFlyer.
2. From the left-hand menu, go to **Agent Hub.**
3. On the agent you want to set up and deploy, click **Deploy**.
4. On the following page, configure the required agent settings.
5. Add your email address or connect your Slack workspace if relevant.
   1. Make sure that the Slack channel has been set up. [See prerequisites](/docs/beta-agent-hub-overview#prerequisites-and-permissions).
6. Select a run schedule (currently based on UTC; additional time zones will be added soon).
7. Click **Deploy Agent**.

#### Available agents

| **Agent** | **Description** | **Premium subscription required** | **Output** |
| --- | --- | --- | --- |
| **Spot Creative Opportunities** | Evaluates and identifies top-performing creatives across partners based on spend and ROAS from the past 30 days and provides recommendations on which partners are not currently running these creatives and where they should be added to maximize performance. | [Creative optimization](/docs/creative-optimization-guide) | - [Slack](/docs/beta-agent-hub-overview#slack-optional)<br>- [Email](/docs/beta-agent-hub-overview#email-optional) |
| **Custom Executive Summaries** | Generates comprehensive executive summaries from aggregated analytics data, highlighting key trends, top performers, and recommendations to keep your team managers informed and data-driven. | No | - [Slack](/docs/beta-agent-hub-overview#slack-optional)<br>- [Email](/docs/beta-agent-hub-overview#email-optional) |
| **Deep Research Analysis** | Analyzes raw, event-level mature data, comparing two consecutive, fully completed weeks (Monday–Sunday) to identify meaningful week-over-week shifts. For example, on Monday, Jan 26, the agent compares Jan 12–18 against Jan 5–11, intentionally excluding the current ongoing week to avoid partial or immature data. Using deep research across partners, geos, OS versions, and SDKs, the agent surfaces trends and setup issues that are not visible in aggregated data, with results delivered weekly on Mondays. | No | - [Slack](/docs/beta-agent-hub-overview#slack-optional)<br>- [Email](/docs/beta-agent-hub-overview#email-optional) |
| **Optimize Anti-Fraud Strategy (Protect360)** | Proactively analyzes data to detect early fraud signs and provides key findings, and recommends actions that reduce fraud and boost performance. | Protect360 + Protect360 closed beta features | Protect 360 dashboard |
| **Monitor App Releases** | Monitors iOS and Android app releases and alerts you when new versions go live. Provides real-time visibility into app release progress, including marketing-related updates such as new features, in-app behavior, and added or removed events, so you can align your UA campaigns with the latest app versions without relying on developer updates. | No | - [Slack](/docs/beta-agent-hub-overview#slack-optional)<br>- [Email](/docs/beta-agent-hub-overview#email-optional) |
| **Detect Performance Anomalies** | Monitors key KPIs daily and flags significant positive or negative anomalies. Sends clear, story-based Slack alerts explaining what changed and why, helping you quickly identify issues such as CPI spikes, IPM drops, or unexpected trends across partners, campaigns, and geos. | No | - [Slack](/docs/beta-agent-hub-overview#slack-optional)<br>- [Email](/docs/beta-agent-hub-overview#email-optional) |
| **Detect Setup Issues** | Detects setup issues that may impact measurement quality or performance. Sends Slack alerts for inactive integrations in SKAN and Cost, as well as other configuration gaps such as disabled View-Through Attribution via Probabilistic Modeling, enabling fast detection and quick remediation. | No | - [Slack](/docs/beta-agent-hub-overview#slack-optional)<br>- [Email](/docs/beta-agent-hub-overview#email-optional) |

### Activity tab

**Activity** tab shows completed agent run outputs. It appears when your account has at least one agent with completed outputs.

Use this tab to review recent agent activity, view previous outputs, provide feedback, and ask AI Assistant questions about a specific run.

The Activity tab includes two sections:

| Section | Description |
| --- | --- |
| Latest activity | Shows the latest completed run for each agent instance. |
| Previous runs | Shows completed runs from the last 30 days. |

You can filter activity by:

- App
- Agent instance

> 📘 Note
>
> The agent filter is based on the specific agent instance, not the agent type.

#### View activity output

To view activity output:

1. Go to **Agent Hub**.
2. Click the **Activity** tab.
3. Select the relevant app or agent instance filters.
4. Click a run to expand it.

The expanded run shows the same output sent by Slack or email.

From the expanded run, you can:

- Copy the output.
- Provide positive or negative feedback.
- Add free-text feedback.
- Click **Analyze activity** to ask AI Assistant questions about the run.

#### Analyze activity with AI Assistant

Use **Analyze activity** to ask AI Assistant questions about a specific completed agent run.

**Analyze activity** is available for all agents. AI Assistant opens in the context of the selected run. It can help you understand how the agent reached its output, what data it used, and which factors it considered or ruled out.

This isn’t a general chat with the agent. AI Assistant answers questions about the selected run only. It doesn’t perform new agent work, access data outside the run, or make predictions.

To ask AI Assistant questions about a run:

1. Go to **Agent Hub**.
2. Click the **Activity** tab.
3. Click a run to expand it.
4. Click **Analyze activity**.
5. Select a suggested question or enter your own question.

For example, you can ask:

- Walk me through your reasoning.
- What data was this based on?
- Why was this finding prioritized?
- What factors did the agent consider?
- What factors did the agent rule out?

##### Supported and unsupported questions

| You can ask about | You can’t ask about |
| --- | --- |
| How the agent reached its output | Data that wasn’t included in the run |
| What data the agent used for the run | New analysis that wasn’t part of the run |
| Why findings were prioritized or ruled out | Forward-looking predictions |
| The context and reasoning of the selected run | General optimization recommendations outside the run context |

### Notes

Keep the following in mind when using the **Activity** tab and **Analyze activity**:

- AI Assistant must be enabled for the account. If AI Assistant is disabled, **Analyze activity** isn’t available. See [Account Settings](/docs/account-settings#agent-hub).
- Activity history includes completed runs from the last 30 days only.
- Deleting an agent also deletes its previous activity, including outputs, findings, and reasoning data. This action can’t be undone.
- AI Assistant answers questions about the selected run only. It doesn’t perform new analysis, access data outside the run, or make predictions.

### FAQ

<Accordion title="Can I create my own agents?">

Currently, only agents developed and maintained by AppsFlyer are available.

</Accordion>

<Accordion title="Can agents automate actions?">

No, automation is not yet supported. Currently, agents provide insights and recommendations only.

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

- All users lose access to Agent Hub.
- All existing agents are permanently deleted and can’t be restored.
- Any active agent runs stop.

If an admin enables Agent Hub again later, users can access it again, but they must create and deploy agents from scratch.

For more information, see [Account settings](/docs/account-settings#agent-hub).

</Accordion>

<Accordion title="Where can I get notifications sent to?">

You can receive notifications via Email or Slack. Email notifications require users to be subscribed to AI capabilities notifications in the Notification Center.

</Accordion>

<Accordion title="Why am I not receiving Agent Hub email notifications?">

If you completed the email notification prerequisites but still don’t receive Agent Hub emails, you might have previously unsubscribed from AppsFlyer emails.

Contact AppsFlyer Support for assistance.

</Accordion>