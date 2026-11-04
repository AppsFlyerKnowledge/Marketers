---
title: Account settings
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2026-03-15T11:09:02Z'
  edited_at: '2026-04-16T19:36:10Z'
  id: 44784756352273
  locale: en-us
  section: Account management
  section_id: 6551191075473
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/44784756352273-Account-settings
---
> **At a glance:** Use the **Account settings** page to manage your personal profile, account-level settings, and AI capabilities from one single place.

<div id="about-account-settings" />

## **About Account settings**

The **Account settings** page has three tabs:

* [**Profile**](/docs/account-settings#profile): Your personal account details
* [**Account**](/docs/account-settings#account): Account-level settings
* [**AI capabilities**](/docs/account-settings#ai-capabilities): Controls for AI-powered products and access

<div id="profile" />

## **Profile**

The **Profile** section displays your personal account details, such as account name, owner email, website, and account ID.

Use this section to review your account information and update supported profile fields.

<div id="account" />

## **Account**

The **Account** section includes account-level security settings. Additional self-service account settings may be added over time

<div id="unique-dev-key" />

### <Anchor target="_blank" href="/marketers/docs/dev-key-management">**Unique Dev Key**</Anchor>

The **Unique Dev Key** setting controls whether AppsFlyer creates a unique Dev key for each new app.

When the **create a unique Dev key per app for future apps** is enabled, A unique Dev Key will automatically be created for each newly added app.

Note: This setting applies only to apps created after the setting is turned on. It doesn’t change the Dev keys of existing apps.

<div id="ai-capabilities" />

## **AI capabilities**

The **AI capabilities** section lets admins manage which supported AI-powered products are available for the account.

<div id="ai-assistant" />

### <Anchor target="_blank" href="/marketers/docs/ai-assistant">AI Assistant</Anchor>

The AI Assistant is your own virtual analyst and platform knowledge helper in AppsFlyer. Use it to uncover insights, measure performance, identify top and low performers, uncover campaign trends, and explore visual insights like tables and charts, right from any page in the platform.

<div id="appsflyer-mcp" />

### <Anchor target="_blank" href="/marketers/docs/beta-appsflyer-mcp">AppsFlyer MCP</Anchor>

The AppsFlyer MCP connects your AppsFlyer data to any large language model (LLM), like Claude or VS Code. Ask questions, get performance insights, and take action directly in your AI chat

MCP is enabled by default for all accounts.

To disable MCP, go to **Account & Profile > AI capabilities**.

When the MCP is disabled:

* Users can no longer access AppsFlyer data through the MCP in external AI tools.
* Existing connections may continue working until the current session expires.
* Doesn’t affect regular API connections
* Doesn’t affect other AI capabilities in AppsFlyer

**Important:** If an MCP token is in use, you must delete it first in **Security Center > AppsFlyer Tokens**.

<div id="agent-hub" />

### <Anchor target="_blank" href="/marketers/docs/beta-agent-hub-overview">Agent Hub</Anchor>

The Agent Hub is AppsFlyer’s centralized platform for managing AI-driven agents that proactively deliver actionable marketing insights directly into your workflow. These agents constantly analyze your data to deliver valuable outputs and recommend actionable steps, all within your team's collaborative environment.

This setting is available to admins only and is enabled by default.

Disabling Agent Hub:

* Users can no longer access Agent Hub.
* All existing agents are permanently deleted and can’t be restored.
* Any active agent runs stop.
* If Agent Hub is enabled again later, users can access it again, but must create agents from scratch.

<div id="permissions" />

## **Permissions**

What you can view or edit on the **Account settings** page depends on your user permissions.

In general:

* All users may not see the same settings
* Some settings may be view-only
* Admin permissions may be required to change account-level or AI-related controls

<div data-zendesk-anchors="h_01KKRJZMP6CDDSJ6RK8QN4T30A=about-account-settings h_01KKRJZMP81BHTCA01W22CRQYG=profile h_01KKRJZMP9PQB0BZQ0931D23AH=account h_01KKRJZMPA9YTMGY0A3A883T0N=unique-dev-key h_01KKRJZMPCAMQFZM3MKQBTYFVD=ai-capabilities h_01KKRJZMPCQJBRRA0EM2EF4BYB=ai-assistant h_01KKRJZMPDZQKY9VV25EKCP5YE=appsflyer-mcp h_01KKRJZMPEHQHPRJEH9PSDTT00=agent-hub h_01KKRJZMPFQJK110AW1CDS23CW=permissions" />
