---
title: 고급 보안 패키지
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
  created_at: '2025-04-03T11:42:43Z'
  edited_at: '2026-10-14T10:28:45Z'
  id: 34053592094737
  locale: ko
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ko/articles/34053592094737
---
> **한눈에 보기:** 다음을 사용하여 계정 보호 강화 **고급 보안 패키지,** 엔터프라이즈급 ID 관리, 토큰 액세스 제어 및 확장된 감사 가시성을 위해 설계된 프리미엄 제품입니다.

<div id="intro" />

## 소개

고급 보안 패키지는 조직의 보안을 강화하는 세 가지 주요 기능을 제공합니다.

* **서비스 제한이 있는 다중 토큰 관리**: API, S2S 및 OneLink에서 확장 가능한 토큰 생성 및 세분화된 액세스 제어.
* **보존 기간이 연장된 감사 로그 API**: 플랫폼 활동에 대한 장기적인 가시성을 확보하고 감사 이벤트를 모니터링 스택에 통합합니다.
* **SCIM 프로비저닝**: ID 공급자를 통해 사용자 액세스 제어를 자동화하고 중앙 집중화합니다.
* **로그인을 위한 IP 허용 목록:** 무단 액세스를 방지하여 신뢰할 수 있는 네트워크 및 IP에서만 앱스플라이어 대시보드에 로그인할 수 있도록 합니다.

<div id="compare-the-standard-and-enterprise-grade-packages" />

### 표준 및 고급 패키지를 비교하십시오.

| 기능 | 표준 패키지 | 고급 보안 패키지 |
| --- | --- | --- |
| [단일 로그인(SSO)](/docs/enterprise-grade-security-package#accordion-item) | SSO 로그인(기존 고객만 해당) | 사용자 및 역할 관리를 자동화하는 SSO SAML 2.0 및 SCIM 프로비저닝 지원 |
| [토큰 관리](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | 토큰 유형별로 최대 2개 관리(API, S2S 또는 원링크) | 토큰 유형별로 최대 30개까지 관리하고, 세분화된 권한 설정 적용 가능 (최대 30개) |
| [감사 로그 접근](/docs/enterprise-grade-security-package#audit-log-api-and-extended-retention) | UI 액세스만, 90일 보존 데이터 | UI 및 API 접근, 180일 데이터 보관 |
| [역할 기반 사용자 관리(RBAC)](/docs/enterprise-grade-security-package#multitoken-management-with-restrictions) | 맞춤 설정 가능한 역할 최대 10개 | 맞춤 설정 가능한 역할 최대 50개 |
| [IP 허용 목록](/docs/enterprise-grade-security-package#ip-allowlist) | API에 대한 IP 허용 목록 | 보안 강화를 위한 로그인 및 API에 대한 IP 허용 목록 |
| 24/7 보안 모니터링 | 포함 | 포함 |
| 다단계 인증 | 포함 | 포함 |

<div id="multitoken-management-with-restrictions" />

<Accordion title="제한이 있는 다중 토큰 관리">

최대 생성 및 관리 **토큰 30개** 유형별(API, S2S, OneLink) **서비스 수준 제한 사항** 토큰에 대한 확장성, 보안 및 제어를 강화합니다.

<div id="key-features" />

#### 주요 기능

* 관리자는 최대 **유형당 토큰 30개**, 표준 토큰이 있는 2개의 토큰과 비교하여 더 큰 팀과 복잡한 워크플로를 지원합니다.
* API 토큰에 서비스별 액세스 권한을 할당하여 민감한 작업에 대한 액세스를 제한합니다.
* 토큰은 통합 또는 자동화를 중단하지 않고 취소하거나 교체할 수 있습니다.
* 토큰별 권한을 통해 내부 팀 및 외부 파트너와의 협업을 단순화합니다.

<div id="example" />

> 📄 **예시**
>
> 최소 권한 액세스를 유지하고 우발적인 데이터 노출을 방지하는 데 도움이 되는 두 개의 토큰을 만듭니다.
>
> **데이터 전용 액세스 토큰:** 집계된 데이터에만 액세스하는 토큰을 만듭니다. 이 토큰은 원시 데이터에 액세스하거나 구성 변경과 같은 작업을 수행할 수 없습니다. 분석 팀 또는 읽기 전용 대행사 사용자에게 사용합니다.
>
> **설정 전용 액세스 토큰:** 내부 팀이 구성 설정을 관리할 수 있지만 데이터를 끌어오는 것은 허용하지 않는 토큰을 발급합니다. 이렇게 하면 관리 기능이 데이터 액세스에서 분리됩니다.

<div id="note" />

> 📘 **참고**
>
> 표준 토큰에 대한 일반적인 정보는 <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">앱스플라이어 토큰 관리</Anchor>.

<div id="how-to-access-and-control-tokens" />

#### 토큰에 액세스하고 제어하는 방법

**제한된 토큰을 만들려면**

1. 상단 표시줄에서 계정 메뉴(이메일 주소 드롭다운) > **보안 센터를 엽니다.**
2. 로 이동 **토큰 관리** 페이지.
3. **토큰 만들기**를 클릭합니다.
4. 토큰 유형을 선택합니다.
   * API
   * S2S
   * 원링크
5. 때문에 **API 토큰**에서 하나 이상의 서비스를 선택합니다. **액세스 제한** 드롭다운.  
   액세스는 이진법입니다: 전체 액세스 또는 없음.
6. **저장**을 클릭합니다.

**토큰 관리**

토큰을 관리하려면 상단 표시줄에서 계정 메뉴(이메일 주소 드롭다운)를 엽니다>**보안 센터 -> 토큰 관리** 페이지.

여기서는 다음을 수행할 수 있습니다.

* 토큰 메타데이터 보기: 이름, 유형, 제한사항, 생성/만료
* 토큰을 개별적으로 삭제
* 감사 로그에서 토큰 활동 모니터링

<div id="note-1" />

> 📘 **참고**
>
> 토큰은 편집할 수 없습니다. 액세스를 변경하려면 토큰을 삭제하고 다시 생성합니다.

</Accordion>

<div id="audit-log-api-and-extended-retention" />

<Accordion title="감사 로그 API 및 보존 기간 연장">

기존 감사 로그 기능을 향상시키는 이 기능은 감사 로그 사용을 위한 API를 도입하고 데이터 보존 기간을 90일에서 180일로 연장합니다. 사용자 작업 로그에 장기간 액세스하거나 감사 이벤트를 외부 모니터링 도구에 통합해야 하는 팀에 적합 SOC 및 SEIM과 같은.

<div id="key-features-1" />

#### 주요 기능

* 전용 API를 사용하여 프로그래밍 방식으로 감사 로그에 액세스
* 최대 로그 보존 **180일**, 표준 감사 로그의 경우 90일과 비교
* 규정 준수, 보안 또는 운영 사용을 위해 데이터 필터링 및 내보내기
* 서비스별 토큰을 사용하여 로그 액세스 격리
* SIEM 도구, 대시보드 또는 클라우드 스토리지로 데이터 내보내기

<div id="note-2" />

> 📘 **참고**
>
> 표준 감사 로그에 대한 일반적인 정보는 <Anchor target="_blank" href="/marketers/ko/docs/audit-log">표준 감사 로그</Anchor>.

<div id="how-to-access-the-audit-log-via-api" />

### **API를 통해 감사 로그에 액세스하는 방법**

감사 로그 API를 사용하려면 다음을 수행합니다.

1. 화면 상단 표시줄에서 계정(이메일 주소) 아래 드롭다운 메뉴를 펼치고 로그아웃을 클릭합니다. 보안 센터
2. **감사 로그** 섹션에서 감사 로그 보기를 클릭합니다.
3. 로 이동 **토큰 관리** 페이지.
4. 기존 사용 또는 새 **API 토큰**.
5. 아래의 **액세스 제한**고르다 **감사 로그** 서비스.
6. 토큰을 사용하여 감사 로그 API 엔드포인트에 대한 요청을 인증합니다.

<div id="note-3" />

> 📘 **참고**
>
> API 토큰을 안전하게 저장해야 합니다. 생성 후 검색할 수 없습니다.

</Accordion>

<div id="accordion-item" />

<Accordion title="SSO 및 SCIM 프로비저닝">

SCIM 프로비저닝은 Okta, Entra ID(Azure), OneLogin, JumpCloud 또는 속성 기반 액세스를 지원하는 자체 관리형 IDP와 같은 ID 공급자(IdP)에서 직접 사용자 수명 주기 관리를 자동화하여 앱스플라이어 SSO 기능을 향상시킵니다. 이를 통해 조직은 수동 개입 없이 사용자를 온보딩, 업데이트 또는 비활성화할 수 있습니다.

SCIM을 통해 사용자를 동기화하면 실시간으로 액세스 권한을 완전히 제어할 수 있습니다. SAML 2.0 SSO와 결합하면 기업 고객을 위한 완벽한 ID 및 액세스 관리 솔루션을 형성할 수 있습니다.

<div id="key-features-2" />

#### **주요 기능**

* IdP(ID 공급자) 레코드를 기반으로 AppsFlyer에서 사용자를 자동으로 생성합니다.
* IdP의 사용자 역할 또는 상태 변경은 AppsFlyer에 즉시 반영됩니다.
* 사용 **SAML 2.0** 보안 SSO를 위해 및 **심** 프로비저닝을 위해 - Okta 및 Azure AD와 같은 주요 IdP와 호환됩니다.

<div id="how-to-set-up-scim-provisioning" />

#### **SCIM 프로비저닝을 설정하는 방법**

앱스플라이어에서 SCIM 프로비저닝을 사용하려면 다음을 수행해야 합니다.

1. [SSO 설정](/docs/enterprise-grade-security-package#sso-설정)
2. [SCIM 사용](/docs/enterprise-grade-security-package#scim-사용)

<div id="sso-set-up" />

#### SSO 설정

SSO를 설정하려면 다음을 수행해야 합니다.

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-1-set-up-the-idp-platform">IdP 플랫폼 설정</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-set-up-appsflyer">앱스플라이어에서 SSO 설정하기</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-configuration">SSO 구성 테스트</Anchor>

<div id="enable-scim" />

#### SCIM 사용

<div id="note-4" />

> 📘 **참고**
>
> SCIM을 활성화하려면 먼저 SSO를 설정해야 합니다

SCIM을 사용하도록 설정하려면 따라야 하는 몇 가지 단계가 있습니다.

* 팔로우 [idP 구성 지침](/docs/enterprise-grade-security-package#idp-명령-링크)
* 구성 [SCIM 연결](/docs/enterprise-grade-security-package#scim-연결)
* 추가 [SCIM 속성](/docs/enterprise-grade-security-package#scim-속성)
* 더하다 [역할](/docs/enterprise-grade-security-package#역할)
* 더하다 [외부 네임스페이스](/docs/enterprise-grade-security-package#external-namespace)

<div id="idp-instruction-links" />

#### IdP 명령 링크

<div id="the-instructions-for-the-idps-can-be-found-below-okta-entra-id-azure-onelogin-jumpcloud" />

##### IdP에 대한 지침은 아래에서 찾을 수 있습니다. <Anchor target="_blank" href="https://help.okta.com/en-us/content/topics/apps/apps_app_integration_wizard_scim.htm">옥타</Anchor>, <Anchor target="_blank" href="https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups#integrate-your-scim-endpoint-with-the-microsoft-entra-provisioning-service">Entra ID (Azure)</Anchor>, <Anchor target="_blank" href="https://onelogin.service-now.com/kb_view_customer.do?sysparm_article=KB0010298">원로그인</Anchor>, <Anchor target="_blank" href="https://jumpcloud.com/support/get-started-identity-management-connectors">점프클라우드</Anchor>

<div id="scim-connections" />

#### SCIM 연결

SCIM 연결에서 다음 필드를 채워야 합니다.

| **필드 이름** | **값** |
| --- | --- |
| SCIM 커넥터 기본 URL(SCIM 엔드포인트) | https://hq1.appsflyer.com/api/scim/v2 |
| 사용자의 고유 식별자 필드 | Username: |
| 인증 방법: "Authorization"이라는 HTTP 헤더 | 무기명 <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">앱스플라이어 API 토큰</Anchor>> |

<div id="scim-attributes" />

#### SCIM 속성

| **속성** | **유형** | **필수** | **필드 이름** | **외부 네임스페이스** | **설명** |
| --- | --- | --- | --- | --- | --- |
| 역할 | 문자열 | ✅ | 역할 | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | <ul><li>사용자에게 미리 정의된 역할 또는 사용자 지정 역할을 할당합니다.</li><li>입력해야 하는 앱스플라이어 역할 목록은 아래를 참조하세요</li></ul> |
| 향후의 모든 앱에 대한 액세스 허용 | Boolean | ❌ | allowAccessToAllFutureApps | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | 사용하도록 설정하면 사용자에게 새 앱에 대한 액세스 권한이 자동으로 부여됩니다. |
| 허용된 앱 ID | 문자열 | ❌ | appIDs | urn:ietf:params:scim:schemas:extension:AppsFlyer:2.0:User | 쉼표로 구분된 앱 ID 목록입니다. 모든 앱에 대해 비워 두거나 앱이 없는 경우 "없음"으로 설정합니다. |

<div id="roles" />

#### 역할

역할은 <Anchor target="_blank" href="/marketers/ko/docs/user-management#roles-tab">앱스플라이어 역할</Anchor>. 아래 표는 현재 앱스플라이어 역할과 해당 값을 보여줍니다. 사용자 지정 역할을 추가할 수 있습니다. JumpCloud의 경우 [제한](/docs/enterprise-grade-security-package#제한-사항) 아래.

| **표시 이름** | **값** |
| --- | --- |
| 관리자 | 관리자 |
| 팀 관리자 | team\_manager |
| 마케팅 리드 | marketing\_lead |
| 마케팅 | 제공합니다. |
| 마케팅 – 제한됨 | marketing\_limited |
| 기여자 | 개발자 |
| 회계 | 회계 |
| 보안 | 보안 |
| 품질 보증 | quality\_assurance |
| 커스텀 역할 | [사용자 지정 역할 값 입력] |

<div id="limitations" />

#### 제한 사항

| **제한 사항** | **설명** |
| --- | --- |
| **JumpCloud - 사용자 지정 속성** | <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#attribute-considerations">사용자 지정 속성은 지원되지 않습니다.</Anchor>. 해결 방법으로 역할 필드를 지원되는 필드로 설정합니다. 직장 주소. 보다 <Anchor target="_blank" href="https://jumpcloud.com/support/provision-and-manage-users-and-groups-in-apps-using-custom-scim-identity-management-integration#custom-scim-user-attributes">JumpCloud SCIM 지원</Anchor>. |

</Accordion>

<div id="ip-allowlist" />

<Accordion title="IP 허용 목록">

향상된 IP 허용 목록은 무단 액세스를 방지하여 보안을 강화하고 신뢰할 수 있는 네트워크만 플랫폼과 상호 작용할 수 있도록 합니다. 이 기능은 엄격한 보안 정책을 시행하거나 원격 액세스를 관리하는 기업에 특히 유용합니다.

<div id="frequently-asked-questions-about-our-security-package" />

<div id="how-quickly-can-i-implement-these-security-controls" />

<div id="does-this-replace-standard-security-features" />

<div id="how-long-are-audit-logs-retained" />

<div id="what-network-restrictions-can-i-apply" />

<div id="can-i-integrate-with-my-existing-security-tools" />

<div id="how-many-roles-and-api-tokens-can-i-create" />

<div id="what-compliance-standards-does-this-support" />

<div id="how-does-scim-provisioning-work" />

<div id="who-is-the-enterprise-grade-security-package-designed-for" />

<div id="what-is-appsflyers-enterprise-grade-security-package" />

<div id="removing-ips-from-the-list" />

<div id="important" />

<div id="adding-ips-to-the-list" />

<div id="key-features-3" />

#### 주요 기능

* 알 수 없는 IP의 로그인 시도를 차단하여 공격을 줄입니다.
* IP 주소 또는 범위를 지정하여 승인된 사용자와 네트워크만 플랫폼에 액세스할 수 있도록 하는 기능을 활성화합니다.
* VPN을 사용하거나 더 엄격한 액세스 제어가 필요한 조직에 이상적입니다.

</Accordion>

<div data-zendesk-anchors="intro=%EC%86%8C%EA%B0%9C h_01JRA2GVNZCDW8C9VW6GH3G4KE=%EC%86%8C%EA%B0%9C compare-the-standard-and-advanced-packages=%ED%91%9C%EC%A4%80-%EB%B0%8F-%EA%B3%A0%EA%B8%89-%ED%8C%A8%ED%82%A4%EC%A7%80%EB%A5%BC-%EB%B9%84%EA%B5%90%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01JVS101KETCVDMT1B2WZM89NF=%ED%91%9C%EC%A4%80-%EB%B0%8F-%EA%B3%A0%EA%B8%89-%ED%8C%A8%ED%82%A4%EC%A7%80%EB%A5%BC-%EB%B9%84%EA%B5%90%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01JQXQ178D9JKZEREHWTQ2FKBF=multitoken-management-with-restrictions key-features=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5 h_01JQXRDEMJF2NT73FP1TFJG63Z=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5 h_01JVRZRXPD4AC1GAMJ2HKC1R9E=%EC%98%88%EC%8B%9C h_01JVRZ0ACA19TGC9WJCZ562B70=%EC%B0%B8%EA%B3%A0 how-to-access-and-control-tokens=%ED%86%A0%ED%81%B0%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EA%B3%A0-%EC%A0%9C%EC%96%B4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01JQXSE4TTYXTWCKXDHB20KJ1Z=%ED%86%A0%ED%81%B0%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EA%B3%A0-%EC%A0%9C%EC%96%B4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01JVRZ9X0D5V765FTXHVHMR807=%EC%B0%B8%EA%B3%A0-1 h_01JQXQ178DHFQ2Y6JDYYBTKJ0V=audit-log-api-and-extended-retention key-features::8c048755=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5-1 h_01JQXR4X1CT8P8M3NYEVK0WQYM=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5-1 h_01JVRZ7WBBY3D8GJE2MJ2E4B0G=%EC%B0%B8%EA%B3%A0-2 how-to-access-the-audit-log-via-api=api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EA%B0%90%EC%82%AC-%EB%A1%9C%EA%B7%B8%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01JQXQM2H3VCJMWFRBJDWJ5FAZ=api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EA%B0%90%EC%82%AC-%EB%A1%9C%EA%B7%B8%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01JVRZ69C2JYY9SK12SEVG3KXF=%EC%B0%B8%EA%B3%A0-3 h_01JQXQ178DSG340QG8R05B8VNX=accordion-item key-features::e7dd8b4e=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5-2 h_01JV9W8DTENC21GS0380Q9DP8T=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5-2 how-to-set-up-scim-provisioning=scim-%ED%94%84%EB%A1%9C%EB%B9%84%EC%A0%80%EB%8B%9D%EC%9D%84-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01JV9W8DTFCE7Z0MQP96MK7BQC=scim-%ED%94%84%EB%A1%9C%EB%B9%84%EC%A0%80%EB%8B%9D%EC%9D%84-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 sso-set-up=sso-%EC%84%A4%EC%A0%95 h_01JV9W8DTFHJME1J1JKKJ3NA6C=sso-%EC%84%A4%EC%A0%95 enable-scim=scim-%EC%82%AC%EC%9A%A9 h_01JV9W8DTG50YYPQ9RS91K2CJ4=scim-%EC%82%AC%EC%9A%A9 h_01JVRZ3MC8J0B1E66A47GM5WYZ=%EC%B0%B8%EA%B3%A0-4 idp-instruction-links=idp-%EB%AA%85%EB%A0%B9-%EB%A7%81%ED%81%AC h_01JV9WBJCPQ0X5SKVVNK4TBYRR=idp-%EB%AA%85%EB%A0%B9-%EB%A7%81%ED%81%AC h_01JV9WTJ33KMJGZGM9P5PRK917=idp%EC%97%90-%EB%8C%80%ED%95%9C-%EC%A7%80%EC%B9%A8%EC%9D%80-%EC%95%84%EB%9E%98%EC%97%90%EC%84%9C-%EC%B0%BE%EC%9D%84-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EB%8B%A4-%EC%98%A5%ED%83%80-entra-id-azure-%EC%9B%90%EB%A1%9C%EA%B7%B8%EC%9D%B8-%EC%A0%90%ED%94%84%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C scim-connections=scim-%EC%97%B0%EA%B2%B0 h_01JV9WBNC51WYW03RKWHBTP0AG=scim-%EC%97%B0%EA%B2%B0 scim-attributes=scim-%EC%86%8D%EC%84%B1 h_01JV9WBS928Z7WKJ2A2CFSWNT4=scim-%EC%86%8D%EC%84%B1 roles=%EC%97%AD%ED%95%A0 h_01JV9WBX3JHEMAG62JCASYXB59=%EC%97%AD%ED%95%A0 limitations=%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01JV9DMY0Y3795TAT3Q1E3PZRM=%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01JVWCNK70QY6PKJRFZGEQ76SW=ip-allowlist key-features::cd0daf96=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5-3 h_01JVWCSA3D6DJZXJKKYDFWWPC0=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5-3" />
