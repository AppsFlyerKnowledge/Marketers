---
title: '[Beta] AppsFlyer MCP'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - MCP
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-eden-locker
    - Marketers
    - MCP
  created_at: '2025-06-19T07:19:33Z'
  edited_at: '2026-10-14T10:01:56Z'
  id: 36349070304785
  locale: zh-cn
  section: AI
  section_id: 36348470056081
  url: https://support.appsflyer.com/hc/zh-cn/articles/36349070304785
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **概要：** AppsFlyer MCP 将您的 AppsFlyer 数据连接到大型语言模型（LLM），如 Claude、ChatGPT、Gemini CLI、Copilot CLI 和 VS Code。您可以在AI聊天或开发环境中直接提问、获取性能洞察，并获取AppsFlyer信息。

<Embed title="[Beta] AppsFlyer MCP" typeOfEmbed="youtube" url="https://www.youtube.com/embed/jAw7oocIx6o?si=-s107vTaTTwO076n" providerUrl="https://www.youtube.com" />

<div id="disclaimer" />

<Accordion title="声明">

**AppsFlyer MCP 服务器目前处于测试阶段，由 AppsFlyer 提供用于评估。**

通过使用它连接第三方人工智能工具，即表示您同意 AppsFlyer 对这些工具、其输出、结果、性能、运营、合法性或可靠性不承担任何责任。AppsFlyer 不控制、背书或验证这些工具及其结果，并明确否认所有明示或暗示的保证。AppsFlyer 不对此类工具的数据存储、保存、处理或使用负不负责。您完全负责确保遵守适用法律和自身内部政策。你代表你拥有所有必要的权利和同意，将这些工具连接到MCP服务器，并向他们提供访问你的数据。该服务仅为支持的使用场景提供“现状”。超出范围使用风险由您自行承担。使用受 <Anchor target="_blank" href="https://www.appsflyer.com/legal/msa/">主服务协议</Anchor>或者如果已经签署了最终协议，则该协议的条款。

</Accordion>

<div id="what-is-appsflyer-mcp" />

## 什么是AppsFlyer MCP？

AppsFlyer MCP可帮助您将LLM安全连接到AppsFlyer平台，以便您可以通过简单的对话与营销数据进行交互。借助AppsFlyer MCP，您可以基于实时数据做出更快速、更明智的决策。

MCP可以帮助您：

* 获取即时的广告活动表现、趋势和KPI。
* 比较ROAS、激活量和LTV等指标。
* 审核OneLink模板、链接和受众连接并对其进行故障排除。
* 检索配置指南或产品文档。

<div id="set-up-appsflyer-mcp" />

## 设置AppsFlyer MCP

AppsFlyer MCP 可以连接聊天助手、CLI、IDE、自动化平台和自托管代理。设置取决于你使用的客户端及其支持的认证方式。

<div id="note" />

> 📘 **注意**
>
> 有些平台可能需要管理员批准才能连接MCP服务器。如果你看不到下面描述的设置选项，请联系你的IT或工作空间管理员。

<div id="authentication-methods" />

## 认证方法

AppsFlyer MCP 支持两种认证方式。使用与你计划连接 AppsFlyer MCP 方式相匹配的方法。

| 认证方法 | 使用 | 最佳 | 访问时间 |
| --- | --- | --- | --- |
| 基于浏览器的OAuth登录 | Gemini CLI、Copilot CLI、ChatGPT、Claude.ai 和 Claude Desktop | 临时提问、探索性分析和一次性报告 | 自连接起有效期为7天。会话结束时需要重新认证 |
| 持有令牌认证 | Claude 代码、自动化平台、自托管代理及集成 | 自动化、定时任务、后台代理和非交互式工作流程 | 有效直到被人工撤销 |

<div id="browser-based-oauth-login" />

### 基于浏览器的OAuth登录

基于浏览器的OAuth登录允许您通过浏览器进行交互式连接。连接后，MCP客户端会打开浏览器窗口，要求你登录AppsFlyer。在你批准访问权限后，客户端会连接到你的AppsFlyer账户。

将此方法用于互动会议、探索性分析和一次性报告。

<div id="bearer-token-authentication" />

### 持有令牌认证

持有令牌认证允许非交互式工具通过使用 AppsFlyer MCP 令牌连接到 AppsFlyer MCP。令牌通过请求头传递：

```http
Authorization: Bearer <YOUR_MCP_TOKEN>
```

这种方法适用于自动化、定时任务、后台代理以及无法使用浏览器登录的集成。

要创建令牌，请前往 **账户菜单 > 安全中心 > AppsFlyer 代币** 并创建一个MCP令牌。

<div id="set-up-by-client" />

## 由客户设置

<div id="h_claude-ai-and-claude-desktop" />

<Accordion title="Claude.ai 和 Claude 桌面">

使用 Claude.ai 和Claude桌面版，并使用基于浏览器的OAuth登录。这些说明适用于 Claude 的网页版和桌面版。

<div id="note-1" />

> 📘 **注意**
>
> 对于团队和企业计划用户，只有所有者或管理员可以添加全组织的集成。

<div id="set-up-claude-chat-and-cowork" />

#### 设置 Claude.ai 和Claude桌面

1. 点击左下角你的名字并选择 **背景设定**.或者，在新聊天中点击 **搜索与工具** > **管理连接器**.
2. 打开<Anchor target="_blank" href="https://claude.ai/settings/integrations">连接器</Anchor>标签页。
3. 切换到**组织连接器**标签页。
4. 在连接器部分中，单击**添加连接器。**
5. 请输入以下连接器细节：
   * Connector name：AppsFlyer
   * **连接器网址：** `https://mcp.appsflyer.com/auth/mcp`
6. 点击**添加**。
7. 切换到**您的连接器**标签页。
8. 在连接器部分中，单击AppsFlyer连接旁边的**连接** 。
9. 按提示登录AppsFlyer。

<div id="note-2" />

<div id="test-the-claude-connection" />

#### 测试Claude连接

1. 在任意聊天窗口中，点击设置按钮。   
   <Image alt="" src="https://files.readme.io/5f27783a0743f9005c5df4f580455777aa3ef612feb220d1058664ee63431cf3-46334217789073.png" width="25%" />
2. 如果 AppsFlyer MCP 设置正确，菜单中会出现 AppsFlyer 工具。

</Accordion>

<div id="h_claude-code" />

<Accordion title="克劳德密码">

使用Claude Code配合持有令牌认证进行自动化、调度和非交互式工作流程。

<div id="add-appsflyer-mcp-to-claude-code" />

#### 将 AppsFlyer MCP 添加到 Claude Code

1. 在 AppsFlyer 中，前往 **账户菜单 > 安全中心 > AppsFlyer 代币**.
2. 创建一个MCP令牌。
3. 在终端中，添加 AppsFlyer MCP 服务器：

   ```bash
   claude mcp add-json appsflyer '{"type":"http","url":"https://mcp.appsflyer.com/auth/mcp","headers":{"Authorization":"Bearer YOUR_APPSFLYER_MCP_TOKEN"}}'
   ```
4. 启动Claude代码：

   ```bash
   claude .
   ```
5. 确认MCP服务器已被添加：

   ```bash
   claude mcp list
   ```
6. 确认这一点 `appsflyer` 出现在配置好的MCP服务器列表中。
7. 提出AppsFlyer的问题。使用场景示例:

   ```text
   What apps are in my AppsFlyer account?
   ```

   ```text
   What were my top media sources in the US last week for "Mypets.android.com"?
   ```

   ```text
   Create a summary of the performance of "Mypets.android.com" in the last day, segmented by campaign.
   ```

</Accordion>

<div id="h_cursor-ide" />

<Accordion title="Cursor IDE">

使用光标IDE将AppsFlyer MCP从本地开发环境连接起来。

1. 根据使用范围创建或打开配置文件：
   * **全局配置：** `~/.cursor/mcp.json`
   * **项目特定配置：** `.cursor/mcp.json`
2. 在JSON文件的字段下`mcpServers`添加以下内容mcpServers：

   ```json
   {
     "mcpServers": {
       "appsflyer": {
         "url": "https://mcp.appsflyer.com/auth/mcp"
       }
     }
   }
   ```
3. 重启Cursor IDE以应用新配置。
4. 当提示访问 AppsFlyer MCP 服务时进行身份验证。

</Accordion>

<div id="h_vs-code" />

<Accordion title="VS Code">

1. 按下`Cmd+Shift+P`或`Ctrl+Shift+P`，打开Command Palette。
2. 选择**Configure MCP Servers**。
3. 在 `.vscode/mcp.json`， 添加 AppsFlyer MCP 服务器配置：

   ```json
   {
     "servers": {
       "appsflyer": {
         "url": "https://mcp.appsflyer.com/auth/mcp"
       }
     }
   }
   ```
4. 保存文件并重启Copilot Chat。

</Accordion>

<div id="h_chatgpt" />

<Accordion title="ChatGPT">

使用 ChatGPT 和 AppsFlyer MCP 有两种方式。

* [定制GPT](#添加appsflyer自定义gpt):最适合简单访问AppsFlyer助理。
* [ChatGPT中的MCP](#在chatgpt中添加appsflyer-mcp):最适合想将 AppsFlyer 数据带入 ChatGPT 对话的用户。

<div id="add-the-appsflyer-custom-gpt" />

#### 添加AppsFlyer自定义GPT

1. 咔哒 <Anchor target="_blank" href="https://chatgpt.com/g/g-68b6a92eb8e0819194cbb81e1e635c0d-appsflyer">AppsFlyer 定制 GPT</Anchor>.
2. 把GPT保存到侧边栏，方便访问。
3. 打开自定义GPT。
4. 问个问题。使用场景示例:

   ```text
   Show me my Meta campaign performance from last week.
   ```

<div id="add-appsflyer-mcp-in-chatgpt" />

#### 在ChatGPT中添加AppsFlyer MCP

<div id="note-3" />

> 📘 **注意**
>
> 可能需要管理员设置才能添加并发布连接器到你的组织。

1. 添加一个连接器并将其发布到你的组织。
2. 请输入以下连接器细节：
   * **姓名：** AppsFlyer MCP
   * URL
   * **身份验证**：OAuth
3. 首次连接，请访问 **AppsFlyer MCP > 应用> 和资源设置**.
4. 连接AppsFlyer MCP。
5. 按照步骤连接并使用您的AppsFlyer凭证登录。

设置好后，打开聊天，选择 **资料来源** 或 **连接器**，并打开AppsFlyer连接。

出于安全考虑，AppsFlyer MCP 大约每 10 小时断开一次连接。要重新连接，重复连接流程。

</Accordion>

<div id="h_gemini-cli" />

<Accordion title="Gemini CLI">

使用基于浏览器的 OAuth 登录的 Gemini CLI。

#### Add AppsFlyer MCP to Gemini CLI

1. 在终端中，添加 AppsFlyer MCP 服务器：

   ```bash
   gemini mcp add appsflyer https://mcp.appsflyer.com/auth/mcp -t http
   ```
2. 启动双子座CLI：

   ```bash
   gemini
   ```
3. 在 Gemini CLI 提示中输入：

   ```text
   auth
   ```
4. 在浏览器中完成认证流程，然后返回终端。
5. 提出AppsFlyer的问题。使用场景示例:

   ```text
   What apps are in my AppsFlyer account?
   ```

<div id="troubleshoot-gemini-cli-authentication" />

#### 排查Gemini CLI认证

如果认证失败，启动 Gemini CLI 的调试模式：

```bash
GEMINI_LOG_LEVEL=debug gemini
```

那就进去 `auth` 同样出现在 Gemini CLI 提示符中。

</Accordion>

<div id="h_copilot-cli" />

<Accordion title="Copilot CLI">

使用Copilot CLI并基于浏览器的OAuth登录。

<div id="add-appsflyer-mcp-to-copilot-cli" />

#### 将 AppsFlyer MCP 添加到 Copilot CLI

1. 打开终端。
2. 启动副驾驶CLI：

   ```bash
   copilot
   ```
3. 如果您尚未登录，请在 Copilot CLI 提示符中输入以下命令：

   ```text
   /login
   ```
4. 完成浏览器登录。
5. 在 Copilot CLI 提示中输入：

   ```text
   /mcp add
   ```
6. 请输入以下MCP服务器详情：

| 字段 | 价值 |
| --- | --- |
| 服务器名称 | `appsflyer` |
| 服务器类型 | `HTTP` |
| URL | `https://mcp.appsflyer.com/auth/mcp` |
| 工具 | `*` |

7. 媒体 **Ctrl+S** 为了保存配置。
8. 当提示时，在浏览器中完成 AppsFlyer 认证流程。
9. 返回终端。
10. 提出AppsFlyer的问题。使用场景示例:

    ```text
    What apps are in my AppsFlyer account?
    ```

</Accordion>

<div id="h_third-party-and-self-hosted-platforms" />

<Accordion title="第三方和自架平台">

使用MCP令牌通过AppsFlyer MCP认证第三方或自主机系统。这支持与n8n、Make或你自己的大型语言模型代理等平台的自动化和AI集成。

MCP 令牌是一个账户级别的持有人令牌，继承创建它的管理员的权限。你可以从以下渠道访问和管理它 <Anchor target="_blank" href="/marketers/zh/docs/managing-appsflyer-tokens">Security Center > AppsFlyer 代币</Anchor>.

<div id="mcp-connection-details" />

#### MCP连接详情

要将您的自动化或代理平台连接到 AppsFlyer MCP，请使用以下配置：

* **认证类型：** 持有人令牌
* **基础网址 / 端点：** `https://mcp.appsflyer.com/auth/mcp`
* **持有人代币：** 你的MCP令牌

<div id="note-4" />

> 📘 **注意**
>
> 切勿公开分享或发布你的代币。把它当作私人凭证。你的MCP令牌可以直接访问你的MCP环境。

<div id="example-use-cases" />

#### 使用场景示例

| 类别 | 示例 |
| --- | --- |
| 海关代理 | 构建一个使用 MCP 获取数据、分析数据并发送推荐的 AI 代理。 |
| 大型语言模型集成 | 让自托管的LLM通过MCP进行绩效指标。 |

</Accordion>

<div id="h_other-platforms" />

<Accordion title="其他平台">

默认情况下，只有上述平台被启用。如需连接其他平台，请联系您的CSM或发送电子邮件至 [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<div id="h_use-multiple-accounts-or-agencies" />

<Accordion title="使用多个账户或代理机构">

AppsFlyer MCP 一次连接一个 AppsFlyer 账户。

<div id="switch-between-accounts-browser-based-oauth" />

#### 在账户间切换（基于浏览器的OAuth）

如果你在同一邮箱下管理多个AppsFlyer账户，你可以切换MCP连接的账户：

1. 在AppsFlyer里，把你想连接的账户设为你的主账户。
2. 在你的MCP客户端重新登录。

你不能在同一次连接中并排查看或查询多个账户。

<div id="connect-multiple-accounts-simultaneously-bearer-token" />

#### 同时连接多个账户（持有人令牌）

例如，为了同时连接多个账户，例如用于代理机构，可以使用多代理流程代替基于浏览器的OAuth：

1. 每个账户，创建一个MCP令牌 **账户菜单 > 安全中心 > AppsFlyer 代币**.
2. 在你的代理平台中，分别使用其持有人代币连接每个账户。

请参见该流程的示例 <Anchor target="_blank" href="https://www.youtube.com/watch?v=o5oK-yWuE5E">本视频</Anchor>.

</Accordion>

<div id="use-appsflyer-mcp" />

## 使用 AppsFlyer MCP

<div id="use-cases-and-prompts" />

### 使用场景与示例提示

AppsFlyer MCP为您提供了一套工具和资源，旨在帮助您获取营销分析、效果洞察，并执行配置任务。

<div id="h_01M6DQ8W2JQ9ECH5VEZPRT7221" />

<div id="h_analyze-incrementality-experiments" />

<div id="h_analyze-creative-performance" />

<div id="note-6" />

<div id="note-5" />

<div id="important" />

> 🚧 **重要提示！**
>
> 通过AppsFlyer MCP生成的答案，仅在以下支持的使用场景中是可靠的。超出这些范围的回答未经AppsFlyer验证，可能不准确或具有误导性。对于不在MCP对接预期范围内的AI生成结果，我们无法保证其准确性。

一些使用场景与示例提示包括：

<div id="analyze-performance" />

<Accordion title="表现分析">

了解实时汇总营销绩效数据。您可以识别效果最佳和效果不佳的广告系列，进行对比、发掘趋势并并获取洞察，以帮助指导决策。

**提示词：** “上周Mypets.android.com在美国表现最佳的媒体渠道有哪些？”

**预期的AI响应：** 返回表现最佳的媒体渠道，包括激活量、收入和ROAS。

**提示词：** “哪个广告活动的ROAS最高且总激活量不低于5000？”

**预期的AI响应：** 识别并对符合条件的广告活动排序，提供效果洞察。

**提示词：** “昨天Mypets.android.com应用在中国的激活量是多少？”

**预期的AI响应：** 返回该应用当天在中国的激活数量。

**提示词：** “按活动划分，制作 Mypets.android.com 最后一天表现的总结。”

**预期的AI响应：** 返回按广告活动分组的效果报告。

**提示词：** “比较上周和前一周的D1留存率，按媒体来源分组。”

**预期的AI响应：** 该AI对D1的留存率进行了逐周比较，按媒体来源分组。

</Accordion>

<div id="analyze-skan-performance" />

<Accordion title="分析SKAN表现">

利用苹果的SKAdNetwork框架，深入了解iOS广告活动的表现。识别表现最佳的活动，分析KPI趋势，以支持决策。

**提示词：** “过去一个月各网络的投资回报率是多少？”

**预期的AI响应：** AI会检索选定期间的投资回报率结果，并突出显示顶级网络。

**提示词：** “哪些竞选的CPI最低？”

**预期的AI响应：** AI会识别CPI最低的广告活动，排名表现最佳的广告。

**提示词：** “过去一个月活动af\_subscribed每周转化率是多少？”

**预期的AI响应：** AI会逐周细分活动的转化率，并显示整体趋势。

**提示词：** “哪些网络的空率最高，哪些活动的空率最高？”

**预期的AI响应：** AI识别出无效率最高的网络，并列出对这些率贡献最大的广告活动。

</Accordion>

<div id="onelink-management" />

<Accordion title="OneLink管理">

查询并审核OneLink模板和链接，确保路由一致性和用户路径准确性，MCP可以帮助你排查问题并验证大规模链路设置。

**提示词：** “审核‘HolidayPush2025’模板，并展示所有带参数的链接。”

**预期的AI响应：** AI返回一个包含短链接和相关参数值的CSV表。

**提示词：** “为什么这个OneLink会将现有用户重定向到App Store？”

**预期的AI响应：** AI会根据链路参数和后备逻辑返回故障排查洞察。

**提示词：** “列出TravelBuddy应用所有支持二维码的OneLink。”

**预期的AI响应：** 返回包含二维码链接和相关元数据的OneLink列表。

</Accordion>

<div id="knowledge-base-and-developer-support" />

<Accordion title="知识库和开发人员支持">

快速访问AppsFlyer文档和DevHub资源。在AI聊天中直接获取SDK配置、产品行为和衡量逻辑的准确答案。

**提示词：** “如何在Android上配置应用内事件去重？”

**预期的AI响应：** 提供配置步骤、代码示例和最佳实践。

**提示词：** “TikTok激活的归因回溯期是多少？”

**预期的AI响应：** AI解释了最新的平台特定归因规则。

**提示词：** “使用AppsFlyer优化应用ROAS的最佳方法是什么？”

**预期的AI响应：** 提供策略方向，例如用户细分、合作渠道优化和LTV衡量最佳实践。

</Accordion>

<div id="apps-management" />

<Accordion title="应用管理">

获取关键应用配置细节，如归因窗口、会话超时、重新参与设置等。利用这些信息来审计和比较你的投资组合中的应用设置。

**提示词：** “我的游戏应用的归因回溯期是多少？”

**预期的AI响应：** 列出应用及其归因回溯期，并标注与标准值的差异。

**提示词：** “哪些应用设置了不同的回溯期？”

**预期的AI响应：** 列出回溯期不一致的应用及其配置值。

**提示词：** “请列出我所有已置顶的活跃iOS应用。”

**预期的AI响应：** 返回已置顶且活跃的iOS应用列表，包括应用ID和名称。

**提示词：** “AppsFlyer游戏应用当前的打开超时是多少？这会影响再营销归因吗？”

**预期的AI响应：** 返回打开超时设置，并解释其对再营销归因的影响。

</Accordion>

<div id="audiences-management" />

<Accordion title="受众共享管理">

### 受众共享管理

即时了解受众结构、归属、合作渠道连接和活跃测试情况，监控上传状态，检测连接失败，识别过时受众，并理解每个受众的配置方式。利用这些信息简化跨职能的活动管理。

**提示词：** “给我FinancePro应用的所有活跃受众。”

**预期的AI响应：** AI返回一份包含创建日期、所有者和合作伙伴等元数据的受众列表。

**提示词：** “谁最后更新了‘Churned Users - Tier A’受众？”

**预期的AI响应：** AI会返回带有最后修改时间戳的用户ID或电子邮件。

**提示词：** “列出当前与Meta和TikTok进行分测的所有受众。”

**预期的AI响应：** 列出活跃受众及其测试配置和分配比例。

**提示词：** “我想测试莫洛科对抗......谷歌，给我所有与谷歌相关的受众。”

**预期的AI响应：** AI返回与谷歌关联的受众列表及其当前状态和配置。

**提示词：** “我快要关闭（网络）了，给我一份活跃观众名单。”

**预期的AI响应：** AI会返回所有活跃受众及其已连接的合作伙伴和当前状态。

**提示词：** “给我一份所有活跃观众、他们已连接的伴侣以及当前分段名单。”

**预期的AI响应：** AI会返回每个合作伙伴连接及其拆分百分比的完整受众列表。

**提示词：** “我的Meta观众现在有上传失败吗？”

**预期的AI响应：** AI返回一份与Meta连接的受众列表，这些受众上传失败，包括每个受众的错误信息。

**提示词：** “我想检查一下我的TikTok活动，哪些与TikTok相关受众失败了，从什么时候开始的？”

**预期的AI响应：** AI会返回所有与TikTok相关的观众，显示其失败状态和最后成功上传时间。

**提示词：** “给我所有在过去7天内没有成功上传的观众。”

**预期的AI响应：** AI会返回过去7天内无成功上传的受众列表及其当前连接状态。

</Accordion>

<div id="feedback-tool" />

<Accordion title="反馈工具">

您可以通过助手界面直接提交关于AppsFlyer MCP的使用反馈，您的反馈帮助我们改进并塑造产品的未来。

**提示词：** “分析工具提供的洞察非常棒，对决策帮助很大。我希望在分析中加入应用内事件测量作为选项。”

**预期的AI响应：** AI会将反馈提交给AppsFlyer MCP产品团队。

</Accordion>

<div id="cost-configuration-integration" />

<Accordion title="成本配置集成">

通过成本配置MCP，您可以对您的成本数据进行可视化和控制。这种集成帮助你最大化成本覆盖，及早发现集成缺口，并保持整个广告网络的成本数据完整且准确。

**提示词：** “我的AppsFlyer账户里有哪些有效的成本集成？”

**预期的AI响应：** AI会列出你AppsFlyer账户中所有已启用的成本集成，以及它们关联的应用ID和当前状态。

**提示词：** “给我看看我在当前成本整合中遇到的问题。”

**预期的AI响应：** AI显示了过去7天内出现问题的活跃成本集成，按广告网络和连接应用排序。

**提示词：** “根据我最近的归因数据，我应该连接哪些成本集成？”

**预期的AI响应：** AI会根据应用的近期流量排名，显示支持成本集成但尚未连接的广告网络。

</Accordion>

<div id="ad-revenue-integrations" />

<Accordion title="20+ 广告收入对接">

通过 AppsFlyer MCP，获得对广告收入集成的可视化和控制。你可以使用MCP确认哪些广告收入集成已启用，监控其健康状况，及早发现缺口，并保持广告收入数据在应用和变现合作伙伴间的稳定流动。

**提示词：** “我的AppsFlyer账户中有哪些活跃的广告收入集成？”

**预期的AI响应：** AI会列出你AppsFlyer账户中所有已启用的广告收入集成，包括已连接的应用和当前的集成状态。

**提示词：** “给我看看我在活跃广告收入集成中遇到的问题。”

**预期的AI响应：** AI显示支持了过去7天内出现问题的广告收入集成，按调解合作伙伴、集成类型和应用进行分组。

</Accordion>

<div id="user-management-and-role-control" />

<Accordion title="用户管理和角色控制">

从你的AppsFlyer账户中获取用户和角色信息。这有助于管理员保持清晰的用户数据库并高效管理访问控制。

**提示词：** “列出最近6个月未登录的非活跃用户。”

**预期的AI响应：** AI会返回超过6个月以上的最后登录日期，甚至完全没有登录，包括电子邮件地址、角色和最后登录时间戳。

**提示词：** “按权限等级列出所有用户，并标注管理员用户。”

**预期的AI响应：** AI按角色类型组织用户，并突出显示管理员用户，包括相关的应用和地理访问权限。

**提示词：** “有团队成员反映无法登录AppsFlyer，能否检查该用户是否存在以及状态如何？”

**预期的AI响应：** AI会验证用户是否存在，并返回用户当前角色、相关应用、最后登录日期及潜在访问限制。

**提示词：** “哪些用户可以访问超过5个应用？他们的角色是什么？”

**预期的AI响应：** AI让用户获得了广泛的应用访问权限、他们的角色以及他们可访问的完整应用列表。

</Accordion>

<div id="other-information" />

## 其他信息

<div id="h_privacy-and-security" />

<Accordion title="安全与隐私">

AppsFlyer MCP 允许您选择的 AI 工具基于现有权限查询 AppsFlyer 数据。

<div id="data-processing" />

#### 数据处理

AppsFlyer MCP作为安全代理，它实时获取 AppsFlyer 数据，返回回答查询所需的数据。AppsFlyer MCP 不会长期归档或存储查询结果。

<div id="credentials" />

#### 登录信息

你的 AppsFlyer 登录让 AppsFlyer MCP 代表你调用 API。你的AppsFlyer凭证不会与AI工具共享。

<div id="permissions" />

#### 授权

AppsFlyer MCP 使用您已有的 AppsFlyer 权限。用户只能访问他们已在 AppsFlyer 中获得权限查看的应用和数据。

没有单独的权限层来配置MCP访问。

<div id="read-and-write-access" />

#### 只读访问

AppsFlyer MCP 目前仅为读取和查询。没有你，它不会在 AppsFlyer 里采取行动。

<div id="ai-provider-data-usage" />

#### 人工智能提供商数据的使用

AppsFlyer MCP检索的数据可能会与您选择的AI工具共享，以回答您的疑问。仅共享生成响应所需的数据。

AppsFlyer 无法控制您所选的 AI 工具是否存储、处理或从数据中学习。在连接AppsFlyer MCP之前，请先阅读您的AI服务提供商的条款和数据使用政策。

<div id="certifications" />

#### 认证

AppsFlyer 获得了 ISO 27001 和 SOC 2 认证。ISO 42001认证正在进行中。

</Accordion>

<div id="tool-mapping" />

<Accordion title="工具映射">

默认情况下，所有工具均已启用。建议您保持启用状态，以确保功能完整，避免使用过程中出现问题。

每个工具都会映射到一个功能类别，例如表现分析、应用管理或OneLink管理。有些类别可能包含多种工具。

以下为有关工具及其类别映射的完整列表。

<table><thead><tr><th>类别</th><th>工具</th><th>说明</th></tr></thead><tbody><tr><td><a href="#analyze-performance">表现分析</a></td><td>fetch_aggregated_data</td><td>获取汇总面板数据，可自定义日期范围、分组、指标和筛选条件</td></tr><tr><td rowspan="2"><a href="#apps-management">应用管理</a></td><td>get_apps</td><td>列出所有有权限的应用，并按已置顶/未置顶状态及转移请求分类</td></tr><tr><td>get_app_settings</td><td>获取所有应用的配置，包括归因窗口、隐私控制、打开管理和平台特定配置。</td></tr><tr><td><a href="#cost-configuration-integration">成本配置集成</a></td><td><p>get_active_cost_integrations</p><p>list_cost_supported_media_source</p></td><td>获取账户中活跃成本集成状态和缺失成本整合的概览。</td></tr><tr><td>20+ 广告收入对接</td><td><p>list_adrevenue_supported_media_sources</p><p>get_active_adrevenue_integrations</p></td><td>检查哪些集成已启用，监控健康状况，检测配置缺口，并帮助保持广告收入数据的一致性。</td></tr><tr><td><a href="#analyze-skan-performance">SKAN表现</a></td><td>skan_get_app_data</td><td>检索按网络、活动或事件在自定义日期区间分组的 SKAN 绩效汇总数据。</td></tr><tr><td rowspan="3"><a href="#onelink-management">OneLink管理</a></td><td>get_onelink_templates</td><td>列出所有OneLink模板。</td></tr><tr><td>get_onelink_template_links</td><td>获取从特定模板生成的所有OneLink链接</td></tr><tr><td>get_onelink_details</td><td>获取特定OneLink的配置详情。</td></tr><tr><td rowspan="3"><a href="#audiences-management">受众共享管理</a></td><td>list_active_audiences</td><td>列出所有每天计算的活跃受众。</td></tr><tr><td>list_audiences_connections</td><td>列出所有广告合作渠道的受众数据对接。</td></tr><tr><td>get_audience_connections</td><td>获取特定受众的合作渠道对接信息。</td></tr><tr><td><a href="#knowledge-base-and-developer-support">知识库和开发人员支持</a></td><td>get_public_knowledge</td><td>搜索 AppsFlyer 知识库和 DevHub 文档。</td></tr><tr><td><a href="#feedback-tool">反馈工具</a></td><td>send_feedback</td><td>提交有关工具或系统的反馈。</td></tr><tr><td><a href="#user-management-and-role-control">用户管理和角色控制</a></td><td>get_users</td><td>列出AppsFlyer的用户和角色。</td></tr></tbody></table>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特点与局限性">

| 特点 | 说明 |
| --- | --- |
| 多账户使用 | AppsFlyer MCP仅使用默认账号的数据要切换账户或同时连接多个账户，请参见 [使用多个账户或代理机构](#h_use-multiple-accounts-or-agencies). |
| OneLink链接 | <ul><li>仅包含从 OneLink 管理页面创建的链接，不包括 API、SDK 或批量创建的链接。</li><li>不返回单平台链接，也就是旧链接。</li></ul> |
| 频次限制 | <ul><li>数据分析：每分钟最多350个请求。</li><li>Audiences：每分钟最多可发送350个请求</li><li>SKAN：每个查询最多可达10,000行</li></ul> |
| 日期范围 | <ul><li>数据分析：3年</li><li>SKAN：每次请求最多90天</li></ul> |
| 分组限制 | <ul><li>数据分析：每次请求最多4个分组</li><li>SKAN：如同 <Anchor target="_blank" href="/marketers/zh/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#metrics">SKAN 仪表盘</Anchor></li></ul> |
| 应用限制 | <ul><li>数据分析：每次请求最多10个应用</li><li>SKAN：每个请求只能用一个应用，仅限 iOS</li></ul> |
| 支持的维度 | 分析支持“我的仪表盘”中所有可用的维度。 |
| 汇总数据 | 支持汇总数据。这包括每周和每月的粒度级别以及自定义指标。 |
| 时效性 | SKAN数据可获得最长3天延迟，UTC时间。 |
| 货币与时区 | SKAN数据默认以美元计价。替代货币的支持方式包括 `revenue_alt = true`.数据以UTC时间报告。 |
| 禁用MCP | <ul><li>MCP 默认启用，管理员可以关闭 **账户与个人资料>人工智能能力**.</li><li>禁用 MCP 后，用户无法通过外部 AI 工具中的 MCP 访问 AppsFlyer 数据。</li><li>现有连接可能会持续到当前会话结束。</li><li>禁用MCP不会影响AppsFlyer中的常规API连接或其他AI功能。</li><li>如果有 MCP 令牌正在使用，请先删除它 **Security Center > AppsFlyer 代币**.</li></ul> |

</Accordion>

<div id="troubleshoot-connection-issues" />

## 排查连接问题

如果AppsFlyer MCP连接无法使用，请按照你的身份验证方式操作。

<div id="h_troubleshoot-browser-based-oauth-login" />

<Accordion title="基于浏览器的OAuth登录">

对于通过浏览器登录连接的客户端，如Gemini CLI、Copilot CLI、ChatGPT、Claude.ai 和Claude Desktop，可以使用本部分。

1. <strong>重新认证你的会话。</strong>OAuth 的课程大约每7天到期一次。重新运行连接流程，并重新完成浏览器登录。
2. <strong>完成认证流程。</strong>确保浏览器登录成功完成。提示时，点击 **允许** 或 **批准**然后返回你的MCP客户端。
3. <strong>重新开始游戏。</strong>重启你的CLI、聊天或应用会话。然后重新连接到MCP服务器。
4. <strong>验证MCP服务器配置。</strong>请确认以下数值：

| 字段 | 价值 |
| --- | --- |
| 服务器类型 | `HTTP` |
| URL | `https://mcp.appsflyer.com/auth/mcp` |

5. <strong>检查用户权限。</strong>确保你的AppsFlyer用户能够访问相关的应用和请求的数据。

</Accordion>

<div id="h_troubleshoot-bearer-token-authentication" />

<Accordion title="持有令牌认证">

使用此部分用于Claude Code、n8n、Make、自架代理及其他自动化工具。

1. <strong>检查令牌是否被吊销。</strong>代币可以手动撤销。之前创建的代币 **2026年3月10日，19：00 UTC** 可能已经不管用了。
2. <strong>创建一个新的MCP令牌。</strong>恢复访问权限：
   1. 登录AppsFlyer。
   2. 前往 **账户菜单>安全中心>令牌管理**.
   3. 查找被吊销的代币。
   4. 删除被吊销的代币。
   5. 创建一个新的MCP令牌。
   6. 用新的令牌更新你的MCP客户端或自动化。
3. <strong>请查看授权首部。</strong>确保头部使用完全相同的格式：

   ```http
   Authorization: Bearer <YOUR_MCP_TOKEN>
   ```
4. <strong>验证MCP服务器配置。</strong>请确认以下数值：

| 字段 | 价值 |
| --- | --- |
| URL | `https://mcp.appsflyer.com/auth/mcp` |
| 交通 | `HTTP` |
| 页面标题 | `Authorization: Bearer` |

5. <strong>确认服务器已注册。</strong>对于 Claude Code，运行：

   ```bash
   claude mcp list
   ```
6. **如果需要，重新添加MCP服务器。**

   ```bash
   claude mcp remove appsflyer
   claude mcp add-json appsflyer '{"type":"http","url":"https://mcp.appsflyer.com/auth/mcp","headers":{"Authorization":"Bearer YOUR_APPSFLYER_MCP_TOKEN"}}'
   ```
7. <strong>检查代币权限。</strong>MCP 令牌继承了创建它的管理员的权限。确保令牌能访问相关应用和请求的数据。

</Accordion>

<div id="h_access-and-permission-issues" />

<Accordion title="访问和权限问题">

如果认证成功但访问仍然失败：

* MCP的访问权限可能会被你的AppsFlyer管理员限制。
* 如果你无法访问账户和个人资料设置，MCP的访问权限可能会被阻止。
* 请联系您的AppsFlyer管理员以启用访问权限。
* 确保你的用户或令牌能够访问相关的应用和请求的数据。

</Accordion>

<div id="h_general-connection-checks" />

<Accordion title="一般检查">

如果问题依旧：

* 确保你的客户支持MCP。
* 检查网络或防火墙限制是否阻挡了MCP端点。
* 请确认MCP的网址是否正确：

  ```text
  https://mcp.appsflyer.com/auth/mcp
  ```
* 尝试从新的会话或环境重新连接。

</Accordion>

<div data-zendesk-anchors="h_01K9CJ9WQ3JJSYWDMNJ5GP7N04=disclaimer what-is-appsflyer-mcp=%E4%BB%80%E4%B9%88%E6%98%AFappsflyer-mcp h_01JY3G849QAT2GC714FR6CADH2=%E4%BB%80%E4%B9%88%E6%98%AFappsflyer-mcp h_set-up-appsflyer-mcp=%E8%AE%BE%E7%BD%AEappsflyer-mcp set-up-appsflyer-mcp=%E8%AE%BE%E7%BD%AEappsflyer-mcp h_01KT8Y9JEJEZ26BRHK530JDB0D=%E6%B3%A8%E6%84%8F h_authentication-methods=%E8%AE%A4%E8%AF%81%E6%96%B9%E6%B3%95 authentication-methods=%E8%AE%A4%E8%AF%81%E6%96%B9%E6%B3%95 h_browser-based-oauth-login=%E5%9F%BA%E4%BA%8E%E6%B5%8F%E8%A7%88%E5%99%A8%E7%9A%84oauth%E7%99%BB%E5%BD%95 browser-based-oauth-login=%E5%9F%BA%E4%BA%8E%E6%B5%8F%E8%A7%88%E5%99%A8%E7%9A%84oauth%E7%99%BB%E5%BD%95 h_bearer-token-authentication=%E6%8C%81%E6%9C%89%E4%BB%A4%E7%89%8C%E8%AE%A4%E8%AF%81 bearer-token-authentication=%E6%8C%81%E6%9C%89%E4%BB%A4%E7%89%8C%E8%AE%A4%E8%AF%81 h_set-up-by-client=%E7%94%B1%E5%AE%A2%E6%88%B7%E8%AE%BE%E7%BD%AE set-up-by-client=%E7%94%B1%E5%AE%A2%E6%88%B7%E8%AE%BE%E7%BD%AE claude-ai-and-claude-desktop=h_claude-ai-and-claude-desktop h_01KT8Y9JEJQNXK3SZ7M0ETH5RN=%E6%B3%A8%E6%84%8F-1 h_set-up-claude-ai-and-desktop=%E8%AE%BE%E7%BD%AE-claudeai-%E5%92%8Cclaude%E6%A1%8C%E9%9D%A2 set-up-claude-ai-and-desktop=%E8%AE%BE%E7%BD%AE-claudeai-%E5%92%8Cclaude%E6%A1%8C%E9%9D%A2 h_test-claude-connection=%E6%B5%8B%E8%AF%95claude%E8%BF%9E%E6%8E%A5 test-claude-connection=%E6%B5%8B%E8%AF%95claude%E8%BF%9E%E6%8E%A5 claude-code=h_claude-code h_add-appsflyer-mcp-to-claude-code=%E5%B0%86-appsflyer-mcp-%E6%B7%BB%E5%8A%A0%E5%88%B0-claude-code add-appsflyer-mcp-to-claude-code=%E5%B0%86-appsflyer-mcp-%E6%B7%BB%E5%8A%A0%E5%88%B0-claude-code cursor-ide=h_cursor-ide vs-code=h_vs-code chatgpt=h_chatgpt custom-gpt-available-for-all-packages-including-free-enterprise=%E6%B7%BB%E5%8A%A0appsflyer%E8%87%AA%E5%AE%9A%E4%B9%89gpt mcp-in-chatgpt-supported-for-chatgpt-users-on-all-paid-plans=%E5%9C%A8chatgpt%E4%B8%AD%E6%B7%BB%E5%8A%A0appsflyer-mcp h_01KT8Y9JEJ806MVHJACM0VNM0K=%E6%B3%A8%E6%84%8F-2 gemini-cli=h_gemini-cli h_add-appsflyer-mcp-to-gemini-cli=add-appsflyer-mcp-to-gemini-cli h_troubleshoot-gemini-cli-authentication=%E6%8E%92%E6%9F%A5gemini-cli%E8%AE%A4%E8%AF%81 troubleshoot-gemini-cli-authentication=%E6%8E%92%E6%9F%A5gemini-cli%E8%AE%A4%E8%AF%81 copilot-cli=h_copilot-cli h_add-appsflyer-mcp-to-copilot-cli=%E5%B0%86-appsflyer-mcp-%E6%B7%BB%E5%8A%A0%E5%88%B0-copilot-cli add-appsflyer-mcp-to-copilot-cli=%E5%B0%86-appsflyer-mcp-%E6%B7%BB%E5%8A%A0%E5%88%B0-copilot-cli third-party-and-self-hosted-platforms=h_third-party-and-self-hosted-platforms h_mcp-connection-details=mcp%E8%BF%9E%E6%8E%A5%E8%AF%A6%E6%83%85 mcp-connection-details=mcp%E8%BF%9E%E6%8E%A5%E8%AF%A6%E6%83%85 h_01KT8Y9JEKZRB56RZJXMMN4WV0=%E6%B3%A8%E6%84%8F-3 h_example-use-cases=%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF%E7%A4%BA%E4%BE%8B example-use-cases=%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF%E7%A4%BA%E4%BE%8B other-platforms=h_other-platforms use-multiple-accounts-or-agencies=h_use-multiple-accounts-or-agencies h_switch-between-accounts=%E5%9C%A8%E8%B4%A6%E6%88%B7%E9%97%B4%E5%88%87%E6%8D%A2%E5%9F%BA%E4%BA%8E%E6%B5%8F%E8%A7%88%E5%99%A8%E7%9A%84oauth switch-between-accounts=%E5%9C%A8%E8%B4%A6%E6%88%B7%E9%97%B4%E5%88%87%E6%8D%A2%E5%9F%BA%E4%BA%8E%E6%B5%8F%E8%A7%88%E5%99%A8%E7%9A%84oauth h_connect-multiple-accounts-simultaneously=%E5%90%8C%E6%97%B6%E8%BF%9E%E6%8E%A5%E5%A4%9A%E4%B8%AA%E8%B4%A6%E6%88%B7%E6%8C%81%E6%9C%89%E4%BA%BA%E4%BB%A4%E7%89%8C connect-multiple-accounts-simultaneously=%E5%90%8C%E6%97%B6%E8%BF%9E%E6%8E%A5%E5%A4%9A%E4%B8%AA%E8%B4%A6%E6%88%B7%E6%8C%81%E6%9C%89%E4%BA%BA%E4%BB%A4%E7%89%8C using-appsflyer-mcp=%E4%BD%BF%E7%94%A8-appsflyer-mcp h_01JY3G1ZEC5Q30KP49RAA7EHRS=%E4%BD%BF%E7%94%A8-appsflyer-mcp use-cases-and-prompts=%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF%E4%B8%8E%E7%A4%BA%E4%BE%8B%E6%8F%90%E7%A4%BA h_01JY3WMZ41HHQ4G13DGV8DPJMW=%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF%E4%B8%8E%E7%A4%BA%E4%BE%8B%E6%8F%90%E7%A4%BA h_01JZHT6BA2NX8GXNV8675XNVWT=%E9%87%8D%E8%A6%81%E6%8F%90%E7%A4%BA h_01JY3WZE6G2WB6DCWV68G1T36D=analyze-performance h_01K7P0A6V86FZ3YQTQ4N5JZ4ZX=analyze-skan-performance h_01JY3VJEQMRDFAFTKZMPZ90RHP=onelink-management h_01JY3VJEQMXD32NSEE0E0FWG60=knowledge-base-and-developer-support h_01K01CE5NQ56HRT967F78ETKMS=apps-management h_01K01CE5NQBW6AADMHEPBQQN7S=audiences-management audiences-management::6584184=%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB%E7%AE%A1%E7%90%86 h_01KWBYTJ8GCJ884DN6XXPXZYMJ=%E5%8F%97%E4%BC%97%E5%85%B1%E4%BA%AB%E7%AE%A1%E7%90%86 h_01JY3VJEQNYKZ3Z724XM9JRWZF=feedback-tool h_01K9SHEQBWKK6AC0GD0YQVVJJ9=cost-configuration-integration h_01KGM1A7V6NB16A1Q07V5FQG2M=ad-revenue-integrations h_01K338G5KA09TESMNC6Z88RJCP=user-management-and-role-control other-information=%E5%85%B6%E4%BB%96%E4%BF%A1%E6%81%AF h_01JZHTJ1FQMXX9GSAN31E8HAYF=%E5%85%B6%E4%BB%96%E4%BF%A1%E6%81%AF privacy-and-security=h_privacy-and-security h_data-processing=%E6%95%B0%E6%8D%AE%E5%A4%84%E7%90%86 data-processing=%E6%95%B0%E6%8D%AE%E5%A4%84%E7%90%86 h_credentials=%E7%99%BB%E5%BD%95%E4%BF%A1%E6%81%AF credentials=%E7%99%BB%E5%BD%95%E4%BF%A1%E6%81%AF h_permissions=%E6%8E%88%E6%9D%83 permissions=%E6%8E%88%E6%9D%83 h_read-only-access=%E5%8F%AA%E8%AF%BB%E8%AE%BF%E9%97%AE read-only-access=%E5%8F%AA%E8%AF%BB%E8%AE%BF%E9%97%AE h_ai-provider-data-usage=%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD%E6%8F%90%E4%BE%9B%E5%95%86%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BD%BF%E7%94%A8 ai-provider-data-usage=%E4%BA%BA%E5%B7%A5%E6%99%BA%E8%83%BD%E6%8F%90%E4%BE%9B%E5%95%86%E6%95%B0%E6%8D%AE%E7%9A%84%E4%BD%BF%E7%94%A8 h_certifications=%E8%AE%A4%E8%AF%81 certifications=%E8%AE%A4%E8%AF%81 h_01K044H4H18ED75GYQWMPDRA4R=tool-mapping h_01K01DT8656BQM1GW0HDHXGCY2=traits-and-limitations h_troubleshoot-connection-issues=%E6%8E%92%E6%9F%A5%E8%BF%9E%E6%8E%A5%E9%97%AE%E9%A2%98 troubleshoot-connection-issues=%E6%8E%92%E6%9F%A5%E8%BF%9E%E6%8E%A5%E9%97%AE%E9%A2%98 troubleshoot-browser-based-oauth-login=h_troubleshoot-browser-based-oauth-login troubleshoot-bearer-token-authentication=h_troubleshoot-bearer-token-authentication access-and-permission-issues=h_access-and-permission-issues general-connection-checks=h_general-connection-checks" />
