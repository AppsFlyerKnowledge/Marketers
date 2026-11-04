---
title: 감사 로그
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-05-05T14:18:09Z'
  edited_at: '2026-10-14T10:30:34Z'
  id: 360007971697
  locale: ko
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ko/articles/360007971697
---
> **한눈에 보기:** 요약: 감사 로그를 사용하여 앱스플라이어 계정에 대한 무단 액세스를 식별하고 방지합니다. 계정의 보안 관련 활동 요약을 보고 다운로드합니다.

<div id="overview" />

## 개요

앱스플라이어 계정의 보안을 보호하기 위해 누가 귀하의 계정에 액세스하고 **어떻게** 액세스하는지 주기적으로 검토하는 것이 좋습니다. 지난 90일 동안의 감사 로그 데이터를 사용할 수 있습니다.

감사 로그에 액세스하는 방법:

1. 화면 상단 표시줄에서 계정(이메일 주소) 아래 드롭다운 메뉴를 펼치고 로그아웃을 클릭합니다. 보안 센터
2. **감사 로그** 섹션에서 **감사 로그 보기**를 클릭하십시오.

<div id="using-the-audit-log" />

## 감사 로그 사용

감사 로그에서 제공하는 데이터에 대한 설명과 해당 기능에 대한 요약이 아래 표에 제공됩니다.

[![audit_log.png](https://files.readme.io/4101dfb4dc84e4e916d165a22387bd6a84fa7889bc4e82e636c980fde1cac248-6867050961809.png)](https://files.readme.io/4101dfb4dc84e4e916d165a22387bd6a84fa7889bc4e82e636c980fde1cac248-6867050961809.png)

|  | 항목 | 설명 |
| --- | --- | --- |
| ![A.png](https://files.readme.io/66b5bb0c4ea35f232f65dbc8dcbdfd6a91c12cf94915b19d33dae44834127058-31237653543313.png) | 검색 상자 및 필터 | 표시되는 데이터를 필터링하여 보려는 항목에만 중점을 둡니다.<ul><li>검색 상자를 사용하여 특정 용어(예: 관련 앱 ID, 이메일 주소 등)로 데이터를 필터링합니다.</li><li>데이트 피커를 사용하여 데이터가 표시되는 기간을 선택합니다.</li><li>서비스 필터를 사용하여 액세스한 특정 서비스를 기반으로 데이터를 필터링합니다.<ul><li>시스템 액세스</li><li>연동 파트너 권한</li><li>유저 관리</li><li>유효성 검증 규칙</li><li>API 호출</li></ul></li></ul>**API 호출** 서비스는 리포트 가독성을 최적화하기 위해 기본적으로 선택 해제되어 있습니다. 리포트에 포함하려면 이 서비스를 선택해야 합니다. |
| ![B.png](https://files.readme.io/f63914d3fefb55b627559c6e4c7d7cdef89239c0376a14c25c713a0a76dbad1b-31237653544337.png) | 감사 로그 데이터 | 감사 로그의 각 항목에는 다음 데이터가 포함됩니다.<ul><li>**날짜 및 시간:** 서비스에 액세스한 날짜 및 시간(UTC)</li><li>**액세스한 앱/계정:**<ul><li>사용자 로그인(시스템 액세스) 및 사용자 관리의 경우 이 열에는 **계정** (계정 수준 액세스를 나타냄)이 표시됩니다.</li><li>API 호출의 경우 이 열에는 데이터에 액세스한 앱의 **계정** 액세스 또는 **앱 ID** 가 표시됩니다.</li></ul></li><li>**자격 증명**<ul><li>시스템 액세스 또는 사용자 관리의 경우 이 열에는 서비스에 액세스하는 사용자의 이메일 주소가 표시됩니다.</li><li>API 호출의 경우 이 열에는 사용된 앱스플라이어 API 토큰(V2)이 표시됩니다.</li></ul></li><li>**서비스:** 접근한 서비스(시스템 접근, 사용자 관리, API 호출)</li><li>**작업:** 기록된 작업(예: 로그인, 로그아웃, API에서 액세스한 데이터)</li><li>세부 정보 세부 정보: 기록된 작업에 대한 추가 세부 정보</li></ul> |
| ![C.png](https://files.readme.io/b428e77b299e10fe0701b7850cea1da8942905ad38d7b30c32f99f0240b22a63-5397303804945.png) | ![audit_log_download_button.png](https://files.readme.io/50e6cfef2aceb4b199f79008090da39d021f94be8d88d329bb8c8a0723edfa75-6867407922577.png) | 다운로드 버튼을 클릭하여 감사 로그를 CSV 파일로 다운로드합니다.<ul><li>검색 상자 및 필터를 사용하여 화면에 표시된 대로 리포트에 적용된 모든 선택 사항은 다운로드한 파일에도 적용됩니다.</li></ul> |

<div id="troubleshooting" />

## 문제 해결

<div id="why-does-an-advertiser-audit-log-show-partner-api-call-requests" />

<Accordion title="광고주 감사 로그에 파트너 API 호출 요청이 표시되는 이유는 무엇인가요?">

파트너가 광고주가 소유한 앱에 대해 API를 요청하면 파트너와 광고주가 모두 감사 로그에서 요청을 볼 수 있습니다.

광고주가 토큰을 사용하여 API를 요청하면 광고주의 감사 로그에만 표시됩니다.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01H9Q3XYYBKYSRP3T0R2MP712C=%EA%B0%9C%EC%9A%94 using-the-audit-log=%EA%B0%90%EC%82%AC-%EB%A1%9C%EA%B7%B8-%EC%82%AC%EC%9A%A9 h_01H9Q3XYYBBCB6PXBZBF97QE11=%EA%B0%90%EC%82%AC-%EB%A1%9C%EA%B7%B8-%EC%82%AC%EC%9A%A9 troubleshooting=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01H9Q3XYYB24R3EATM7R32V0G7=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01H9Q3XYYCHWJ1NQS389MR311X=why-does-an-advertiser-audit-log-show-partner-api-call-requests" />
