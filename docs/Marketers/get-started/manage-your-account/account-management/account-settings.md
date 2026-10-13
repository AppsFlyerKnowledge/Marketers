---
title: "Account settings"
excerpt: "Manage your personal profile, account-level security settings, and AI capabilities from a single centralized page."
x-zendesk:
  id: 44784756352273
  url: https://support.appsflyer.com/hc/en-us/articles/44784756352273-Account-settings
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Account management
  section_id: 6551191075473
  position: 0
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-negri, Marketers, Platform essentials]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2026-03-15T11:09:02Z'
  edited_at: '2026-04-16T19:36:10Z'
---
<Cards>
  <Card title="About Account settings" href="#about-account-settings" icon="fa-solid fa-user-gear" />
  <Card title="Profile" href="#profile" icon="fa-solid fa-file-lines" />
  <Card title="Account" href="#account" icon="fa-solid fa-user-gear" />
  <Card title="AI capabilities" href="#ai-capabilities" icon="fa-solid fa-robot" />
  <Card title="Permissions" href="#permissions" icon="fa-solid fa-user-gear" />
</Cards>

At a glance: Use the **Account settings** page to manage your personal profile, account-level settings, and AI capabilities from one single place.

## About Account settings

The **Account settings** page has three tabs:

- [**Profile**](#profile): Your personal account details
- [**Account**](#account): Account-level settings
- [**AI capabilities**](#ai-capabilities): Controls for AI-powered products and access

## Profile

The **Profile** section displays your personal account details, such as account name, owner email, website, and account ID.

Use this section to review your account information and update supported profile fields.

## Account

The **Account** section includes account-level security settings. Additional self-service account settings may be added over time

### [Unique Dev Key](/docs/dev-key-management)

The **Unique Dev Key** setting controls whether AppsFlyer creates a unique Dev key for each new app.

When the **create a unique Dev key per app for future apps** is enabled, A unique Dev Key will automatically be created for each newly added app.

> 📘 Note
>
> This setting applies only to apps created after the setting is turned on. It doesn’t change the Dev keys of existing apps.

## AI capabilities

The **AI capabilities** section lets admins manage which supported AI-powered products are available for the account.

### [AI Assistant](/docs/ai-assistant)

The AI Assistant is your own virtual analyst and platform knowledge helper in AppsFlyer. Use it to uncover insights, measure performance, identify top and low performers, uncover campaign trends, and explore visual insights like tables and charts, right from any page in the platform.

### [AppsFlyer MCP](/docs/beta-appsflyer-mcp)

The AppsFlyer MCP connects your AppsFlyer data to any large language model (LLM), like Claude or VS Code. Ask questions, get performance insights, and take action directly in your AI chat

MCP is enabled by default for all accounts.

To disable MCP, go to **Account & Profile > AI capabilities**.

When the MCP is disabled:

- Users can no longer access AppsFlyer data through the MCP in external AI tools.
- Existing connections may continue working until the current session expires.
- Doesn’t affect regular API connections
- Doesn’t affect other AI capabilities in AppsFlyer

> ❗️ Important
>
> If an MCP token is in use, you must delete it first in **Security Center > AppsFlyer Tokens**.

### [Agent Hub](/docs/beta-agent-hub-overview)

The Agent Hub is AppsFlyer’s centralized platform for managing AI-driven agents that proactively deliver actionable marketing insights directly into your workflow. These agents constantly analyze your data to deliver valuable outputs and recommend actionable steps, all within your team's collaborative environment.

This setting is available to admins only and is enabled by default.

Disabling Agent Hub:

- Users can no longer access Agent Hub.
- All existing agents are permanently deleted and can’t be restored.
- Any active agent runs stop.
- If Agent Hub is enabled again later, users can access it again, but must create agents from scratch.

## Permissions

What you can view or edit on the **Account settings** page depends on your user permissions.

In general:

- All users may not see the same settings
- Some settings may be view-only
- Admin permissions may be required to change account-level or AI-related controls