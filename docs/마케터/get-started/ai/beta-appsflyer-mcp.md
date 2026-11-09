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
  edited_at: '2026-10-14T10:28:47Z'
  id: 36349070304785
  locale: ko
  section: AI
  section_id: 36348470056081
  url: https://support.appsflyer.com/hc/ko/articles/36349070304785
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **한눈에 보기:** AppsFlyer MCP는 AppsFlyer 데이터를 Claude, ChatGPT, Gemini CLI, Copilot CLI 및 VS Code와 같은 대형 언어 모델(LLM)에 연결합니다. AI 채팅이나 개발 환경에서 직접 질문하고 성능 통찰력을 얻으며 AppsFlyer 정보를 검색할 수 있습니다.

<Embed title="[Beta] AppsFlyer MCP" typeOfEmbed="youtube" url="https://www.youtube.com/embed/jAw7oocIx6o?si=-s107vTaTTwO076n" providerUrl="https://www.youtube.com" />

<div id="disclaimer" />

<Accordion title="주의 사항">

**AppsFlyer MCP 서버는 현재 AppsFlyer에서 평가 목적으로 제공하는 베타 단계의 서비스입니다.**

이를 사용하여 타사 AI 도구를 연결하면 AppsFlyer는 해당 도구, 그 출력물, 결과, 성능, 작동, 합법성 또는 신뢰성에 대한 책임이나 의무가 없음에 동의하게 됩니다. AppsFlyer는 이러한 도구나 그 결과를 통제, 보증 또는 검증하지 않으며, 관련된 모든 명시적 또는 묵시적 보증을 명시적으로 부인합니다. AppsFlyer는 이러한 도구의 데이터 저장, 보존, 처리 또는 사용에 대해 책임을 지지 않습니다. 관련 법률 및 자체 내부 정책을 준수하는 것은 전적으로 귀하의 책임입니다. 귀하는 이러한 도구를 MCP 서버에 연결하고 데이터에 대한 액세스를 제공하는 데 필요한 모든 권리와 동의를 가지고 있음을 나타냅니다. 이 서비스는 지원되는 사용 사례에 대해서만 "있는 그대로" 제공됩니다. 이 범위를 벗어난 사용은 전적으로 귀하의 책임입니다. 사용은 다음 약관의 적용을 받습니다: <Anchor target="_blank" href="https://www.appsflyer.com/legal/msa/">마스터 서비스 계약</Anchor> , 또는 최종 계약이 체결된 경우 해당 계약의 조건.

</Accordion>

<div id="what-is-appsflyer-mcp" />

## 앱스플라이어 MCP란 무엇인가요?

앱스플라이어 MCP를 사용하여 LLM을 앱스플라이어 플랫폼에 안전하게 연결하고, 간단한 대화를 통해 마케팅 데이터를 분석합니다. 앱스플라이어 MCP는 실시간 데이터를 기반으로 더 스마트하고 신속한 의사 결정을 내릴 수 있도록 합니다.

MCP는 다음의 기능을 수행합니다:

* 캠페인 성과, 트렌드, KPI 정보 바로 가져오기
* ROAS, 인스톨, LTV 등의 지표 비교
* 원링크 템플릿, 링크 및 오디언스 연결 검사 및 문제 해결
* 설정 가이드, 제품 문서 불러오기

<div id="set-up-appsflyer-mcp" />

## AppsFlyer MCP 설정

AppsFlyer MCP는 채팅 어시스턴트, CLI, IDE, 자동화 플랫폼 및 자체 호스팅 에이전트에 연결할 수 있습니다. 설정은 사용하는 클라이언트와 해당 클라이언트가 지원하는 인증 방법에 따라 다릅니다.

<div id="note" />

> 📘 **참고**
>
> 일부 플랫폼에서는 MCP 서버를 연결하기 위해 관리자 승인이 필요할 수 있습니다. 아래에 설명된 설정 옵션이 보이지 않으면 IT 또는 작업 공간 관리자에게 문의하십시오.

<div id="authentication-methods" />

## 인증 방법

AppsFlyer MCP는 두 가지 인증 방법을 지원합니다. AppsFlyer MCP에 연결할 계획에 맞는 방법을 사용하세요.

| 인증 방법 | 사용되는 대상 | 최적의 사용 사례 | 액세스 기간 |
| --- | --- | --- | --- |
| 브라우저 기반 OAuth 로그인 | Gemini CLI, Copilot CLI, ChatGPT, Claude.ai 및 Claude 데스크톱 | 임시 질문, 탐색적 분석 및 일회성 보고서 | 연결 후 7일 동안 유효합니다. 세션 종료 시 재인증이 필요합니다. |
| 보안 토큰 인증 | Claude 코드, 자동화 플랫폼, 자체 호스팅 에이전트 및 통합 | 자동화, 예약된 작업, 백그라운드 에이전트 및 비대화형 워크플로 | 수동으로 해지될 때까지 유효 |

<div id="browser-based-oauth-login" />

### 브라우저 기반 OAuth 로그인

브라우저 기반 OAuth 로그인을 사용하면 브라우저를 통해 대화형으로 연결할 수 있습니다. 연결하면 MCP 클라이언트가 브라우저 창을 열고 AppsFlyer에 로그인하라는 메시지를 표시합니다. 접근을 승인하면 클라이언트가 고객님의 AppsFlyer 계정에 연결됩니다.

대화형 세션, 탐색적 분석 및 일회성 보고서에 이 방법을 사용하십시오.

<div id="bearer-token-authentication" />

### 보안 토큰 인증

Bearer 토큰 인증을 사용하면 비대화형 도구가 AppsFlyer MCP 토큰을 사용하여 AppsFlyer MCP에 연결할 수 있습니다. 토큰은 요청 헤더에 전달됩니다:

```http
Authorization: Bearer <YOUR_MCP_TOKEN>
```

브라우저 로그인을 사용할 수 없는 자동화, 예약된 작업, 백그라운드 에이전트 및 통합에 이 방법을 사용하십시오.

토큰을 생성하려면 다음으로 이동하십시오. **계정 메뉴 > 보안 센터 > AppsFlyer 토큰** 그리고 MCP 토큰을 생성하십시오.

<div id="set-up-by-client" />

## 클라이언트에 의해 설정됨

<div id="h_claude-ai-and-claude-desktop" />

<Accordion title="Claude.ai 및 Claude Desktop">

브라우저 기반 OAuth 로그인을 사용하여 Claude.ai 및 Claude 데스크톱을 사용하십시오. 이 지침은 웹 및 데스크톱의 Claude에 적용됩니다.

<div id="note-1" />

> 📘 **참고**
>
> 팀 및 기업 플랜 사용자의 경우 소유자 또는 관리자만 조직 전체 통합을 추가할 수 있습니다.

<div id="set-up-claude-chat-and-cowork" />

#### Claude.ai 및 Claude 데스크톱 설정

1. 왼쪽 하단 모서리에 있는 이름을 클릭하고 선택하십시오. **설정 . 또는 새 채팅에서 을 클릭합니다.** 검색 및 도구 **>** 연결관리.
2. <Anchor target="_blank" href="https://claude.ai/settings/integrations">Connectors</Anchor> 탭을 엽니다.
3. **Organization connectors** 탭을 엽니다.
4. 커넥터 섹션에서 **커넥터 추가**를 클릭합니다.
5. 다음 연결관 세부 정보를 입력합니다.
   * 커넥터 이름: 앱스플라이어
   * **연결관 URL:** `https://mcp.appsflyer.com/auth/mcp`
6. **추가**를 클릭합니다.
7. **Your connectors** 탭을 엽니다.
8. 커넥터 섹션에서 AppsFlyer connection 옆에 있는 **연결**을 클릭합니다.
9. 로그인 창이 뜨면 앱스플라이어에 로그인합니다.

<div id="note-2" />

<div id="test-the-claude-connection" />

#### Claude 연결 테스트

1. 채팅 창에서 설정 버튼을 클릭합니다.   
   <Image align="center" alt="" src="https://files.readme.io/5f27783a0743f9005c5df4f580455777aa3ef612feb220d1058664ee63431cf3-46334217789073.png" width="25%" />
2. AppsFlyer MCP가 올바르게 설정되었다면 AppsFlyer 도구가 메뉴에 나타납니다.

</Accordion>

<div id="h_claude-code" />

<Accordion title="Claude Code">

Claude Code를 사용하여 자동화, 스케줄링 및 비대화형 워크플로우에 대한 액세스 토큰 인증을 사용합니다.

<div id="add-appsflyer-mcp-to-claude-code" />

#### Claude Code에 AppsFlyer MCP 추가

1. AppsFlyer에서 이동하십시오. **계정 메뉴 > 보안 센터 > AppsFlyer 토큰**.
2. MCP 토큰을 만듭니다.
3. 터미널에서 AppsFlyer MCP 서버를 추가합니다:

   ```bash
   claude mcp add-json appsflyer '{"type":"http","url":"https://mcp.appsflyer.com/auth/mcp","headers":{"Authorization":"Bearer YOUR_APPSFLYER_MCP_TOKEN"}}'
   ```
4. Start Claude Code:

   ```bash
   claude .
   ```
5. MCP 서버가 추가되었는지 확인하십시오.

   ```bash
   claude mcp list
   ```
6. 확인하십시오: `appsflyer` 구성된 MCP 서버 목록에 나타납니다.
7. AppsFlyer 질문을 하십시오. 예시:

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

로컬 개발 환경에서 AppsFlyer MCP를 연결하려면 Cursor IDE를 사용하십시오.

1. 범위에 따라 설정 파일을 생성하거나 엽니다.
   * **글로벌 구성:** `~/.cursor/mcp.json`
   * **프로젝트별 구성:** `.cursor/mcp.json`
2. JSON 파일 필드에 `mcpServers`다음 항목을 추가하십시오mcpServers.

   ```json
   {
     "mcpServers": {
       "appsflyer": {
         "url": "https://mcp.appsflyer.com/auth/mcp"
       }
     }
   }
   ```
3. 새 설정을 적용하려면 Cursor IDE를 재시작합니다.
4. AppsFlyer MCP 서비스에 액세스하라는 메시지가 표시되면 인증합니다.

</Accordion>

<div id="h_vs-code" />

<Accordion title="VS코드">

1. `Cmd+Shift+P` 또는 `Ctrl+Shift+P` 키를 눌러 커맨드 팔레트를 엽니다.
2. **MCP 서버 구성**을 선택합니다.
3. In `.vscode/mcp.json`, AppsFlyer MCP 서버 구성 추가:

   ```json
   {
     "servers": {
       "appsflyer": {
         "url": "https://mcp.appsflyer.com/auth/mcp"
       }
     }
   }
   ```
4. 파일을 저장하고 Copilot Chat을 다시 시작하십시오.

</Accordion>

<div id="h_chatgpt" />

<Accordion title="ChatGPT">

ChatGPT를 AppsFlyer MCP와 함께 사용하는 방법은 두 가지가 있습니다.

* [맞춤형 GPT](#appsflyer-맞춤형-gpt-추가): AppsFlyer 어시스턴트에 간단하게 액세스하는 데 가장 적합합니다.
* [ChatGPT의 MCP](#chatgpt에-appsflyer-mcp-추가): AppsFlyer 데이터를 ChatGPT 대화에 가져오려는 사용자에게 가장 적합합니다.

<div id="add-the-appsflyer-custom-gpt" />

#### AppsFlyer 맞춤형 GPT 추가

1. 클릭 <Anchor target="_blank" href="https://chatgpt.com/g/g-68b6a92eb8e0819194cbb81e1e635c0d-appsflyer">AppsFlyer 맞춤형 GPT</Anchor>.
2. 사이드바에 GPT를 저장하여 쉽게 액세스할 수 있습니다.
3. 맞춤형 GPT를 엽니다.
4. 다음과 같은 방법으로 예시:

   ```text
   Show me my Meta campaign performance from last week.
   ```

<div id="add-appsflyer-mcp-in-chatgpt" />

#### ChatGPT에 AppsFlyer MCP 추가

<div id="note-3" />

> 📘 **참고**
>
> 조직에 커넥터를 추가하고 게시하려면 관리자 설정이 필요할 수 있습니다.

1. 커넥터를 추가하고 조직에 게시합니다.
2. 다음 연결관 세부 정보를 입력합니다.
   * **이름:** AppsFlyer MCP
   * **URL:** `https://mcp.appsflyer.com/auth/mcp`
   * 인증 OAuth
3. 처음으로 연결하려면 다음으로 이동하십시오. **설정 > 앱 및 소스 > AppsFlyer MCP**.
4. AppsFlyer MCP에 연결합니다.
5. AppsFlyer 자격 증명을 사용하여 연결하고 로그인하는 단계를 따르십시오.

설정 후 채팅을 열고 선택하십시오. **출처** 또는 **연결기**, 그리고 AppsFlyer 연결을 켭니다.

보안을 위해 AppsFlyer MCP는 약 10시간마다 연결을 끊습니다. 연결을 다시 설정하려면 연결 흐름을 반복하십시오.

</Accordion>

<div id="h_gemini-cli" />

<Accordion title="Gemini CLI">

브라우저 기반 OAuth 로그인으로 Gemini CLI 사용.

<div id="add-appsflyer-mcp-to-gemini-cli" />

#### Gemini CLI에 AppsFlyer MCP 추가

1. 터미널에서 AppsFlyer MCP 서버를 추가합니다:

   ```bash
   gemini mcp add appsflyer https://mcp.appsflyer.com/auth/mcp -t http
   ```
2. Gemini CLI 시작:

   ```bash
   gemini
   ```
3. Gemini CLI 프롬프트에 다음을 입력하십시오.

   ```text
   auth
   ```
4. 브라우저에서 인증 흐름을 완료한 다음 터미널로 돌아갑니다.
5. AppsFlyer 질문을 하십시오. 예시:

   ```text
   What apps are in my AppsFlyer account?
   ```

<div id="troubleshoot-gemini-cli-authentication" />

#### Gemini CLI 인증 문제 해결

인증에 실패하면 디버그 모드에서 Gemini CLI를 시작합니다.

```bash
GEMINI_LOG_LEVEL=debug gemini
```

그런 다음 입력하십시오. `auth` 다시 Gemini CLI 프롬프트에서.

</Accordion>

<div id="h_copilot-cli" />

<Accordion title="Copilot CLI">

브라우저 기반 OAuth 로그인을 사용하여 Copilot CLI를 사용합니다.

<div id="add-appsflyer-mcp-to-copilot-cli" />

#### AppsFlyer MCP를 Copilot CLI에 추가합니다.

1. 터미널을 엽니다.
2. Copilot CLI를 시작합니다.

   ```bash
   copilot
   ```
3. 로그인하지 않은 경우 Copilot CLI 프롬프트에 다음 명령을 입력합니다.

   ```text
   /login
   ```
4. 브라우저 로그인을 완료합니다.
5. Copilot CLI 프롬프트에 다음을 입력하십시오.

   ```text
   /mcp add
   ```
6. 다음 MCP 서버 세부 정보를 입력하십시오.

| 필드 | 창출 가치 |
| --- | --- |
| 서버 이름 | `appsflyer` |
| 서버 유형 | `HTTP` |
| URL | `https://mcp.appsflyer.com/auth/mcp` |
| 도구 | `*` |

7. 보도 자료 **Ctrl+S** 구성을 저장하려면.
8. 메시지가 표시되면 브라우저에서 AppsFlyer 인증 흐름을 완료하십시오.
9. 터미널로 돌아갑니다.
10. AppsFlyer 질문을 하십시오. 예시:

    ```text
    What apps are in my AppsFlyer account?
    ```

</Accordion>

<div id="h_third-party-and-self-hosted-platforms" />

<Accordion title="타사 및 자체 호스팅 플랫폼">

MCP 토큰을 사용하여 타사 또는 자체 호스팅 시스템을 AppsFlyer MCP와 인증합니다. 이는 n8n, Make 또는 자체 LLM 기반 에이전트와 같은 플랫폼과의 자동화 및 AI 통합을 지원합니다.

MCP 토큰은 해당 토큰을 만든 관리자의 권한을 상속받는 계정 수준의 보유자 토큰입니다. <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">에서 액세스하고 관리할 수 있습니다.</Anchor> <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">보안 센터 > AppsFlyer 토큰</Anchor>.

<div id="mcp-connection-details" />

#### MCP 연결 세부 정보

자동화 또는 에이전트 플랫폼을 AppsFlyer MCP에 연결하려면 다음 구성을 사용하십시오.

* **인증 유형:** Bearer Token
* **기본 URL/엔드포인트:** `https://mcp.appsflyer.com/auth/mcp`
* **보유자 토큰:** MCP 토큰

<div id="note-4" />

> 📘 **참고**
>
> 토큰을 공개적으로 공유하거나 게시하지 마십시오. 개인 자격 증명으로 취급하십시오. MCP 토큰은 MCP 환경에 대한 직접 액세스 권한을 부여합니다.

<div id="example-use-cases" />

#### 사용 사례 예시

| 카테고리 | 예시 |
| --- | --- |
| 맞춤형 에이전트 | MCP를 사용하여 데이터를 가져오고, 분석하고, 권장 사항을 보내는 AI 에이전트를 구축합니다. |
| LLM 통합 | 자체 호스팅 LLM이 MCP을 통해 캠페인 성과 지표를 쿼리하도록 허용합니다. |

</Accordion>

<div id="h_other-platforms" />

<Accordion title="기타 플랫폼">

기본적으로 위에 나열된 플랫폼만 활성화되어 있습니다. 다른 플랫폼을 연결하려면 CSM에 문의하거나 이메일을 보내십시오. [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<div id="h_use-multiple-accounts-or-agencies" />

<Accordion title="여러 계정 또는 에이전시 사용">

AppsFlyer MCP는 한 번에 하나의 AppsFlyer 계정에 연결됩니다.

<div id="switch-between-accounts-browser-based-oauth" />

#### 계정 전환(브라우저 기반 OAuth)

동일한 이메일로 여러 AppsFlyer 계정을 관리하는 경우 MCP가 연결되는 계정을 전환할 수 있습니다.

1. AppsFlyer에서 연결할 기본 계정으로 설정하려는 계정을 설정합니다.
2. MCP 클라이언트에서 다시 로그인합니다.

단일 연결에서 여러 계정을 나란히 보거나 쿼리할 수 없습니다.

<div id="connect-multiple-accounts-simultaneously-bearer-token" />

#### 여러 계정을 동시에 연결(담당자 토큰)

예를 들어 에이전시 사용을 위해 동시에 여러 계정에 연결하려면 브라우저 기반 OAuth 대신 다중 에이전트 흐름을 사용하십시오.

1. 각 계정에 대해 MCP 토큰을 생성합니다. **계정 메뉴 > 보안 센터 > AppsFlyer 토큰**.
2. 에이전트 플랫폼에서 각 계정을 개별적으로 연결하려면 해당 계정의 고유한 액세스 토큰을 사용하십시오.

이러한 흐름의 예는 다음과 같습니다. <Anchor target="_blank" href="https://www.youtube.com/watch?v=o5oK-yWuE5E">이 비디오</Anchor>.

</Accordion>

<div id="use-appsflyer-mcp" />

## AppsFlyer MCP 사용

<div id="use-cases-and-prompts" />

### 사용 사례 및 프롬프트

앱스플라이어 MCP는 마케팅 분석 정보 및 성과 인사이트를 불러오고 설정 작업을 수행할 수 있도록 툴과 리소스를 제공합니다.

<div id="h_01M6DQ8W2JQ9ECH5VEZPRT7221" />

<div id="h_analyze-incrementality-experiments" />

<div id="h_analyze-creative-performance" />

<div id="note-6" />

<div id="note-5" />

<div id="important" />

> 🚧 **중요!**
>
> 앱스플라이어 MCP를 통해 생성된 답변은 아래 제시된 사용 사례 범위 내에서만 신뢰할 수 있습니다. 사용 사례 범위 밖의 답변은 검증되지 않았으며 부정확하거나 왜곡된 정보를 포함할 수 있습니다. 앱스플라이어 MCP 연동 범위 밖에서 생성된 AI 답변의 정밀도나 정확성을 보장하지 않습니다.

사용 사례와 프롬프트는 아래와 같습니다:

<div id="analyze-performance" />

<Accordion title="성과 분석">

집약적 마케팅 성과 데이터를 실시간으로 검색합니다. 성과가 높은 캠페인과 낮은 캠페인을 비교하고, 트렌드를 파악하며, 의사 결정에 도움이 되는 인사이트를 얻을 수 있습니다.

**프롬프트:** "지난주 미국에서 Mypets.android.com에 가장 많은 트래픽을 가져온 매체 소스는 무엇인가요?"

**예상 AI 답변:** 설치, 수익 및 ROAS를 포함한 가장 성과가 좋은 미디어 소스를 분석해 알려줍니다.

**프롬프트:** "총 설치 건수가 최소 5,000회 이상인 캠페인 중 ROAS가 가장 높은 것은 무엇입니까?”

**예상 AI 답변:** 기준에 부합하는 캠페인을 찾아 순위를 매겨 인사이트를 제공합니다.

**프롬프트:** "중국에서 몇 건의 Mypets.android.com 앱 인스톨이 발생했나요?”

**예상 AI 답변:** 해당 날짜와 앱에 대해 중국에서 발생한 인스톨 건수를 불러옵니다.

**프롬프트:** "캠페인별로 세분화된 지난 하루 동안의 Mypets.android.com 성과 요약을 작성하십시오."

**예상 AI 답변:** 해당 앱에 대한 캠페인별 성과 리포트를 제공합니다.

**프롬프트:** "지난 주 D1 보유율과 그 전 주를 미디어 소스별로 그룹화하여 비교하십시오."

**예상 AI 답변:** AI는 미디어 소스별로 그룹화된 D1 유지율을 주 단위로 비교합니다.

</Accordion>

<div id="analyze-skan-performance" />

<Accordion title="SKAN 성과 분석">

Apple의 SKAdNetwork 프레임워크를 사용하여 iOS 캠페인 성과에 대한 통찰력을 얻습니다. 성과가 가장 우수한 캠페인을 식별하고 의사 결정을 지원하기 위해 KPI 추세를 분석합니다.

**프롬프트:** "지난 달 네트워크별 ROI는 얼마였나요?"

**예상 AI 답변:** AI는 선택한 기간 동안의 ROI 결과를 검색하고 상위 네트워크를 강조 표시합니다.

**프롬프트:** "CPI가 가장 낮은 캠페인은 무엇인가요?"

**예상 AI 답변:** AI는 CPI가 가장 낮은 캠페인을 식별하고 상위 성과자를 순위에 따라 표시합니다.

**프롬프트:** "지난 달 af\_subscribed 이벤트의 주간 전환율은 얼마였나요?"

**예상 AI 답변:** AI는 이벤트에 대한 전환율을 주 단위로 분류하고 전반적인 추세를 나타냅니다.

**프롬프트:** "null 비율이 가장 높은 네트워크는 무엇이며, 그 아래의 어떤 캠페인이 가장 높은 null 비율을 보여주나요?"

**예상 AI 답변:** AI는 가장 높은 누적 비율을 가진 네트워크를 식별하고 해당 비율에 가장 기여하는 캠페인을 개요합니다.

</Accordion>

<div id="onelink-management" />

<Accordion title="원링크 관리">

OneLink 템플릿과 링크를 조회하고 점검하여 라우팅을 일관되게 유지하고 명확한 사용자 여정을 보장합니다. MCP는 문제를 해결하고 대규모로 링크 설정을 검증하는 데 도움을 줄 수 있습니다.

**프롬프트:** "'HolidayPush2025' 템플릿을 검토하고, 파라미터를 포함한 모든 링크를 표시하십시오."

**예상 AI 답변:** AI는 짧은 링크와 관련 매개 변수 값이 포함된 CSV 테이블을 반환합니다.

**프롬프트:** “원링크가 기존 유저를 앱 스토어로 리디렉션하는 이유는 무엇입니까?"

**예상 AI 답변:** AI는 링크 매개 변수 및 폴백 로직을 기반으로 문제 해결 통찰력을 반환합니다.

**프롬프트:** "TravelBuddy 앱의 QR 활성화된 OneLink를 모두 나열하시오"

**예상 AI 답변:** QR 링크와 관련 메타데이터가 포함된 원링크 목록

</Accordion>

<div id="knowledge-base-and-developer-support" />

<Accordion title="지식 베이스 및 개발자 지원">

앱스플라이어 문서와 DevHub 리소스에 빠르게 액세스할 수 있습니다. AI 채팅에서 직접 SDK 설정, 제품 동작 및 측정 로직에 대한 정확한 답변을 받으세요.

**프롬프트:** "안드로이드에서 인앱 이벤트 중복 제거를 어떻게 설정합니까?"

**예상 AI 답변:** AI는 설정 단계, 코드 스니펫 및 모범 사례를 제공합니다.

**프롬프트:** "TikTok 설치에 대한 어트리뷰션 룩백 윈도우는 어떻게 됩니까?"

**예상 AI 답변:** AI는 최신 플랫폼별 기여 규칙을 설명합니다.

**프롬프트:** "앱스플라이어를 사용하여 앱의 ROAS를 최적화하는 가장 좋은 방법은 무엇입니까?"

**예상 AI 답변:** 세분화, 파트너 최적화, LTV 측정 모범 사례 등의 전략적 레버를 간략히 소개합니다.

</Accordion>

<div id="apps-management" />

<Accordion title="앱 관리">

기여 창, 세션 시간 초과, 재참여 설정 등 주요 앱 구성 세부 정보를 검색합니다. 이 정보를 사용하여 포트폴리오 전체에서 앱 설정을 감사하고 비교합니다.

**프롬프트:** "게임 앱에 대해 설정된 어트리뷰션 윈도우는 어떻게 됩니까?"

**예상 AI 답변:** 각 앱의 어트리뷰션 윈도우를 나열한 뒤, 표준값과의 편차를 표시합니다.

**프롬프트:** "어떤 앱의 룩백 윈도우가 다른가요?"

**예상 AI 답변:** 비표준 룩백 윈도우가 있는 앱을 표면화하고 설정된 값을 표시합니다.

**프롬프트:** “고정된 iOS 앱 중 활성화된 앱을 모두 나열하십시오."

**예상 AI 답변:** 고정된 iOS 앱 중 활성화된 앱 목록(앱 ID, 이름 포함)을 제공합니다.

**프롬프트:** "앱스플라이어 게임 앱의 현재 세션 타임아웃 설정은 어떻게 되어있으며, 리인게이지먼트가 어트리뷰션 되는 데에 지장이 있을 수 있습니까?”

**예상 AI 답변:** 세션 타임아웃 설정과 이것이 리인게이지먼트에 미치는 영향에 대해 설명합니다.

</Accordion>

<div id="audiences-management" />

<Accordion title="오디언스 관리">

### 오디언스 관리

오디언스 구조, 소유권, 파트너 연결 및 진행 중인 테스트 관련 정보를 즉시 파악하세요. 업로드 상태를 모니터링하고, 연결 실패를 감지하며, 사용되지 않는 오디언스를 식별하고 각 오디언스가 어떻게 구성되어 있는지 이해합니다. 이 정보를 사용하여 팀 간 캠페인 관리를 간소화합니다.

**프롬프트:** "FinancePro 앱의 활성 오디언스를 전부 알려주십시오."

**예상 AI 답변:** AI는 생성 날짜, 소유자 및 파트너와 같은 메타데이터가 포함된 오디언스 목록을 반환합니다.

**프롬프트:** "가장 최근 'Churned Users - Tier A' 오디언스를 누가 업데이트했나요?”

**예상 AI 답변:** AI는 마지막 수정 시간이 포함된 사용자 ID 또는 이메일을 반환합니다.

**프롬프트:** "메타 ,틱톡과 스플릿 테스트 중인 모든 오디언스를 나열해 주세요."

**예상 AI 답변:** 테스트 설정과 스플릿 비율을 포함한 활성 오디언스 목록을 제공합니다.

**프롬프트:** "Moloco와 테스트하고 싶습니다. 구글, 구글과 연결된 모든 청중을 보여줘."

**예상 AI 답변:** AI는 현재 상태와 구성을 가진 구글과 연결된 청중 목록을 반환합니다.

**프롬프트:** "(네트워크)를 닫을 예정이니 실행 중인 활성 청중 목록을 보여줘."

**예상 AI 답변:** AI는 연결된 파트너와 현재 상태를 가진 모든 활성 청중을 반환합니다.

**프롬프트:** "모든 활성 청중, 연결된 파트너 및 현재 분할 목록을 보여줘."

**예상 AI 답변:** AI는 각 파트너 연결 및 분할 비율과 함께 전체 오디언스 목록을 반환합니다.

**프롬프트:** "현재 내 Meta 오디언스 중 업로드에 실패한 것이 있나요?"

**예상 AI 답변:** AI는 업로드 상태가 실패한 Meta 연결 오디언스 목록을 각각의 오류 메시지와 함께 반환합니다.

**프롬프트:** "TikTok 캠페인을 확인하고 싶습니다. TikTok에 연결된 어떤 오디언스가 언제부터 실패하고 있나요?"

**예상 AI 답변:** AI는 상태가 실패한 모든 TikTok 연결 오디언스와 마지막 성공적인 업로드 시간을 반환합니다.

**프롬프트:** "지난 7일 동안 성공적인 업로드가 없었던 모든 오디언스를 보여주세요."

**예상 AI 답변:** AI는 지난 7일 동안 성공적인 업로드가 없었던 오디언스 목록과 현재 연결 상태를 반환합니다.

</Accordion>

<div id="feedback-tool" />

<Accordion title="피드백 툴">

어시스트 인터페이스를 통해 앱스플라이어 MCP 사용 경험에 대한 피드백을 제출해 주세요. 고객님의 의견은 저희가 제품을 개선하고 미래를 형성하는 데 도움이 됩니다.

**프롬프트:** “분석 툴이 제공하는 분석 데이터는 매우 유용하며 의사 결정에 큰 도움이 됩니다. "분석에 앱 내 이벤트 측정을 옵션으로 추가해 주시면 좋겠습니다."

**예상 AI 답변:** AI는 이 의견을 AppsFlyer MCP 제품 팀에 제출합니다.

</Accordion>

<div id="cost-configuration-integration" />

<Accordion title="비용 구성 통합">

비용 구성 MCP를 통해 비용 데이터에 대한 가시성과 제어권을 확보하세요. 이 통합을 통해 비용 적용 범위를 극대화하고, 통합 격차를 조기에 감지하며, 광고 네트워크 전반에 걸쳐 비용 데이터를 완전하고 정확하게 유지할 수 있습니다.

**프롬프트:** "내 AppsFlyer 계정에 어떤 활성 비용 통합이 있나요?"

**예상 AI 답변:** AI는 활성화된 모든 비용 통합과 연결된 앱 ID 및 현재 상태를 AppsFlyer 계정에 나열합니다.

**프롬프트:** "활성 비용 통합에서 발생한 문제를 보여주세요."

**예상 AI 답변:** AI는 지난 7일 동안 문제가 있었던 활성 비용 통합을 광고 네트워크 및 연결된 앱별로 정렬하여 표시합니다.

**프롬프트:** "최근 어트리뷰션 데이터를 기반으로 어떤 비용 통합을 연결해야 할까요?"

**예상 AI 답변:** AI는 비용 통합을 지원하지만 아직 연결되지 않은 광고 네트워크를 앱별 최근 트래픽 볼륨 순으로 표시합니다.

</Accordion>

<div id="ad-revenue-integrations" />

<Accordion title="광고 수익 연동">

AppsFlyer MCP를 사용하여 광고 수익 통합에 대한 가시성과 제어권을 확보하세요. MCP를 사용하여 어떤 광고 수익 통합이 활성화되어 있는지 확인하고, 그 상태를 모니터링하며, 문제를 조기에 감지하고, 앱 및 수익화 파트너 전반에 걸쳐 광고 수익 데이터가 일관되게 전달되도록 할 수 있습니다.

**프롬프트:** "내 AppsFlyer 계정에 어떤 활성 광고 수익 통합이 있나요?"

**예상 AI 답변:** AI는 연결된 앱 및 현재 통합 상태를 포함하여 AppsFlyer 계정에서 활성화된 모든 광고 수익 통합을 나열합니다.

**프롬프트:** "활성 광고 수익 통합에 있는 문제를 보여주세요."

**예상 AI 답변:** AI는 지난 7일 동안 문제가 있었던 활성화된 광고 수익 통합을 중재 파트너, 통합 유형 및 앱별로 그룹화하여 표시합니다.

</Accordion>

<div id="user-management-and-role-control" />

<Accordion title="사용자 및 역할 관리">

AppsFlyer 계정에서 사용자 및 역할 정보를 검색합니다. 이는 관리자가 명확한 사용자 데이터베이스를 유지하고 접근 제어를 효율적으로 관리하는 데 도움이 됩니다.

**프롬프트:** "지난 6개월 동안 앱스플라이어에 로그인하지 않은 비활성 사용자를 나열합니다."

**예상 AI 답변:** AI는 이메일 주소, 역할 및 마지막 로그인 타임스탬프를 포함하여 마지막 로그인 날짜가 6개월 이상이거나 전혀 로그인하지 않은 사용자를 반환합니다.

**프롬프트:** "권한 수준으로 그룹화된 모든 사용자를 표시하고 관리자 역할의 사용자를 강조 표시합니다."

**예상 AI 답변:** AI는 역할 유형별로 사용자를 정리하고 관련 앱 및 지리적 액세스 권한을 포함하여 관리자 사용자를 강조 표시합니다.

**프롬프트:** "어느 팀 멤버가 앱스플라이어에 로그인할 수 없다고 불평했습니다. 사용자가 존재하는지, 현재 상태가 무엇인지 확인할 수 있습니까?"

**예상 AI 답변:** AI는 사용자가 존재하는지 확인하고 사용자의 현재 역할, 관련 앱, 마지막 로그인 날짜 및 잠재적 액세스 제한을 반환합니다.

**프롬프트:** "5개 이상의 앱에 액세스할 수 있는 사용자는 누구이고, 역할은 무엇입니까?"

**예상 AI 답변:** AI는 광범위한 앱 액세스 권한을 가진 사용자, 해당 역할 및 액세스할 수 있는 전체 앱 목록을 반환합니다.

</Accordion>

<div id="other-information" />

## 기타 정보

<div id="h_privacy-and-security" />

<Accordion title="개인정보 보호 및 보안">

AppsFlyer MCP는 선택한 AI 도구가 기존 권한을 기반으로 AppsFlyer 데이터를 쿼리할 수 있도록 합니다.

<div id="data-processing" />

#### 데이터 처리:

아닙니다. 앱스플라이어 MCP는 보안 프록시 역할을 합니다. 실시간으로 AppsFlyer 데이터를 가져와 쿼리에 대한 답변에 필요한 데이터를 반환합니다. AppsFlyer MCP는 쿼리 결과를 장기간 보관하거나 저장하지 않습니다.

<div id="credentials" />

#### 자격 증명

AppsFlyer 로그인을 통해 AppsFlyer MCP가 대신 API 호출을 할 수 있습니다. AppsFlyer 자격 증명은 AI 도구와 공유되지 않습니다.

<div id="permissions" />

#### 권한

AppsFlyer MCP는 기존 AppsFlyer 권한을 사용합니다. 사용자는 AppsFlyer에서 이미 열람 권한이 있는 앱과 데이터에만 액세스할 수 있습니다.

MCP 액세스를 구성하기 위한 별도의 권한 계층은 없습니다.

<div id="read-and-write-access" />

#### 읽기 전용 액세스

AppsFlyer MCP는 현재 읽기 및 쿼리 전용입니다. 사용자 없이는 AppsFlyer에서 아무런 조치를 취하지 않습니다.

<div id="ai-provider-data-usage" />

#### AI 제공업체 데이터 사용

AppsFlyer MCP에서 검색한 데이터는 사용자의 쿼리에 응답하기 위해 선택한 AI 도구와 공유될 수 있습니다. 응답을 생성하는 데 필요한 데이터만 공유됩니다.

AppsFlyer는 선택한 AI 도구가 데이터를 저장, 처리 또는 학습하는지 여부를 제어하지 않습니다. AppsFlyer MCP를 연결하기 전에 AI 제공업체의 약관 및 데이터 사용 정책을 검토하십시오.

<div id="certifications" />

#### 인증

AppsFlyer는 ISO 27001 및 SOC 2 인증을 받았습니다. ISO 42001 인증 진행 중입니다.

</Accordion>

<div id="tool-mapping" />

<Accordion title="툴 매핑">

모든 툴은 디폴트로 활성화되어있습니다. 기능을 제한 없이, 문제없이 사용하려면 전체 툴 활성화를 유지할 것을 권장합니다.

각 도구는 성과 분석, 앱 관리 또는 원링크 관리 등을 포함하는 기능 카테고리에 매핑됩니다. 일부 범주에는 여러 도구가 포함될 수 있습니다.

툴과 카테고리 매핑의 전체 목록은 아래 표를 참고하십시오.

<table><thead><tr><th>카테고리</th><th>도구</th><th>설명</th></tr></thead><tbody><tr><td><a href="#analyze-performance">성과 분석</a></td><td>fetch_aggregated_data</td><td>사용자 정의 날짜 범위, 그룹, 지표 및 필터를 사용하여 집계된 대시보드 데이터를 가져옵니다.</td></tr><tr><td rowspan="2"><a href="#apps-management">앱 관리</a></td><td>get_apps</td><td>모든 허용된 앱을 고정, 비고정 상태별로 구분하여 표시하고, 전송 요청 정보 또한 표시합니다.</td></tr><tr><td>get_app_settings</td><td>어트리뷰션 윈도우, 프라이버시 컨트롤, 세션 관리 및 플랫폼별 설정을 포함한 앱 구성 설정을 가져옵니다.</td></tr><tr><td><a href="#cost-configuration-integration">비용 구성 통합</a></td><td><p>get_active_cost_integrations</p><p>list_cost_supported_media_source</p></td><td>계정의 활성 비용 통합 상태 및 누락된 비용 통합에 대한 개요를 확인합니다.</td></tr><tr><td><a href="#ad-revenue-integrations">광고 수익 연동</a></td><td><p>list_adrevenue_supported_media_sources</p><p>get_active_adrevenue_integrations</p></td><td>어떤 통합이 활성화되어 있는지 확인하고, 상태를 모니터링하며, 구성 격차를 감지하고 광고 수익 데이터를 일관되게 유지하는 데 도움을 줍니다.</td></tr><tr><td><a href="#analyze-skan-performance">SKAN 성능</a></td><td>skan_get_app_data</td><td>사용자 지정 날짜 범위에 걸쳐 네트워크, 캠페인 또는 이벤트별로 그룹화된 집계된 SKAN 성능 데이터를 검색합니다.</td></tr><tr><td rowspan="3"><a href="#onelink-management">원링크 관리</a></td><td>get_onelink_templates</td><td>모든 OneLink 템플릿을 나열합니다.</td></tr><tr><td>get_onelink_template_links</td><td>특정 템플릿에서 생성된 모든 원링크 링크를 가져옵니다.</td></tr><tr><td>get_onelink_details</td><td>특정 OneLink의 구성 세부 정보를 가져옵니다.</td></tr><tr><td rowspan="3"><a href="#audiences-management">오디언스 관리</a></td><td>list_active_audiences</td><td>매일 계산되는 활성 오디언스를 모두 나열합니다.</td></tr><tr><td>list_audiences_connections</td><td>오디언스 데이터에 대한 광고 파트너 연동을 모두 나열합니다.</td></tr><tr><td>get_audience_connections</td><td>특정 오디언스에 대한 파트너 연결을 구축합니다.</td></tr><tr><td><a href="#knowledge-base-and-developer-support">지식 베이스 및 개발자 지원</a></td><td>get_public_knowledge</td><td>AppsFlyer 기술 자료 및 DevHub 문서를 검색합니다.</td></tr><tr><td><a href="#feedback-tool">피드백 툴</a></td><td>send_feedback</td><td>툴 또는 시스템에 대한 피드백을 제출합니다.</td></tr><tr><td><a href="#user-management-and-role-control">사용자 및 역할 관리</a></td><td>get_users</td><td>AppsFlyer에서 사용자 및 역할을 나열합니다.</td></tr></tbody></table>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제한 사항">

| 특징 | 설명 |
| --- | --- |
| 멀티 계정 사용 | 앱스플라이어 MCP는 디폴트 계정의 데이터만 사용합니다. 계정을 전환하거나 여러 계정을 한 번에 연결하려면 다음을 참조하십시오. [여러 계정 또는 에이전시 사용](#h_use-multiple-accounts-or-agencies). |
| 원링크 링크 | <ul><li>API, SDK 또는 대량 생성된 링크가 아닌 OneLink 관리 페이지에서 생성된 링크만 포함됩니다.</li><li>단일 플랫폼 링크(레거시 링크라고도 함)는 반환하지 않습니다.</li></ul> |
| 요청 제한 | <ul><li>분석: 분당 350건의 요청</li><li>복사합니다. 분당 350건의 요청</li><li>SKAN 쿼리당 최대 10,000개 행</li></ul> |
| 날짜 범위 | <ul><li>분석: 3년</li><li>SKAN 요청당 최대 90일</li></ul> |
| 그룹 | <ul><li>분석: 요청 당 4개의 조회 기준</li><li>SKAN 사용 가능한 경우 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#metrics">SKAN 대시보드</Anchor></li></ul> |
| 앱 제한 | <ul><li>분석: 요청 당 10개 앱</li><li>SKAN 요청당 1개의 앱, iOS 전용</li></ul> |
| 지원되는 디멘션 | 분석은 내 대시보드에서 사용 가능한 모든 차원을 지원합니다. |
| 집약형 데이터 | 집계 데이터가 지원됩니다. 여기에는 주간 및 월간 세분성 수준과 사용자 지정 메트릭이 포함됩니다. |
| 최신성 | SKAN 데이터는 UTC 기준으로 최대 3일 지연되어 제공됩니다. |
| 통화 및 시간대 | SKAN 데이터는 기본적으로 USD로 제공됩니다. 대체 통화는 다음을 사용하여 지원됩니다: `revenue_alt = true`. 데이터는 UTC로 보고됩니다. |
| MCP 비활성화 | <ul><li>MCP는 기본적으로 활성화되어 있으며 관리자가 비활성화할 수 있습니다. **계정 및 프로필 > AI 기능**.</li><li>MCP가 비활성화되면 사용자는 외부 AI 도구의 MCP를 통해 AppsFlyer 데이터에 액세스할 수 없습니다.</li><li>기존 연결은 현재 세션이 만료될 때까지 계속될 수 있습니다.</li><li>MCP를 비활성화해도 AppsFlyer의 일반 API 연결이나 기타 AI 기능에는 영향을 주지 않습니다.</li><li>MCP 토큰을 사용 중인 경우 먼저 다음에서 삭제하십시오. **보안 센터 > AppsFlyer 토큰**.</li></ul> |

</Accordion>

<div id="troubleshoot-connection-issues" />

## 연결 문제 해결 방법Troubleshoot connection issues

AppsFlyer MCP 연결이 작동하지 않으면 인증 방법에 대한 단계를 따르십시오.

<div id="h_troubleshoot-browser-based-oauth-login" />

<Accordion title="브라우저 기반 OAuth 로그인">

Gemini CLI, Copilot CLI, ChatGPT, Claude.ai 및 Claude Desktop과 같이 브라우저 로그인을 통해 연결되는 클라이언트에게는 이 섹션을 사용하십시오.

1. **세션을 다시 인증하십시오.** OAuth 세션은 약 7일마다 만료됩니다. 연결 흐름을 다시 실행하고 브라우저 로그인을 다시 완료하십시오.
2. **인증 흐름을 완료합니다.** 브라우저 로그인이 성공적으로 완료되었는지 확인합니다. 메시지가 표시되면 클릭하십시오. **허용** 또는 **승인**, 그런 다음 MCP 클라이언트로 돌아갑니다.
3. **세션을 다시 시작합니다.** CLI, 채팅 또는 애플리케이션 세션을 다시 시작합니다. 그런 다음 MCP 서버에 다시 연결합니다.
4. **MCP 서버 구성을 확인합니다.** 다음 값을 확인합니다.

| 필드 | 창출 가치 |
| --- | --- |
| 서버 유형 | `HTTP` |
| URL | `https://mcp.appsflyer.com/auth/mcp` |

5. **사용자 권한을 확인합니다.** AppsFlyer 사용자가 관련 앱 및 요청된 데이터에 액세스할 수 있는지 확인합니다.

</Accordion>

<div id="h_troubleshoot-bearer-token-authentication" />

<Accordion title="보안 토큰 인증">

이 섹션에서는 Claude Code, n8n, Make, 자체 호스팅 에이전트 및 기타 자동화 도구를 사용합니다.

1. **토큰이 해지되었는지 확인합니다.** 토큰은 수동으로 해지할 수 있습니다. 이전에 생성된 토큰 **2026년 3월 10일, 19:00 UTC** 더 이상 작동하지 않을 수 있습니다.
2. **새 MCP 토큰을 만듭니다.** 액세스 복원 방법:
   1. 앱스플라이어에 로그인합니다.
   2. 가기: **계정 메뉴 > 보안 센터 > 토큰 관리**.
   3. 취소된 토큰을 찾습니다.
   4. 취소된 토큰을 삭제합니다.
   5. 새 MCP 토큰을 만듭니다.
   6. 새 토큰으로 MCP 클라이언트 또는 자동화를 업데이트합니다.
3. **인증 헤더를 확인합니다.** 헤더가 다음 정확한 형식을 사용하는지 확인합니다.

   ```http
   Authorization: Bearer <YOUR_MCP_TOKEN>
   ```
4. **MCP 서버 구성을 확인합니다.** 다음 값을 확인합니다.

| 필드 | 창출 가치 |
| --- | --- |
| URL | `https://mcp.appsflyer.com/auth/mcp` |
| Transport | `HTTP` |
| 머리말 | `Authorization: Bearer` |

5. **서버가 등록되어 있는지 확인합니다.** Claude Code의 경우 다음을 실행합니다.

   ```bash
   claude mcp list
   ```
6. **필요한 경우 MCP 서버를 다시 추가합니다.**

   ```bash
   claude mcp remove appsflyer
   claude mcp add-json appsflyer '{"type":"http","url":"https://mcp.appsflyer.com/auth/mcp","headers":{"Authorization":"Bearer YOUR_APPSFLYER_MCP_TOKEN"}}'
   ```
7. **토큰 권한 확인.** MCP 토큰은 해당 토큰을 만든 관리자의 권한을 상속합니다. 토큰이 관련 앱 및 요청된 데이터에 액세스할 수 있는지 확인합니다.

</Accordion>

<div id="h_access-and-permission-issues" />

<Accordion title="액세스 및 권한 문제">

인증이 성공했지만 액세스가 여전히 실패하는 경우:

* MCP 액세스는 AppsFlyer 관리자에 의해 제한될 수 있습니다.
* 계정 및 프로필 설정에 액세스할 수 없는 경우 MCP 액세스가 차단되었을 수 있습니다.
* 액세스를 활성화하려면 AppsFlyer 관리자에게 문의하십시오.
* 사용자 또는 토큰이 관련 앱 및 요청된 데이터에 액세스할 수 있는지 확인하십시오.

</Accordion>

<div id="h_general-connection-checks" />

<Accordion title="일반 확인">

문제가 지속되면:

* 클라이언트가 MCP를 지원하는지 확인하십시오.
* 네트워크 또는 방화벽 제한이 MCP 엔드포인트를 차단하는지 확인하십시오.
* MCP URL이 올바른지 확인하십시오:

  ```text
  https://mcp.appsflyer.com/auth/mcp
  ```
* 새 세션 또는 환경에서 다시 연결을 시도하십시오.

</Accordion>

<div data-zendesk-anchors="h_01K9CJ9WQ3JJSYWDMNJ5GP7N04=disclaimer what-is-appsflyer-mcp=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-mcp%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_01JY3G849QAT2GC714FR6CADH2=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-mcp%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_set-up-appsflyer-mcp=appsflyer-mcp-%EC%84%A4%EC%A0%95 set-up-appsflyer-mcp=appsflyer-mcp-%EC%84%A4%EC%A0%95 h_01KT8Y9JEJEZ26BRHK530JDB0D=%EC%B0%B8%EA%B3%A0 h_authentication-methods=%EC%9D%B8%EC%A6%9D-%EB%B0%A9%EB%B2%95 authentication-methods=%EC%9D%B8%EC%A6%9D-%EB%B0%A9%EB%B2%95 h_browser-based-oauth-login=%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80-%EA%B8%B0%EB%B0%98-oauth-%EB%A1%9C%EA%B7%B8%EC%9D%B8 browser-based-oauth-login=%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80-%EA%B8%B0%EB%B0%98-oauth-%EB%A1%9C%EA%B7%B8%EC%9D%B8 h_bearer-token-authentication=%EB%B3%B4%EC%95%88-%ED%86%A0%ED%81%B0-%EC%9D%B8%EC%A6%9D bearer-token-authentication=%EB%B3%B4%EC%95%88-%ED%86%A0%ED%81%B0-%EC%9D%B8%EC%A6%9D h_set-up-by-client=%ED%81%B4%EB%9D%BC%EC%9D%B4%EC%96%B8%ED%8A%B8%EC%97%90-%EC%9D%98%ED%95%B4-%EC%84%A4%EC%A0%95%EB%90%A8 set-up-by-client=%ED%81%B4%EB%9D%BC%EC%9D%B4%EC%96%B8%ED%8A%B8%EC%97%90-%EC%9D%98%ED%95%B4-%EC%84%A4%EC%A0%95%EB%90%A8 claude-ai-and-claude-desktop=h_claude-ai-and-claude-desktop h_01KT8Y9JEJQNXK3SZ7M0ETH5RN=%EC%B0%B8%EA%B3%A0-1 h_set-up-claude-ai-and-desktop=claudeai-%EB%B0%8F-claude-%EB%8D%B0%EC%8A%A4%ED%81%AC%ED%86%B1-%EC%84%A4%EC%A0%95 set-up-claude-ai-and-desktop=claudeai-%EB%B0%8F-claude-%EB%8D%B0%EC%8A%A4%ED%81%AC%ED%86%B1-%EC%84%A4%EC%A0%95 h_test-claude-connection=claude-%EC%97%B0%EA%B2%B0-%ED%85%8C%EC%8A%A4%ED%8A%B8 test-claude-connection=claude-%EC%97%B0%EA%B2%B0-%ED%85%8C%EC%8A%A4%ED%8A%B8 claude-code=h_claude-code h_add-appsflyer-mcp-to-claude-code=claude-code%EC%97%90-appsflyer-mcp-%EC%B6%94%EA%B0%80 add-appsflyer-mcp-to-claude-code=claude-code%EC%97%90-appsflyer-mcp-%EC%B6%94%EA%B0%80 cursor-ide=h_cursor-ide vs-code=h_vs-code chatgpt=h_chatgpt custom-gpt-available-for-all-packages-including-free-enterprise=appsflyer-%EB%A7%9E%EC%B6%A4%ED%98%95-gpt-%EC%B6%94%EA%B0%80 mcp-in-chatgpt-supported-for-chatgpt-users-on-all-paid-plans=chatgpt%EC%97%90-appsflyer-mcp-%EC%B6%94%EA%B0%80 h_01KT8Y9JEJ806MVHJACM0VNM0K=%EC%B0%B8%EA%B3%A0-2 gemini-cli=h_gemini-cli h_add-appsflyer-mcp-to-gemini-cli=gemini-cli%EC%97%90-appsflyer-mcp-%EC%B6%94%EA%B0%80 add-appsflyer-mcp-to-gemini-cli=gemini-cli%EC%97%90-appsflyer-mcp-%EC%B6%94%EA%B0%80 h_troubleshoot-gemini-cli-authentication=gemini-cli-%EC%9D%B8%EC%A6%9D-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 troubleshoot-gemini-cli-authentication=gemini-cli-%EC%9D%B8%EC%A6%9D-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 copilot-cli=h_copilot-cli h_add-appsflyer-mcp-to-copilot-cli=appsflyer-mcp%EB%A5%BC-copilot-cli%EC%97%90-%EC%B6%94%EA%B0%80%ED%95%A9%EB%8B%88%EB%8B%A4 add-appsflyer-mcp-to-copilot-cli=appsflyer-mcp%EB%A5%BC-copilot-cli%EC%97%90-%EC%B6%94%EA%B0%80%ED%95%A9%EB%8B%88%EB%8B%A4 third-party-and-self-hosted-platforms=h_third-party-and-self-hosted-platforms h_mcp-connection-details=mcp-%EC%97%B0%EA%B2%B0-%EC%84%B8%EB%B6%80-%EC%A0%95%EB%B3%B4 mcp-connection-details=mcp-%EC%97%B0%EA%B2%B0-%EC%84%B8%EB%B6%80-%EC%A0%95%EB%B3%B4 h_01KT8Y9JEKZRB56RZJXMMN4WV0=%EC%B0%B8%EA%B3%A0-3 h_example-use-cases=%EC%82%AC%EC%9A%A9-%EC%82%AC%EB%A1%80-%EC%98%88%EC%8B%9C example-use-cases=%EC%82%AC%EC%9A%A9-%EC%82%AC%EB%A1%80-%EC%98%88%EC%8B%9C other-platforms=h_other-platforms use-multiple-accounts-or-agencies=h_use-multiple-accounts-or-agencies h_switch-between-accounts=%EA%B3%84%EC%A0%95-%EC%A0%84%ED%99%98%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80-%EA%B8%B0%EB%B0%98-oauth switch-between-accounts=%EA%B3%84%EC%A0%95-%EC%A0%84%ED%99%98%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80-%EA%B8%B0%EB%B0%98-oauth h_connect-multiple-accounts-simultaneously=%EC%97%AC%EB%9F%AC-%EA%B3%84%EC%A0%95%EC%9D%84-%EB%8F%99%EC%8B%9C%EC%97%90-%EC%97%B0%EA%B2%B0%EB%8B%B4%EB%8B%B9%EC%9E%90-%ED%86%A0%ED%81%B0 connect-multiple-accounts-simultaneously=%EC%97%AC%EB%9F%AC-%EA%B3%84%EC%A0%95%EC%9D%84-%EB%8F%99%EC%8B%9C%EC%97%90-%EC%97%B0%EA%B2%B0%EB%8B%B4%EB%8B%B9%EC%9E%90-%ED%86%A0%ED%81%B0 using-appsflyer-mcp=appsflyer-mcp-%EC%82%AC%EC%9A%A9 h_01JY3G1ZEC5Q30KP49RAA7EHRS=appsflyer-mcp-%EC%82%AC%EC%9A%A9 use-cases-and-prompts=%EC%82%AC%EC%9A%A9-%EC%82%AC%EB%A1%80-%EB%B0%8F-%ED%94%84%EB%A1%AC%ED%94%84%ED%8A%B8 h_01JY3WMZ41HHQ4G13DGV8DPJMW=%EC%82%AC%EC%9A%A9-%EC%82%AC%EB%A1%80-%EB%B0%8F-%ED%94%84%EB%A1%AC%ED%94%84%ED%8A%B8 h_01JZHT6BA2NX8GXNV8675XNVWT=%EC%A4%91%EC%9A%94 h_01JY3WZE6G2WB6DCWV68G1T36D=analyze-performance h_01K7P0A6V86FZ3YQTQ4N5JZ4ZX=analyze-skan-performance h_01JY3VJEQMRDFAFTKZMPZ90RHP=onelink-management h_01JY3VJEQMXD32NSEE0E0FWG60=knowledge-base-and-developer-support h_01K01CE5NQ56HRT967F78ETKMS=apps-management h_01K01CE5NQBW6AADMHEPBQQN7S=audiences-management audiences-management::6584184=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B4%80%EB%A6%AC h_01KWBYTJ8GCJ884DN6XXPXZYMJ=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B4%80%EB%A6%AC h_01JY3VJEQNYKZ3Z724XM9JRWZF=feedback-tool h_01K9SHEQBWKK6AC0GD0YQVVJJ9=cost-configuration-integration h_01KGM1A7V6NB16A1Q07V5FQG2M=ad-revenue-integrations h_01K338G5KA09TESMNC6Z88RJCP=user-management-and-role-control other-information=%EA%B8%B0%ED%83%80-%EC%A0%95%EB%B3%B4 h_01JZHTJ1FQMXX9GSAN31E8HAYF=%EA%B8%B0%ED%83%80-%EC%A0%95%EB%B3%B4 privacy-and-security=h_privacy-and-security h_data-processing=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B2%98%EB%A6%AC data-processing=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B2%98%EB%A6%AC h_credentials=%EC%9E%90%EA%B2%A9-%EC%A6%9D%EB%AA%85 credentials=%EC%9E%90%EA%B2%A9-%EC%A6%9D%EB%AA%85 h_permissions=%EA%B6%8C%ED%95%9C permissions=%EA%B6%8C%ED%95%9C h_read-only-access=%EC%9D%BD%EA%B8%B0-%EC%A0%84%EC%9A%A9-%EC%95%A1%EC%84%B8%EC%8A%A4 read-only-access=%EC%9D%BD%EA%B8%B0-%EC%A0%84%EC%9A%A9-%EC%95%A1%EC%84%B8%EC%8A%A4 h_ai-provider-data-usage=ai-%EC%A0%9C%EA%B3%B5%EC%97%85%EC%B2%B4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9A%A9 ai-provider-data-usage=ai-%EC%A0%9C%EA%B3%B5%EC%97%85%EC%B2%B4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9A%A9 h_certifications=%EC%9D%B8%EC%A6%9D certifications=%EC%9D%B8%EC%A6%9D h_01K044H4H18ED75GYQWMPDRA4R=tool-mapping h_01K01DT8656BQM1GW0HDHXGCY2=traits-and-limitations h_troubleshoot-connection-issues=%EC%97%B0%EA%B2%B0-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%EB%B0%A9%EB%B2%95troubleshoot-connection-issues troubleshoot-connection-issues=%EC%97%B0%EA%B2%B0-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%EB%B0%A9%EB%B2%95troubleshoot-connection-issues troubleshoot-browser-based-oauth-login=h_troubleshoot-browser-based-oauth-login troubleshoot-bearer-token-authentication=h_troubleshoot-bearer-token-authentication access-and-permission-issues=h_access-and-permission-issues general-connection-checks=h_general-connection-checks" />
