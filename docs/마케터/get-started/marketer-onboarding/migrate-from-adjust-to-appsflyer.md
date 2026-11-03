---
title: Adjust에서 앱스플라이어로 마이그레이션
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
  created_at: '2024-12-02T10:01:48Z'
  edited_at: '2026-10-14T10:26:11Z'
  id: 30563700129297
  locale: ko
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/ko/articles/30563700129297
---
> **한눈에 보기:** Adjust에서 앱스플라이어로의 마이그레이션을 계획하세요. 마이그레이션 기간 동안 이중 청구, 데이터 중복 및 데이터 유실을 방지하는 방법을 알아봅니다.

<Image alt="" src="https://files.readme.io/cc012894dd05255c0b7fa448b1c95d925d556ddb43dc461086bb71e9279da90d-30633481029137.png" width="1765px" />

## 앱스플라이어로 마이그레이션

Adjust에서 앱스플라이어로의 마이그레이션은 어트리뷰션 및 마케팅 애널리틱스를 위한 신뢰할 수 있고 포괄적인 플랫폼으로의 원활한 전환을 제공합니다. 앱스플라이어는 브랜드가 업계 변화에 대처할 수 있도록 설계된 고급 툴 세트와 함께 안전하고 공정한 솔루션을 제공합니다. 글로벌 고객 지원과 지속적인 제품 개선에 중점을 두고 있는 앱스플라이어는 기업이 성장하고 적응하는 데 필요한 툴과 인사이트를 갖추도록 지원하는 것을 목표로 합니다.

#### 앱스플라이어와 애드저스트 간의 측정 비교

마이그레이션을 고려할 때, 동일한 미디어 소스 및 캠페인 전체에서 앱스플라이어와 Adjust의 어트리뷰션 측정 방식을 비교해 보고 싶을 수 있습니다. 하지만 모든 미디어 소스가 둘 이상의 MMP를 통한 측정을 지원하는 것은 아닙니다. 복수 측정을 지원하는 미디어 소스라 하더라도 어트리뷰션 데이터 불일치를 방지하기 위해 특정 제한 사항이나 까다로운 조건이 존재할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/measuring-attribution-with-multiple-mmps">여러 MMP의 어트리뷰션 측정</Anchor>에서 자세한 내용을 살펴보세요.

## 작업

[![](https://files.readme.io/7deffffc032dce24c30b5b73ae09c083a227ac6f4ec13be224bb7f7fb5b7042f-30642410251793.png)](https://files.readme.io/7deffffc032dce24c30b5b73ae09c083a227ac6f4ec13be224bb7f7fb5b7042f-30642410251793.png)다음 표는 마이그레이션에 필요한 주요 단계를 설명합니다. 일반적인 작업들의 상세 내역을 확인하고 진행 상황을 기록하려면 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQqbJIkE7kD87uSm7MH7zfkPN1VLuBaeotTEHAID2pYFVWM_LuQIA2AE2-8fVnXH-DrbXUQCs2iaiDe/pub?output=xlsx">이 스프레드시트</Anchor>를 다운로드하세요.

이 작업들은 동시에 진행할 수 있으며, 이는 마케터, 개발자, 데이터 엔지니어가 대부분의 경우 각자에게 할당된 타스크를 병렬로 수행할 수 있음을 의미합니다. 다음 사항을 권장합니다:

* 안 1: 앱스플라이어 SDK가 포함된 업데이트 앱을 출시하기 전에 모든 작업을 완료하세요.
* 디바이스 ID 마이그레이션을 수행하기 전에 기존의 마케팅 캠페인을 일시정지합니다.

<table><thead><tr><th>단계</th><th>담당자</th><th>예상 시간</th><th>비고</th></tr></thead><tbody><tr><td>1. 앱스플라이어 계정 만들기</td><td>마케터/앱스플라이어 대시보드 사용자</td><td>2시간</td><td> </td></tr><tr><td>2. 앱스플라이어에 앱 추가</td><td>마케터/앱스플라이어 대시보드 사용자</td><td>2시간</td><td> </td></tr><tr><td>3. SDK 연동</td><td>앱 개발자</td><td>1일 + 테스트 및 반복 1주일</td><td><ul><li> <strong>권장 사항</strong>: 테스트를 위해 사전 프로덕션 앱에 앱스플라이어 SDK를 연동하십시오.</li><li>다른 모든 과제가 완료된 후에 앱 스토어에서 프로덕션 앱을 업데이트해야 합니다.</li></ul></td></tr><tr><td>4. 디바이스 마이그레이션(선택 사항)</td><td>데이터 엔지니어</td><td>1&#126;2주</td><td rowspan="2"><ul><li>마이그레이션 전에 기존 캠페인을 일시 중지하고, 앱 버전이 업데이트된 후에 캠페인을 재개하는 것을 고려하세요. </li><li>완전한 적용 범위를 보장하기 위해 최종 마이그레이션 날짜에 디바이스 마이그레이션을 반복하세요. </li></ul></td></tr><tr><td>5. 캠페인 마이그레이션</td><td>마케터/UA 관리자</td><td>각 미디어 소스마다 1-3일</td></tr><tr><td>6. 데이터 리포팅 설정</td><td>데이터 엔지니어</td><td>3&#126;6주</td><td> </td></tr></tbody></table>

<Accordion title="1단계: 앱스플라이어 계정 만들기">

**앱스플라이어 계정 만들기**:

1. <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">앱스플라이어 계정을 만듭니다</Anchor>.
2. <Anchor target="_blank" href="/marketers/ko/docs/user-management">적합한 권한이 있는 계정 사용자 추가</Anchor>

</Accordion>

<Accordion title="2단계: 앱 추가">

**앱스플라이어에 앱을 추가하려면**:

1. 앱스플라이어에 <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">앱을 추가</Anchor>하세요.
2. [선택 사항] 활성 사용자 정의에 맞게 기본 90일 <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 기간</Anchor>을 변경합니다.
3. 앱스플라이어 앱 온보딩 위저드의 일환으로, SDK 연동 및 인앱 이벤트 매핑을 위한 가이드와 타스크를 담당 개발자에게 이메일로 작성하여 발송하세요.

</Accordion>

<Accordion title="3단계: SDK 연동">

앱에 연동된 앱스플라이어 SDK는 앱과 앱스플라이어 플랫폼을 연결하는 링크 역할을 합니다. 앱 인스톨, 앱 열기, 인앱이벤트 등을 리포트합니다.

**앱스플라이어 SDK 연동 방법**:

1. 마케터로부터 SDK 연동 및 인앱 이벤트 매핑을 위한 가이드와 타스크가 담긴 이메일을 수신합니다.
2. 이메일 안내 지침을 따르고 <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?sourceos=android&utm_source=kb&utm_medium=sdk-int-wizard-orvw">앱스플라이어 SDK 연동 마법사</Anchor>를 사용하여 앱스플라이어 SDK를 앱에 연동하세요.
   * 마법사는 개발자가 설치부터 연동 테스트 성공에 이르기까지 전 과정을 진행할 수 있도록 안내합니다. 또한 개발자가 인앱 이벤트를 정의하고 앱스플라이어로의 이벤트 전송 테스트를 성공적으로 마칠 수 있도록 안내합니다. <Anchor target="_blank" href="/marketers/ko/docs/for-ios-and-android-the-sdk-integration-wizard">SDK 연동 마법사에 대해 자세히 알아보기</Anchor>
   * <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">Android</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">iOS</Anchor> SDK 연동을 위한 추가 개발자 가이드를 참조하세요.
   * 앱스플라이어 스킴을 사용하여 기록하려는 인앱 이벤트를 매핑합니다.  
     이것은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">SDK</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>를 통해 수행할 수 있습니다.
3. Adjust SDK를 제거하세요.  
   이 작업을 즉시 수행하여 앱스플라이어로 전면 전환하거나, 일정 기간 동안 두 SDK를 동시에 실행할 수 있습니다. 아래 표에서 옵션에 대한 분석을 확인하세요.

| 옵션 | 업데이트 후  <br />변경되는 사항 | 영향 |
| --- | --- | --- |
| 애드저스트 SDK 제거(권장) | 앱스플라이어만이 신규 인스톨 및 업데이트 사용자를 기록합니다.  <br />사용자가 앱을 업데이트할 때까지는 Adjust에서 해당 사용자가 수행한 이벤트가 여전히 표시됩니다. | <ul><li>빠른 전환.</li><li>이중 어트리뷰션 없음.</li></ul> |
| 전환 기간 동안 Adjust SDK 유지 | 앱스플라이어와 Adjust는 신규 설치를 어트리뷰션하고 이벤트를 리포팅합니다. 나중에 Adjust SDK를 제거하세요. | <ul><li>데이터 유효성 검증 가능. 즉, 앱스플라이어와 Adjust의 데이터를 서로 비교해 볼 수 있습니다.</li><li>플랫폼 모두에서 기여가 인정되는 중복 어트리뷰션이 발생하여 광고 네트워크로부터 중복 과금이 청구될 수 있습니다. 아래 예시 참고.</li><li>업무량 증가.</li></ul> |

4. 이 마이그레이션 아티클에 있는 다른 모든 작업이 완료된 후, 앱스플라이어 SDK가 포함된 앱 버전을 마켓에 출시하세요. 신규 사용자는 앱스플라이어에 의해 어트리뷰션됩니다.   
   **참고**:
   * iOS, Google Play 및 관련 있는 모든 Android 제3자 앱 마켓(제조사 앱스토어 등)용 앱을 반드시 업데이트하세요.
   * Android 앱이 비공식 APK 사이트에 존재할 수도 있습니다. 웹에서 앱의 패키지 이름을 검색하여 확인하세요.  APK 사이트가 최신 버전으로 업데이트되는 데는 어느 정도 시간이 걸리므로, 앱스플라이어 SDK가 없는 이전 버전을 설치하는 오가닉 사용자가 유입될 수 있습니다.
   * 앱스토어에서 앱 업데이트가 완전히 반영되기까지 며칠이 걸릴 수도 있습니다. 이 기간 동안에 앱을 설치한 사용자에게는 이전 버전이 계속 제공될 수 있습니다.

</Accordion>

<Accordion title="4단계: 디바이스 마이그레이션 — 선택사항">

디바이스 마이그레이션은 기존 사용자 디바이스 ID(IDFA, IDFV, GAID, CUID)의 목록을 앱스플라이어로 업로드하는 프로세스입니다. (필요한 모든 디바이스 ID를 보유하고 있지 않은 경우, CUID를 사용하여 마이그레이션 프로세스를 진행할 수 있도록 지원하는 귀하의 CSM에게 연락할 수 있습니다.) 앱스플라이어 SDK가 포함될 새 앱 버전을 마켓에 출시하기 전에 이 프로세스를 수행해야 합니다. 디바이스를 마이그레이션할 때 [어트리뷰션 마이그레이션](/docs/migrate-from-adjust-to-appsflyer#attributed-migration)과 [비어트리뷰션 마이그레이션](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration)의 두 가지 옵션이 있습니다.

디바이스 마이그레이션은 이전에 앱을 다운로드하고 Adjust에 의해 기여가 인정된 기존 앱 사용자들과 관련된 데이터 문제를 해결해 줍니다. 를 들어, 원래 Adjust에서 SRN의 성과로 인정되었던 사용자가 아직 룩백 윈도우 기간 내에 있는 상태에서, 앱스플라이어 하에 해당 SRN에 의해 다시 한번 성과로 주장될 때 발생하는 'SRN 중복 과금' 문제가 이에 해당합니다.

> 📄 **예시**
>
> * 6월 15일에 신규 사용자가 페이스북 앱에서 광고를 클릭하고 귀하의 앱을 설치했습니다.
> * 6월 24일에 사용자는 앱을 앱스플라이어 SDK 연동 버전으로 업데이트하고 실행했습니다. 앱스플라이어 측면에서 이 사용자는 실시간 어트리뷰션해야 하는 신규 사용자입니다.
> * 앱스플라이어는 사용자의 디바이스 ID를 사용하여 Meta 광고에 쿼리를 보냅니다. 사용자가 여전히 Meta 광고의 28일 룩백 윈도우(기여 인정 기간) 내에 있기 때문에, Meta 광고는 해당 사용자를 자체 기여로 판정합니다. 이로 인해 앱 소유자는 동일한 사용자에 대해 중복 과금을 지불하게 됩니다.

디바이스를 마이그레이션하면 데이터는 앱스플라이어에서 다음과 같이 반영됩니다.

* **설치** **데이터:** <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window#reinstall">재설치</Anchor>과 유사하게, 마이그레이션된 디바이스는 설치 데이터를 갖지 않습니다. 마이그레이션된 디바이스 설치는 앱스플라이어에 표시되지 않습니다.
* **인앱 이벤트 및 세션 데이터:** [비어트리뷰션 디바이스 마이그레이션](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration) 방식을 사용할 경우 오가닉으로 기록 및 표시되며, [어트리뷰션 방식](/docs/migrate-from-adjust-to-appsflyer#attributed-migration)을 사용할 경우 해당 미디어 소스 및 캠페인의 성과로 기여 처리됩니다.
* **리타겟팅:** 리어트리뷰션과 리인게이지먼트는 정상적으로 표시됩니다.
* **액티비티 데이터:** 정상적으로 표시됩니다.
* **리텐션 및 코호트 데이터:** 마이그레이션된 디바이스는 설치 기록이 없습니다. 따라서 이러한 디바이스는 어떠한 코호트 그룹과도 연결되지 않으며, 코호트 및 잔존율 리포트에 표시될 수 없습니다.

> 📘 **참고**
>
> 마이그레이션된 날짜로부터 180일 이내에 앱을 실행하지 않으면, 마이그레이션된 모든 디바이스 데이터가 삭제됩니다. 따라서, 180일의 기간이 지난 후에 앱을 실행하면 신규 설치로 기록됩니다.

**디바이스를 마이그레이션하는 방법:**

1. 마이그레이션할 사용자 대상을 결정하십시오. 모든 기존 사용자를 마이그레이션하거나(이 경우 앱스플라이어로부터 정확한 리어트리뷰션 데이터를 얻지 못할 수 있음), 최근에 앱을 설치한 사용자만 마이그레이션할 수 있습니다(이 경우 다소 오래된 사용자에 대한 중복 과금이 발생할 수 있음).  
   **현재 설정된 리어트리뷰션 윈도우 동안 활성 상태였던 사용자들을 마이그레이션하는 것을 권장합니다.** 예를 들어, 앱의 리어트리뷰션 윈도우가 90일인 경우, 지난 90일 동안 최소 한 번 이상의 세션이 발생한 사용자를 마이그레이션하세요.
2. [선택 사항] 마케터 또는 UA 매니저에게 디바이스 마이그레이션이 완료될 때까지 기존 마케팅 캠페인(SRN, 비SRN 광고 네트워크, 자체 미디어 등)을 일시 중단하도록 안내하십시오.  
   캠페인을 일시 중단하지 않기로 결정한 경우, 앱스플라이어 SDK가 포함된 업데이트된 앱 버전이 앱 스토어에 출시되는 즉시 타사 어트리뷰션 벤더에 남아 있는 나머지 디바이스 ID를 마이그레이션하십시오.
3. 선택한 사용자 대상을 기반으로, [어트리뷰션 데이터가 포](/docs/migrate-from-adjust-to-appsflyer#attributed-migration)함되었거나 [포함되지 않은](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration) 마이그레이션 구조를 사용하여 CSV 파일을 준비하세요. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">샘플 CSV 참조</Anchor>
4. 앱스플라이어 CSM을 CSV로 전송하세요.  
   사용자의 CSM은 디바이스 ID를 앱스플라이어로 마이그레이션합니다.

</Accordion>

<Accordion title="5단계: 캠페인 마이그레이션">

기존 마케팅 캠페인을 앱스플라이어로 전환하여 앱스플라이어 어트리뷰션을 활성화하고, 비용이 중복 청구되거나 어트리뷰션 데이터가 누락되는 것을 방지하세요.

**참고**: 한 번에 몇 개의 마케팅 캠페인만 선택하여 순차적으로 마이그레이션을 진행할 수 있습니다. 이 경우, 마이그레이션하려는 캠페인을 미디어 소스(예: 광고 네트워크 또는 대행사), 지역 또는 캠페인별로 세분화하여 선택할 수 있습니다.

다음 섹션에서는 다양한 유형의 미디어 소스에 대해 앱스플라이어 측정을 활성화하는 데 필요한 사항을 설명합니다 (SRN, 비 SRN 애드 네트워크, 온드 미디어 및 SKAN).

#### SRNs

SRN은 MMP(Mobile Measurement Partner)가 특정 디바이스의 인게이지먼트에 대해 쿼리하는 경우 응답합니다. 앱스플라이어와 Adjust가 동일한 디바이스 설치에 대해 동일한 SRN에 쿼리를 보내는 경우, 비용이 중복 청구될 수 있습니다.

**SRN 캠페인을 마이그레이션하는 방법**:

* 앱스플라이어에서 관련 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#앱스플라이어와-통합된-srn">SRN</Anchor>을 활성화하고 설정하세요.

> 📘 **참고**
>
> * SRN은 여러 MMP를 실행할 수 있습니다(메타 광고 및 트위터 제외).
> * Meta 광고는 인앱 이벤트의 중복을 제거할 수 없습니다.

#### 비-SRN 애드 네트워크

광고 네트워크의 어트리뷰션 링크는 사용자 인게이지먼트를 기록한 후, 실제 설치 전환으로 연결된 인게이지먼트를 찾아 어트리뷰션을 성립시키는 데 활용됩니다.

**비-SRN 광고 네트워크 캠페인을 마이그레이션하는 방법**:

1. 앱스플라이어에서 관련 광고 네트워크를 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">활성화</Anchor>하세요.
2. 각 광고 네트워크에 대해 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">앱스플라이어 어트리뷰션 링크를 생성</Anchor>합니다.
3. 각 캠페인의 기존 링크를 앱스플라이어 어트리뷰션 링크로 전환합니다.

#### 온드 미디어

온드 미디어는 사용자가 다음에서 사용하는 어트리뷰션 링크를 말합니다.

* 콘텐츠 공유하기
* 웹-투-앱
* 이메일
* SMS
* 소셜 미디어 포스트
* 블로그
* 인터넷 커뮤니티(Quora 등)
* 그 외 다수

이 캠페인에서는 앱스플라이어가 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크</Anchor>를 사용합니다. 원링크는 사용자의 디바이스를 기반으로 올바른 앱 스토어, 앱 내부 화면으로 직접 이동시키거나 특정 웹 URL 및 랜딩 페이지로 리다이렉트합니다.

**Adjust 링크를 앱스플라이어 원링크 링크로 변경하려면**:

* 원링크는 사용자의 디바이스를 기반으로 올바른 앱 스토어, 앱 내부 화면으로 직접 이동시키거나 특정 웹 URL 및 랜딩 페이지로 리다이렉트합니다.

#### SKAN

SKAdNetwork(SKAN) 어트리뷰션의 경우, 변환 값은 SDK 하나만 업데이트할 수 있습니다. 그렇지 않으면, SKAN 데이터는 무의미하게 됩니다. 따라서 마이그레이션 후에 앱스플라이어 SDK만이 SKAN 변환 값을 업데이트합니다.

<Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">앱스플라이어에서 SKAN 전환 값 설정에 대해 자세히 알아보기.</Anchor>

</Accordion>

<Accordion title="6단계: 데이터 리포팅 설정">

여러 가지 방법을 사용하여 앱스플라이어에서 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-apis">로우</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/analytics-and-aggregate-reporting-apis">집약형</Anchor> 보고 데이터를 가져올 수 있습니다. 방법을 숙지하고 관련된 사용자와 관련된 방법을 설정하세요.

리포팅 메서드에는 다음이 포함됩니다.

* 대시보드
* 리포트 내보내기
* Push API
* Pull API
* 데이터 락커

마이그레이션 전에 귀사의 시스템은 Adjust와 함께 설정한 리포팅 구조, 필드 및 파라미터에 따라 Adjust로부터 수집된 어트리뷰션 데이터를 저장합니다. 앱스플라이어가 데이터를 올바르게 리포트하려면 현재 리포트 구조를 앱스플라이어 리포트 구조, 필드 및 파라미터에 적용하고 매핑해야 합니다.

**리포트 구조를 적용하고 매핑하는 방법:**

* Adjust에서 앱스플라이어로 리포트 데이터 구조를 빠르게 조정 및 마이그레이션할 수 있도록 지원이 필요하다면 앱스플라이어 CSM에게 문의하세요.

</Accordion>

## 추가 정보

<Accordion title="어트리뷰션된 마이그레이션">

이 방법으로 앱스플라이어에 마이그레이션된 디바이스는 이전 어트리뷰션 벤더가 리포팅한 미디어 소스 및 해당 애드 네트워크의 데이터 보유 정책에 따라 인앱 이벤트와 세션이 기록되고 표시됩니다.

#### 어트리뷰트된 디바이스 마이그레이션 CSV 구조

| 열  <br />이름 | 설명 | 필수 | 예시 |
| --- | --- | --- | --- |
| app\_id | 앱스플라이어 대시보드에 표시되는 앱 ID | 예 | <ul><li>Android: com.great.app1</li><li>iOS: id123456789</li></ul> |
| platform | 디바이스 플랫폼: ios 또는 android | 예 | <ul><li>ios</li><li>android</li></ul> |
| device\_id | <ul><li>안드로이드: gaid 또는 android\_id</li><li>iOS: IDFV(사용 가능한 경우 권장됨) 또는 IDFA</li><li>동일한 디바이스 ID와 앱 ID의 조합을 여러 행에 중복으로 입력하지 마세요. 중복이 발생하면 파일의 마지막 발생이 사용됩니다.</li></ul> | 예 | <ul><li>**gaid** (소문자): 9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**android\_id** (소문자): f35aea8908254891</li><li>**IDFV** (대문자) A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA** (대문자) 9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>안드로이드: advertiserId (amazon\_aid도 지원)j, android\_id</li><li>iOS:idfa 또는 idfv</li><li>현재 OAID, IMEI와 같은 다른 식별자는 지원되지 않습니다.<br />구글 플레이 외 다른 곳에서의 안드로이드 사용자의 경우, 어트리뷰션 되지 않은 마이그레이션을 사용하십시오.</li></ul> | 예 | <ul><li>advertiserId</li><li>android\_id</li><li>idfa</li><li>idfv</li></ul> |
| install\_time | <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor> UTC 형식을 따른 최초 앱 설치 시간:  <br />**yyyy-mm-ddTHH:MM:SS.SSS** | 아니요 | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>다음 중 하나:<ul><li>앱스플라이어 파트너 ID</li><li>커스텀 미디어 소스(파트너 ID는 안됨)</li></ul></li><li>앱스플라이어에서 필요한 파트너 ID 목록을 얻는 방법:<ul><li><Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">모든 관련 연동 파트너를 활성화합니다.</Anchor></li><li>모든 활성 연동 목록에 대해 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">활성 연동 API 가져오기</Anchor>를 실행합니다.</li><li>API의 **media\_source\_name** 을 CSV의 **media\_source** 값으로 사용합니다.</li><li>예외:<ul><li>Apple Search Ads의 경우 **Apple Search Ads**를 사용합니다.</li><li>Twitter의 경우 **twitter**를 사용합니다.</li></ul></li></ul></li><li>형식: 값은 대소문자를 구분합니다.</li></ul> | 예 | 논오가닉: facebook\_int, googleadwords\_int<br /><br />오가닉: organic |
| integrated\_partner | <ul><li>미디어 소스가 연동된 파트너인지 아닌지 표시합니다. 오가닉인지 또는 사용자정의 미디어 소스인지를 의미합니다.</li><li>형식: 값은 대소문자를 구분합니다.</li></ul> | 예 | <ul><li>yes</li><li>no(media\_source가 커스텀인 경우)</li></ul> |
| campaign | 더 세부적인 어트리뷰션 상세 내역을 위해, 원래의 캠페인 이름을 제공하십시오.<br /><br />형식: 문자열 | 아니요 |  |
| campaign\_id | 더 세부적인 어트리뷰션 상세 내역을 위해, 원래의 캠페인 ID를 제공하십시오.<br /><br />형식: 공백이 허용되지 않는 문자열 | 아니요 |  |

**CSV 파일 규칙:**

* CSV 파일에는 여러 앱의 사용자 디바이스가 포함될 수 있습니다.
* 동일한 디바이스 ID와 앱 ID의 조합을 여러 행에 중복으로 입력하지 마세요. 중복이 발생하면 파일의 마지막 발생이 사용됩니다.
* 모든 컬럼 헤더 app\_id, platform, device\_id, id\_type, install\_time, media\_source, integrated\_partner, campaign, campaign\_id가 포함되어야 합니다. **참고**: 필드의 순서는 중요하며 유지해야 합니다.
* 동일한 디바이스에 IDFV및 IDFA를 둘 다 추가할 수 있지만 별도의 행에 있어야 합니다. 별도의 행에 있는 모든 필드는 device\_id를 제외하고 동일해야 합니다.
* 각 행은 쉼표로 구분된 정확히 9개의 필드를 포함해야 합니다.
* 필수가 아닌 필드는 비워두세요(공백).
* 파일은 최대 2천만 개의 행을 포함할 수 있습니다.
* 파일이 여러 개 있는 경우 각 파일에 고유한 이름을 할당하십시오.
* UTF-8을 사용하여 데이터를 인코딩합니다.
* [선택사항] ZIP 또는 GZIP을 사용하여 파일을 압축하세요.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=0&single=true&output=csv">샘플 CSV 참조</Anchor>

</Accordion>

<Accordion title="어트리뷰션 되지 않은 마이그레이션">

이 방법을 통해 앱스플라이어에 마이그레이션된 디바이스는 오가닉 사용자로 기록됩니다(그러나 표시되지는 않습니다). 이들의 인앱 이벤트와 세션도 또한 오가닉으로 기록되고 표시됩니다.

#### 어트리뷰션되지 않은 디바이스 마이그레이션 CSV 파일 구조

| 옵션 | 열 | 사용할 때 | 예시 |
| --- | --- | --- | --- |
| 1 | App ID + IDFA/GAID/IDFV | <ul><li>모든 안드로이드 사용자가 GAID 식별자를 가진 경우.</li><li>iOS 사용자만 있는 경우.</li></ul> | [![device_migration_file_option_1.png](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png)](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png) |
| 2 | 앱 ID + 디바이스 ID + 디바이스 ID 유형 | <ul><li>일부 Android 사용자에게 GAID는 없고 IMEI 또는 Android ID만 있는 경우(제3자 앱스토어 마켓, 4.4.2 미만의 Android 버전).</li><li>Android ID는 16진법 형식입니다.</li></ul>**참고**:<ul><li>**ID 유형** 열에는 advertiserId(amazon\_aid도 지원됨), idfa, idfv, android\_id, imei와 같은 정확한 문자열을 사용하세요.</li><li>android\_id 또는 imei를 사용하는 상태에서, 향후 앱스플라이어가 더 적합한 식별자를 수신하게 되면 새로운 어트리뷰션이 기록될 수 있습니다.</li></ul> | [![device_migration_file_option_2.png](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png)](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png) |

**CSV 파일 규칙:**

* CSV 파일에는 여러 앱의 사용자 디바이스가 포함될 수 있습니다.
* 각 행에는 앱당 단일 디바이스 ID가 포함됩니다.
* 선택한 파일 구조 옵션에 따라 파일 열은 다음과 같아야 하며(나열된 순서대로):
  * Option 1: app\_id,device\_id
  * Option 2: app\_id,device\_id,id\_type
* 소문자로 된 앱 ID
* 소문자로 된 안드로이드 ID
* 대문자로 된 IDFA/IDFV
* 최대 2,500만 행 허용

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">샘플 CSV 참조</Anchor>

</Accordion>
