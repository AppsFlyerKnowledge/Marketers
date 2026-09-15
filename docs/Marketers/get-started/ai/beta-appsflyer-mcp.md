---
title: "[Beta] AppsFlyer MCP"
excerpt: "Connect your AppsFlyer data to large language models (LLMs) like Claude, ChatGPT, and Gemini to ask questions and retrieve performance insights directly in your AI chat or development environment."
---
**At a glance:** AppsFlyer MCP connects your AppsFlyer data to large language models (LLMs), such as Claude, ChatGPT, Gemini CLI, Copilot CLI, and VS Code. Ask questions, get performance insights, and retrieve AppsFlyer information directly in your AI chat or development environment.

<Embed title="[Beta] AppsFlyer MCP" typeOfEmbed="youtube" url="https://www.youtube.com/embed/jAw7oocIx6o?si=-s107vTaTTwO076n" providerUrl="https://www.youtube.com" />

### Disclaimer

**The AppsFlyer MCP Server is a service currently in beta phase, provided by AppsFlyer for evaluation purposes.**

By using it to connect third-party AI tools, you agree that AppsFlyer has no responsibility or liability for such tools, their outputs, results, performance, operation, legality, or reliability. AppsFlyer does not control, endorse, or verify these tools or their results and expressly disclaims all warranties, express or implied, relating thereto. AppsFlyer is not responsible for data storage, retention, processing, or use by such tools. You are solely responsible for ensuring compliance with applicable laws and your own internal policies. You represent that you have all necessary rights and consents to connect these tools to the MCP Server and provide them access to your data. The service is provided "as-is" for supported use cases only. Use outside this scope is at your sole risk. Use is subject to the terms of the [Master Services Agreement](https://www.appsflyer.com/legal/msa/), or if a definitive agreement has been signed, then the terms of such agreement.

## What is AppsFlyer MCP?

AppsFlyer MCP lets you securely connect LLMs to the AppsFlyer platform so you can interact with your marketing data through simple conversation. AppsFlyer MCP helps you make smarter, faster decisions based on real-time data.

With MCP, you can:

* Get instant campaign performance, trends, and KPI information.
* Compare metrics like ROAS, installs, and LTV.
* Audit and troubleshoot OneLink templates, links, and Audiences connections.
* Retrieve setup guidance or product documentation.

## Set up AppsFlyer MCP

AppsFlyer MCP can connect to chat assistants, CLIs, IDEs, automation platforms, and self-hosted agents. Setup depends on the client you use and the authentication method it supports.

> 📘 **Note**
>
> #### Note
>
> Some platforms might require admin approval to connect MCP servers. If you don't see the setup options described below, contact your IT or workspace admin.


## Authentication methods

AppsFlyer MCP supports two authentication methods. Use the method that matches how you plan to connect to AppsFlyer MCP.



| Authentication method | Used by | Best for | Access duration |
| --- | --- | --- | --- |
| Browser-based OAuth login | Gemini CLI, Copilot CLI, ChatGPT, Claude.ai, and Claude Desktop | Ad hoc questions, exploratory analysis, and one-off reports | Valid for 7 days from connection. Re-authentication is required at the end of the session |
| Bearer token authentication | Claude Code, automation platforms, self-hosted agents, and integrations | Automations, scheduled tasks, background agents, and non-interactive workflows | Valid until manually revoked |



### Browser-based OAuth login

Browser-based OAuth login lets you connect interactively through your browser. When you connect, the MCP client opens a browser window and asks you to log in to AppsFlyer. After you approve access, the client connects to your AppsFlyer account.

Use this method for interactive sessions, exploratory analysis, and one-off reports.

### Bearer token authentication

Bearer token authentication lets non-interactive tools connect to AppsFlyer MCP by using an AppsFlyer MCP token. The token is passed in the request header:

```
Authorization: Bearer <YOUR_MCP_TOKEN>
```

Use this method for automations, scheduled tasks, background agents, and integrations that can't use a browser login.

To create a token, go to **Account menu > Security Center > AppsFlyer Tokens** and create an MCP token.

## Set up by client

### Claude Chat and Cowork

Use Claude chat and Claude Cowork with browser-based OAuth login. These instructions apply to Claude on web, desktop, and Cowork.

> 📘 **Note**
>
> #### Note
>
> For Team and Enterprise plan users, only Owners or Admins can add organization-wide integrations.


#### Set up Claude chat and Cowork

1. Click your name in the lower-left corner and select **Settings**. Alternatively, in a new chat, click **Search & tools** > **Manage connectors**.
2. Open the [Connectors](https://claude.ai/settings/integrations) tab.
3. Switch to the **Organization connectors** tab.
4. In the connectors section, click **Add connector**.
5. Enter the following connector details:
   * **Connector name:** AppsFlyer
   * **Connector URL:** `https://mcp.appsflyer.com/auth/mcp`
6. Click **Add**.
7. Switch to the **Your connectors** tab.
8. In the connectors section, click **Connect** next to the AppsFlyer connection.
9. Log in to AppsFlyer when prompted.

#### Test the Claude connection

1. In any chat window, click the settings button.   
   ![](https://support.appsflyer.com/hc/article_attachments/46334217789073)
2. If AppsFlyer MCP was set up correctly, the AppsFlyer tools appear in the menu.

> 📘 **Note**
>
> #### Note
>
> **Get started faster with Cowork: save as a Skill.** If your team works in Claude Cowork, use the [Claude Cowork starter kit for marketers](https://github.com/AppsFlyerKnowledge/appsflyer-ai-agents-examples/tree/main/Claude/AppsFlyer%20Cowork%20Starter%20Kit) to get set up faster. The starter kit includes an activation plan, ready-to-use templates, and copy-paste prompts for working with your AppsFlyer data through AI from day one, so you don't have to build your first workflows, reports, or briefs from scratch.


### Claude Code

Use Claude Code with bearer token authentication for automation, scheduling, and non-interactive workflows.

#### Add AppsFlyer MCP to Claude Code

1. In AppsFlyer, go to **Account menu > Security Center > AppsFlyer Tokens**.
2. Create an MCP token.
3. In Terminal, add the AppsFlyer MCP server:

   ```
   claude mcp add-json appsflyer '{"type":"http","url":"https://mcp.appsflyer.com/auth/mcp","headers":{"Authorization":"Bearer YOUR_APPSFLYER_MCP_TOKEN"}}'
   ```
4. Start Claude Code:

   ```
   claude .
   ```
5. Verify that the MCP server was added:

   ```
   claude mcp list
   ```
6. Confirm that `appsflyer` appears in the list of configured MCP servers.
7. Ask an AppsFlyer question. For example:

   ```
   What apps are in my AppsFlyer account?
   ```

   ```
   What were my top media sources in the US last week for "Mypets.android.com"?
   ```

   ```
   Create a summary of the performance of "Mypets.android.com" in the last day, segmented by campaign.
   ```

### Cursor IDE

Use Cursor IDE to connect AppsFlyer MCP from your local development environment.

1. Create or open a configuration file, depending on the scope:
   * **Global configuration:** `~/.cursor/mcp.json`
   * **Project-specific configuration:** `.cursor/mcp.json`
2. Add the following entry under the `mcpServers` field in your JSON file:

   ```
   {
     "mcpServers": {
       "appsflyer": {
         "url": "https://mcp.appsflyer.com/auth/mcp"
       }
     }
   }
   ```
3. Restart Cursor IDE to apply the new configuration.
4. Authenticate when prompted to access AppsFlyer MCP services.

### VS Code

1. Press `Cmd+Shift+P` or `Ctrl+Shift+P` to open the Command Palette.
2. Select **Configure MCP Servers**.
3. In `.vscode/mcp.json`, add the AppsFlyer MCP server configuration:

   ```
   {
     "servers": {
       "appsflyer": {
         "url": "https://mcp.appsflyer.com/auth/mcp"
       }
     }
   }
   ```
4. Save the file and restart Copilot Chat.

### ChatGPT

There are two ways to use ChatGPT with AppsFlyer MCP.

* [Custom GPT](#custom-gpt-available-for-all-packages-including-free-enterprise): Best for simple access to an AppsFlyer assistant.
* [MCP in ChatGPT](#mcp-in-chatgpt-supported-for-chatgpt-users-on-all-paid-plans): Best for users who want to bring AppsFlyer data into ChatGPT conversations.

#### Add the AppsFlyer custom GPT

1. Click [AppsFlyer custom GPT](https://chatgpt.com/g/g-68b6a92eb8e0819194cbb81e1e635c0d-appsflyer).
2. Save the GPT to your sidebar for easy access.
3. Open the custom GPT.
4. Ask a question. For example:

   ```
   Show me my Meta campaign performance from last week.
   ```

#### Add AppsFlyer MCP in ChatGPT

> 📘 **Note**
>
> #### Note
>
> Admin setup might be required to add and publish a connector to your organization.


1. Add a connector and publish it to your organization.
2. Enter the following connector details:
   * **Name:** AppsFlyer MCP
   * **URL:** `https://mcp.appsflyer.com/auth/mcp`
   * **Authentication:** OAuth
3. To connect for the first time, go to **Settings > Apps & Sources > AppsFlyer MCP**.
4. Connect to AppsFlyer MCP.
5. Follow the steps to connect and log in with your AppsFlyer credentials.

After setup, open a chat, select **Sources** or **Connectors**, and turn on the AppsFlyer connection.

For security, AppsFlyer MCP disconnects approximately every 10 hours. To reconnect, repeat the connection flow.

### Gemini CLI

Use Gemini CLI with browser-based OAuth login.

#### Add AppsFlyer MCP to Gemini CLI

1. In Terminal, add the AppsFlyer MCP server:

   ```
   gemini mcp add appsflyer https://mcp.appsflyer.com/auth/mcp -t http
   ```
2. Start Gemini CLI:

   ```
   gemini
   ```
3. In the Gemini CLI prompt, enter:

   ```
   auth
   ```
4. Complete the authentication flow in your browser, and then return to Terminal.
5. Ask an AppsFlyer question. For example:

   ```
   What apps are in my AppsFlyer account?
   ```

#### Troubleshoot Gemini CLI authentication

If authentication fails, start Gemini CLI in debug mode:

```
GEMINI_LOG_LEVEL=debug gemini
```

Then enter `auth` again in the Gemini CLI prompt.

### Copilot CLI

Use Copilot CLI with browser-based OAuth login.

#### Add AppsFlyer MCP to Copilot CLI

1. Open Terminal.
2. Start Copilot CLI:

   ```
   copilot
   ```
3. If you're not logged in, enter the following command in the Copilot CLI prompt:

   ```
   /login
   ```
4. Complete the browser login.
5. In the Copilot CLI prompt, enter:

   ```
   /mcp add
   ```
6. Enter the following MCP server details:

   

| Field | Value |
| --- | --- |
| Server Name | `appsflyer` |
| Server Type | `HTTP` |
| URL | `https://mcp.appsflyer.com/auth/mcp` |
| Tools | `*` |


7. Press **Ctrl+S** to save the configuration.
8. When prompted, complete the AppsFlyer authentication flow in your browser.
9. Return to Terminal.
10. Ask an AppsFlyer question. For example:

    ```
    What apps are in my AppsFlyer account?
    ```

### Third-party and self-hosted platforms

Use an MCP token to authenticate third-party or self-hosted systems with AppsFlyer MCP. This supports automation and AI integrations with platforms like n8n, Make, or your own LLM-powered agents.

The MCP token is an account-level bearer token that inherits the permissions of the admin who created it. You can access and manage it from [Security Center > AppsFlyer Tokens](/docs/managing-appsflyer-tokens).

#### MCP connection details

To connect your automation or agent platform to AppsFlyer MCP, use the following configuration:

* **Auth Type:** Bearer Token
* **Base URL / Endpoint:** `https://mcp.appsflyer.com/auth/mcp`
* **Bearer Token:** Your MCP token

> 📘 **Note**
>
> #### Note
>
> Never share or publish your token publicly. Treat it as a private credential. Your MCP token grants direct access to your MCP environment.


#### Example use cases



| Category | Example |
| --- | --- |
| Custom agents | Build an AI agent that uses MCP to fetch data, analyze it, and send recommendations. |
| LLM integrations | Let a self-hosted LLM query campaign performance metrics through MCP. |



### Other platforms

By default, only the platforms listed above are enabled. To connect a different platform, contact your CSM or send an email to [hello@appsflyer.com](mailto:hello@appsflyer.com).

### Use multiple accounts or agencies

AppsFlyer MCP connects to one AppsFlyer account at a time.

#### Switch between accounts (browser-based OAuth)

If you manage multiple AppsFlyer accounts under the same email, you can switch which account MCP connects to:

1. In AppsFlyer, set the account you want to connect to as your primary account.
2. Log in again in your MCP client.

You can't view or query multiple accounts side-by-side in a single connection.

#### Connect multiple accounts simultaneously (bearer token)

To connect to several accounts at the same time, for example for agency use, use a multi-agent flow instead of browser-based OAuth:

1. For each account, create an MCP token in **Account menu > Security Center > AppsFlyer Tokens**.
2. In your agent platform, connect each account separately using its own bearer token.

See an example of this flow in [this video](https://www.youtube.com/watch?v=o5oK-yWuE5E).

## Use AppsFlyer MCP

### Use cases and prompts

AppsFlyer MCP gives you a set of tools and resources designed to help you retrieve marketing analytics, performance insights, and configuration information.

> 📘 **Note**
>
> #### Important!
>
> Answers generated through AppsFlyer MCP are only reliable when used for the supported use cases listed below. Responses outside of these use cases have not been validated by AppsFlyer and might be inaccurate or misleading. We can't guarantee the precision or correctness of AI-generated answers that fall outside the intended scope of the AppsFlyer MCP integration.


Some example use cases and prompts are:

### Analyze performance

Explore aggregated marketing performance data in real time. You can identify top- and low-performing campaigns, run comparisons, spot trends, and uncover insights to help guide decision-making.

**Prompt:** "What were my top media sources in the US last week for Mypets.android.com?"

**Expected AI response:** The AI retrieves top-performing media sources, including installs, revenue, and ROAS.

**Prompt:** "What is the best campaign in terms of ROAS where total installs are at least 5000?"

**Expected AI response:** The AI identifies and ranks campaigns meeting the criteria with performance insights.

**Prompt:** "How many installs did we have yesterday in China for Mypets.android.com app?"

**Expected AI response:** The AI fetches the number of installs in China for that day and app.

**Prompt:** "Create a summary of the performance of Mypets.android.com in the last day, segmented by campaign."

**Expected AI response:** The AI returns a campaign-segmented performance report for that app.

**Prompt:** "Compare D1 retention last week vs. the week before, grouped by media source."

**Expected AI response:** The AI performs a week-over-week comparison of D1 retention rates, grouped by media source.

> 📘 **Note**
>
> #### Note
>
> **Get started faster with Cowork: save as a Skill.** If your team works in Claude Cowork, use the [Claude Cowork starter kit for marketers](https://github.com/AppsFlyerKnowledge/appsflyer-ai-agents-examples/tree/main/Claude/AppsFlyer%20Cowork%20Starter%20Kit) to get set up faster. The starter kit includes an activation plan, ready-to-use templates, and copy-paste prompts for working with your AppsFlyer data through AI from day one, so you don't have to build your first workflows, reports, or briefs from scratch.


### Analyze Incrementality for UA experiments

Retrieve your Incrementality for UA experiments and their results, including lift, incremental conversions, incrementality factor, and cost per incremental conversion. Use this information to see which campaigns drove real, incremental growth and where to shift budget.

**Prompt:** "Which incrementality experiments ran for Mypets.android.com in the US last quarter?"

**Expected AI response:** The AI returns the experiments matching that app, country, and date range, including each experiment's status, media source, measured event, and test period.

**Prompt:** "Summarize the results of Incrementality experiment 12345"

**Expected AI response:** The AI returns the experiment's lift, incremental conversions, incrementality factor compared to classic attribution, and cost per incremental conversion, with the credible interval at the experiment's confidence level.

**Prompt:** "Compare cost per incremental action and Incremental ROAS across all my Incrementality experiments in the past 6 months."

**Expected AI response:** The AI compares the efficiency of your completed experiments from the last 6 months side by side, highlighting which campaigns delivered the most incremental value per dollar of ad spend.

### Analyze SKAN performance

Gain insights into iOS campaign performance using Apple's SKAdNetwork framework. Identify top-performing campaigns and analyze KPI trends to support decision-making.

**Prompt:** "What was the ROI by network for the last month?"

**Expected AI response:** The AI retrieves ROI results for the selected period and highlights the top networks.

**Prompt:** "Which campaigns have the lowest CPI?"

**Expected AI response:** The AI identifies campaigns with the lowest CPI, ranking the top performers.

**Prompt:** "What were the weekly conversion rates for the event af\_subscribed in the last month?"

**Expected AI response:** The AI provides a week-by-week breakdown of conversion rates for the event and indicates the overall trend.

**Prompt:** "Which networks have the highest null rates, and which campaigns under them show the highest null rates?"

**Expected AI response:** The AI identifies networks with the highest null rates and outlines the campaigns contributing most to those rates.

### OneLink management

Query and audit your OneLink templates and links to support consistent routing and accurate user journeys. MCP can help you troubleshoot issues and verify link setup at scale.

**Prompt:** "Audit the HolidayPush2025 template and show all links with parameters."

**Expected AI response:** The AI returns a CSV table with short links and associated parameter values.

**Prompt:** "Why does this OneLink redirect to the App Store for existing users?"

**Expected AI response:** The AI returns troubleshooting insights based on link parameters and fallback logic.

**Prompt:** "List all QR-enabled OneLinks for app TravelBuddy."

**Expected AI response:** The AI returns a list of generated OneLinks with QR links and associated metadata.

**Prompt:** "What parameters, capabilities, and redirect behavior does this link have: https://mypets.onelink.me/abc123?"

**Expected AI response:** The AI returns the link's parameters by category, its enabled capabilities such as deep linking and retargeting, and how it redirects users by device, platform, and install status.

### Knowledge base and developer support

Quickly access AppsFlyer documentation and DevHub resources. Get answers about SDK setup, product behavior, and measurement logic directly in your AI chat.

**Prompt:** "How do I set up in-app event deduplication on Android?"

**Expected AI response:** The AI provides setup steps, code snippets, and best practices.

**Prompt:** "What's the attribution lookback window for TikTok installs?"

**Expected AI response:** The AI explains the latest platform-specific attribution rules.

**Prompt:** "What's the best way to optimize my app's ROAS using AppsFlyer?"

**Expected AI response:** The AI outlines strategic levers like segmentation, partner optimization, and LTV measurement best practices.

### Apps management

Retrieve key app configuration details such as attribution windows, session timeouts, re-engagement settings, and more. Use this information to audit and compare app settings across your portfolio.

**Prompt:** "What is the attribution window set for my gaming apps?"

**Expected AI response:** The AI returns a list of apps with their configured attribution windows, highlighting any deviations from the standard.

**Prompt:** "In which of my apps do I have a different lookback window?"

**Expected AI response:** The AI surfaces apps with non-standard lookback windows and shows their configured values.

**Prompt:** "List all of my iOS pinned apps that are active."

**Expected AI response:** The AI returns a list of pinned iOS apps that are currently active, including app IDs and names.

**Prompt:** "What is the current session timeout setting for the AppsFlyer gaming app and could it affect my re-engagement from being attributed?"

**Expected AI response:** The AI returns the session timeout setting and explains its impact on re-engagement.

### Audiences management

### Audiences management

Gain visibility into audience structure, ownership, partner connections, and active tests. Monitor upload health, detect failed connections, identify stale audiences, and understand how each audience is configured. Use this information to streamline cross-functional campaign management.

**Prompt:** "Give me all active audiences for the FinancePro app."

**Expected AI response:** The AI returns a list of audiences with metadata such as creation date, owner, and partners.

**Prompt:** "Who last updated the audience Churned Users - Tier A?"

**Expected AI response:** The AI returns the user ID or email with the timestamp of the last modification.

**Prompt:** "List all audiences currently in a split test with Meta and TikTok."

**Expected AI response:** The AI returns a list of active audiences with test configuration and split percentages.

**Prompt:** "I want to test Moloco vs. Google, give me all the audiences connected to Google."

**Expected AI response:** The AI returns a list of audiences connected to Google with their current status and configuration.

**Prompt:** "I'm about to close (network), give me a list of the active audiences running."

**Expected AI response:** The AI returns all active audiences with their connected partners and current status.

**Prompt:** "Give me a list of all active audiences, their connected partners, and their current splits."

**Expected AI response:** The AI returns a full list of audiences with each partner connection and its split percentage.

**Prompt:** "Are any of my Meta audiences currently failing to upload?"

**Expected AI response:** The AI returns a list of Meta-connected audiences with a failed upload status, including the error message for each.

**Prompt:** "I want to check my TikTok campaigns, which audiences connected to TikTok are failing and since when?"

**Expected AI response:** The AI returns all TikTok-connected audiences with a failed status and their last successful upload time.

**Prompt:** "Give me all audiences that had no successful upload in the last 7 days."

**Expected AI response:** The AI returns a list of audiences with no successful upload in the last 7 days and their current connection statuses.

### Feedback tool

Submit feedback about your experience using AppsFlyer MCP directly through the assistant interface. Your feedback helps us improve and shape the future of the product.

**Prompt:** "The analytics provided in the analysis tool are amazing and helpful for our decision-making. I'd like to see in-app event measurement added as an option in the analysis."

**Expected AI response:** The AI submits the feedback to the AppsFlyer MCP product team.

### Cost configuration integration

Gain visibility and control over your cost data with the Cost Configuration MCP. This integration helps you maximize cost coverage, detect integration gaps early, and keep cost data complete and accurate across ad networks.

**Prompt:** "What active cost integrations do I have in my AppsFlyer account?"

**Expected AI response:** The AI lists all enabled cost integrations in your AppsFlyer account, along with their linked app IDs and current status.

**Prompt:** "Show me the issues I have in my active cost integrations."

**Expected AI response:** The AI displays active cost integrations that had issues in the last 7 days, ordered by ad network and connected apps.

**Prompt:** "Which cost integrations should I connect based on my recent attribution data?"

**Expected AI response:** The AI shows ad networks that support cost integration but aren't connected yet, ranked by recent traffic volume by app.

### Ad revenue integrations

Gain visibility and control over your ad revenue integrations using AppsFlyer MCP. You can use MCP to confirm which ad revenue integrations are enabled, monitor their health, detect gaps early, and keep ad revenue data flowing consistently across your apps and monetization partners.

**Prompt:** "What active ad revenue integrations do I have in my AppsFlyer account?"

**Expected AI response:** The AI lists all enabled ad revenue integrations in your AppsFlyer account, including connected apps and current integration status.

**Prompt:** "Show me the issues I have in my active ad revenue integrations."

**Expected AI response:** The AI displays enabled ad revenue integrations that had issues in the last 7 days, grouped by mediation partner, integration type, and app.

### User management and role control

Retrieve user and role information from your AppsFlyer account. This helps administrators maintain a clear user database and manage access controls efficiently.

**Prompt:** "List any inactive users who haven't logged into AppsFlyer in the last 6 months."

**Expected AI response:** The AI returns users with last login dates older than 6 months, or no login at all, including email addresses, roles, and last login timestamps.

**Prompt:** "Show me all users grouped by their permission levels and highlight any admin users."

**Expected AI response:** The AI organizes users by role type and highlights admin users, including associated apps and geographical access permissions.

**Prompt:** "One of the team members has complained they can't log into AppsFlyer. Can you check if their user exists and what their current status is?"

**Expected AI response:** The AI verifies whether the user exists and returns the user's current role, associated apps, last login date, and potential access restrictions.

**Prompt:** "Which users have access to more than 5 apps, and what are their roles?"

**Expected AI response:** The AI returns users with extensive app access, their roles, and the full list of apps they can access.

## Other information

### Privacy and security

AppsFlyer MCP lets your selected AI tool query AppsFlyer data based on your existing permissions.

#### Data processing

AppsFlyer MCP acts as a secure proxy. It fetches AppsFlyer data in real time and returns the data needed to answer the query. AppsFlyer MCP doesn't archive or store query results long term.

#### Credentials

Your AppsFlyer login lets AppsFlyer MCP make API calls on your behalf. Your AppsFlyer credentials aren't shared with the AI tool.

#### Permissions

AppsFlyer MCP uses your existing AppsFlyer permissions. Users can only access the apps and data they already have permission to view in AppsFlyer.

There's no separate permission layer to configure for MCP access.

#### Read-only access

AppsFlyer MCP is currently read and query only. It doesn't take action in AppsFlyer without you.

#### AI provider data usage

The data retrieved by AppsFlyer MCP may be shared with your selected AI tool to answer your query. Only the data needed to generate the response is shared.

AppsFlyer doesn't control whether your selected AI tool stores, processes, or learns from the data. Review your AI provider's terms and data usage policies before connecting AppsFlyer MCP.

#### Certifications

AppsFlyer is ISO 27001 and SOC 2 certified. ISO 42001 certification is in progress.

### Tool mapping

By default, all tools are enabled. We recommend keeping them enabled to ensure full functionality and prevent issues during use.

Each tool is mapped to a functional category, such as Analyze performance, apps management, or OneLink management. Some categories might include multiple tools.

See the table below for the complete list of tools and their category mappings.



<table><thead><tr><th>Category</th><th>Tool</th><th>Description</th></tr></thead><tbody><tr><td><a href="#analyze-performance">Analyze performance</a></td><td>fetch_aggregated_data</td><td>Retrieves aggregated dashboard data with custom date ranges, groupings, metrics, and filters.</td></tr><tr><td rowspan="2"><a href="#analyze-incrementality-experiments">Analyze Incrementality for UA experiments</a></td><td>incrementality_list_experiments</td><td>Lists incrementality experiments, filtered by status, app, country, media source, and date range.</td></tr><tr><td>incrementality_get_experiment_results</td><td>Gets results for a specific experiment, including lift, incremental conversions, incrementality factor, and cost per incremental conversion.</td></tr><tr><td rowspan="2"><a href="#apps-management">Apps management</a></td><td>get_apps</td><td>Lists all permitted apps organized by pinned and unpinned status with transfer requests.</td></tr><tr><td>get_app_settings</td><td>Gets app configuration settings including attribution windows, privacy controls, session management, and platform-specific configurations.</td></tr><tr><td><a href="#cost-configuration-integration">Cost configuration integration</a></td><td><p>get_active_cost_integrations</p><p>list_cost_supported_media_source</p></td><td>Gets an overview of active cost integration status and missing cost integrations in your account.</td></tr><tr><td><a href="#ad-revenue-integrations">Ad revenue integrations</a></td><td><p>list_adrevenue_supported_media_sources</p><p>get_active_adrevenue_integrations</p></td><td>Checks which integrations are enabled, monitors health, detects configuration gaps, and helps keep ad revenue data consistent.</td></tr><tr><td><a href="#analyze-skan-performance">SKAN performance</a></td><td>skan_get_app_data</td><td>Retrieves aggregated SKAN performance data grouped by network, campaign, or event across custom date ranges.</td></tr><tr><td rowspan="4"><a href="#onelink-management">OneLink management</a></td><td>get_onelink_templates</td><td>Lists all OneLink templates.</td></tr><tr><td>get_onelink_template_links</td><td>Gets all OneLink links created from a specific template.</td></tr><tr><td>get_onelink_details</td><td>Gets configuration details for a specific OneLink.</td></tr><tr><td>discover_onelink</td><td>Discovers a link's parameters, capabilities, and redirection behavior from a short or long URL.</td></tr><tr><td rowspan="3"><a href="#audiences-management">Audiences management</a></td><td>list_active_audiences</td><td>Lists all active audiences that are calculated daily.</td></tr><tr><td>list_audiences_connections</td><td>Lists advertising partner integrations for audience data.</td></tr><tr><td>get_audience_connections</td><td>Gets partner connections for a specific audience.</td></tr><tr><td><a href="#knowledge-base-and-developer-support">Knowledge base and developer support</a></td><td>get_public_knowledge</td><td>Searches AppsFlyer Knowledge Base and DevHub documentation.</td></tr><tr><td><a href="#feedback-tool">Feedback tool</a></td><td>send_feedback</td><td>Submits feedback about the tools or system.</td></tr><tr><td><a href="#user-management-and-role-control">User management and role control</a></td><td>get_users</td><td>Lists users and roles from AppsFlyer.</td></tr></tbody></table>



### Traits and limitations



| Trait | Description |
| --- | --- |
| Multi-account use | AppsFlyer MCP uses data from the default account only. To switch accounts or connect several accounts at once, see [Use multiple accounts or agencies](#use-multiple-accounts-or-agencies). |
| OneLink links | * The get\_onelink\_template\_links tool includes only links created from the OneLink Management page, not links created via API, SDK, or bulk creation.<br />* Discover OneLink (discover\_onelink) has no such restriction. It supports all AppsFlyer link types, including single-platform (legacy) links, branded domains, and links created via the UI, API, SDK, or bulk creation. |
| Rate limits | * Analytics: 20 requests per minute<br />* Audiences: 350 requests per minute<br />* SKAN: Up to 10,000 rows per query |
| Date range | * Analytics: 3 years<br />* SKAN: Maximum 90 days per request |
| Groupings | * Analytics: 4 groupings per request<br />* SKAN: As available in the [SKAN dashboard](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#metrics) |
| App limits | * Analytics: 10 apps per request<br />* SKAN: One app per request, iOS only |
| Supported dimensions | Analytics supports all dimensions available in My Dashboards. |
| Aggregated data | Aggregated data is supported. This includes weekly and monthly granularity levels and custom metrics. |
| Freshness | SKAN data is available with up to a 3-day delay, in UTC. |
| Currency and time zone | SKAN data is available in USD by default. Alternative currencies are supported by using `revenue_alt = true`. Data is reported in UTC. |
| Disabling MCP | * MCP is enabled by default and can be disabled by an admin in **Account & Profile > AI capabilities**.<br />* When MCP is disabled, users can't access AppsFlyer data through MCP in external AI tools.<br />* Existing connections might continue until the current session expires.<br />* Disabling MCP doesn't affect regular API connections or other AI capabilities in AppsFlyer.<br />* If an MCP token is in use, delete it first in **Security Center > AppsFlyer Tokens**. |



## Troubleshoot connection issues

If the AppsFlyer MCP connection isn't working, follow the steps for your authentication method.

### Browser-based OAuth login

Use this section for clients that connect through browser login, such as Gemini CLI, Copilot CLI, ChatGPT, Claude.ai, and Claude Desktop.

1. **Re-authenticate your session.** OAuth sessions expire approximately every 7 days. Re-run the connection flow and complete the browser login again.
2. **Complete the authentication flow.** Make sure the browser login completes successfully. When prompted, click **Allow** or **Approve**, and then return to your MCP client.
3. **Restart the session.** Restart your CLI, chat, or application session. Then reconnect to the MCP server.
4. **Verify the MCP server configuration.** Confirm the following values:

   

| Field | Value |
| --- | --- |
| Server Type | `HTTP` |
| URL | `https://mcp.appsflyer.com/auth/mcp` |


5. **Check user permissions.** Make sure your AppsFlyer user has access to the relevant apps and requested data.

### Bearer token authentication

Use this section for Claude Code, n8n, Make, self-hosted agents, and other automation tools.

1. **Check whether the token was revoked.** Tokens can be manually revoked. Tokens created before **March 10, 2026, 19:00 UTC** might no longer work.
2. **Create a new MCP token.** To restore access:
   1. Log in to AppsFlyer.
   2. Go to **Account menu > Security Center > Token Management**.
   3. Locate revoked tokens.
   4. Delete the revoked token.
   5. Create a new MCP token.
   6. Update your MCP client or automation with the new token.
3. **Check the Authorization header.** Make sure the header uses this exact format:

   ```
   Authorization: Bearer <YOUR_MCP_TOKEN>
   ```
4. **Verify the MCP server configuration.** Confirm the following values:

   

| Field | Value |
| --- | --- |
| URL | `https://mcp.appsflyer.com/auth/mcp` |
| Transport | `HTTP` |
| Header | `Authorization: Bearer <YOUR_MCP_TOKEN>` |


5. **Verify that the server is registered.** For Claude Code, run:

   ```
   claude mcp list
   ```
6. **Re-add the MCP server, if needed.**

   ```
   claude mcp remove appsflyer
   claude mcp add-json appsflyer '{"type":"http","url":"https://mcp.appsflyer.com/auth/mcp","headers":{"Authorization":"Bearer YOUR_APPSFLYER_MCP_TOKEN"}}'
   ```
7. **Check token permissions.** The MCP token inherits permissions from the admin who created it. Make sure the token has access to the relevant apps and requested data.

### Access and permission issues

If authentication succeeds but access still fails:

* MCP access might be restricted by your AppsFlyer admin.
* If you don't have access to Account & Profile settings, MCP access might be blocked.
* Contact your AppsFlyer admin to enable access.
* Make sure your user or token has access to the relevant apps and requested data.

### General checks

If the issue persists:

* Make sure your client supports MCP.
* Check whether network or firewall restrictions block the MCP endpoint.
* Confirm that the MCP URL is correct:

  ```
  https://mcp.appsflyer.com/auth/mcp
  ```
* Try reconnecting from a new session or environment.