---
title: 타 업체에서 앱스플라이어로 마이그레이션 하기
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2019-07-01T13:11:37Z'
  edited_at: '2026-10-14T10:26:26Z'
  id: 360001923697
  locale: ko
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/ko/articles/360001923697
---
> **한눈에 보기:** 요약: 다른 어트리뷰션 공급업체의 앱스플라이어로 마이그레이션을 계획합니다. 마이그레이션 기간 동안 이중 청구, 데이터 중복 및 데이터 유실을 방지하는 방법을 이해합니다.

마이그레이션 흐름

<div id="about-migrating-to-appsflyer-from-other-vendors" />

## 타 업체에서 앱스플라이어로 마이그레이션 하기

다른 공급업체의 앱스플라이어로 마이그레이션하는 데는 다음과 같은 기본 태스크가 포함됩니다.

* [SDK 통합](/docs/migration-to-appsflyer-from-other-vendors#sdk-integration)
* [디바이스 데이터 마이그레이션](/docs/migration-to-appsflyer-from-other-vendors#device-migration%E2%80%94optional)
* [캠페인 데이터 마이그레이션](/docs/migration-to-appsflyer-from-other-vendors#campaign-migration)
* [데이터 리포트 설정](/docs/migration-to-appsflyer-from-other-vendors#data-report-setup)

이런 태스트를 동시에 작업할 수 있습니다. 그렇지만 이때 권장되는 사항은 다음과 같습니다.

* 앱스플라이어 SDK를 사용하여 업데이트된 앱을 릴리스하기 전에 모든 태스크를 완료합니다.
* 디바이스 ID 마이그레이션을 수행하기 전에 기존의 마케팅 캠페인을 일시정지합니다.

<div id="compare-measurement-between-appsflyer-and-other-mmps" />

### 앱스플라이어와 애드저스트 간의 측정 비교

다른 MMP 에서 앱스플라이어 로 이전을 고려할 때 광고주는 동일한 미디어 소스 와 캠페인에 걸쳐 두 MMP 기여도 측정 방식을 비교해 보는 것이 좋습니다. 그러나 모든 미디어소스가 두 개 이상의 MMP를 사용한 측정을 지원하는 것은 아닙니다.   그러한 방식은 출처 불일치를 방지하기 위해 특정 제한 사항과 어려움을 수반할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/measuring-attribution-with-multiple-mmps">여러 MMP의 어트리뷰션 측정</Anchor>에서 자세한 내용을 살펴보세요.

<div id="tasks" />

## 작업

다음 표는 각 과제에 필요한 작업의 범위를 설명합니다. 전반적인 작업 내용을 자세히 확인하고 진행 상황을 기록하려면 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQqbJIkE7kD87uSm7MH7zfkPN1VLuBaeotTEHAID2pYFVWM_LuQIA2AE2-8fVnXH-DrbXUQCs2iaiDe/pub?output=xlsx">이 스프레드시트를</Anchor> 다운로드.

<div id="scope-of-work" />

#### 작업 범위

<table><thead><tr><th>작업</th><th>필요한 조치</th><th>담당자</th><th>예상 시간</th><th>비고</th></tr></thead><tbody><tr><td>필수 조건</td><td><ol><li> <a href="https://www.appsflyer.com/get-started" target="_blank">앱스플라이어 계정을 만듭니다</a>.</li><li> 앱스플라이어에 <a href="./adding-an-app-to-appsflyer" target="_blank">앱을 추가합니다</a>.</li><li>[선택사항] 활동적인 사용자 정의와 <a href="./set-up-re-attribution-window" target="_blank">맞추기 위해 기본 90일 <span>리어트리뷰션 기간</span>을 변경하십시오.</a> </li></ol></td><td>마케터/앱스플라이어 대시보드 사용자</td><td>2시간</td><td> </td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#sdk-integration">SDK 통합</a></td><td><ul><li>앱에 앱스플라이어 SDK를 연동합니다.</li><li>S2S 또는 SDK 인앱이벤트를 매핑합니다.</li><li>앱 스토어에서 앱 버전을 갱신합니다.</li></ul></td><td>앱 개발자</td><td>1&#126;2주</td><td><ul><li> <strong>권장 사항</strong>: 권장사항: 테스트를 위해 사전 프로덕션 앱에 앱스플라이어 SDK를 통합하십시오.</li><li>다른 모든 과제가 완료된 후에 앱 스토어에서 프로덕션 앱을 업데이트해야 합니다.</li></ul></td></tr><tr><td> <a href="./migration-to-appsflyer-from-other-vendors#device-migration%E2%80%94optional">디바이스 마이그레이션</a> [선택사항]</td><td>기존 사용자의 이중 어트리뷰션을 피하기 위해 디바이스 ID를 마이그레이션합니다.</td><td>데이터 엔지니어</td><td>1&#126;2주</td><td rowspan="2"><ul><li>마이그레이션 전에 기존 캠페인을 일시정지하고 앱 버전이 업데이트된 후에 재개하는 것을 고려하십시오. </li><li>완전한 적용 범위를 보장하기 위해 최종 마이그레이션 날짜에 디바이스 마이그레이션을 반복하십시오.  </li></ul></td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#campaign-migration">캠페인 데이터 마이그레이션</a></td><td><ul><li>광고 네트워크를 앱스플라이어에 연동하기</li><li>다음에 존재하는 기존 캠페인을 마이그레이션합니다. <ul><li>SRNs</li><li>비-SRN 애드 네트워크</li><li>소유 매체</li></ul></li></ul></td><td>마케터/UA 관리자</td><td>1&#126;3주</td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#data-report-setup">데이터 리포트 설정</a></td><td><ul><li>현재 리포트 구조를 앱스플라이어 구조로 적용/매핑합니다.</li><li>앱스플라이어 리포트를 받을 준비를 합니다.</li></ul></td><td>데이터 엔지니어</td><td>2&#126;4주</td><td> </td></tr></tbody></table>

<div id="sdk-integration" />

### SDK 통합

<div id="sdk-integration::c763138b" />

<Accordion title="SDK 통합">

앱에 연동된 앱스플라이어 SDK는 앱과 앱스플라이어 플랫폼 간의 링크입니다. 앱 인스톨, 앱 열기, 인앱이벤트 등을 리포트합니다.

**앱스플라이어 SDK 연동 방법**:

1. 앱에 앱스플라이어 SDK를 연동합니다.  
   <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">안드로이드</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">iOS</Anchor> SDK 연동에 대해서는 안내서를 참조하십시오.
2. 앱스플라이어 스킴을 사용하여 기록하려는 인앱 이벤트를 매핑합니다.  
   이것은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">SDK</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>를 통해 수행할 수 있습니다.
3. 경쟁하는 어트리뷰션 공급업체의 SDK를 제거하십시오.  
   이 작업을 즉시 수행하여 앱스플라이어로 전환하거나, 몇 주 동안 SDK를 동시에 실행할 수 있습니다. 아래 표에서 옵션에 대한 분석을 확인하세요.

| 옵션 | 업데이트된 앱 버전 출시 후   <br />변경되는 사항 | 영향 |
| --- | --- | --- |
| 타 업체 SDK 제거 (권장) | 앱스플라이어만이 신규 설치 및 업데이트 사용자를 기록합니다.  <br />사용자가 앱을 업데이트 할 때까지 기존 버전의 이벤트를 타 업체가 여전히 표시합니다. | <ul><li>빠른 전환.</li><li>이중 어트리뷰션 없음.</li></ul> |
| 변환 기간 동안 타 업체 SDK 유지 | 앱스플라이어와 타 업체가 모두 신규 앱 설치를 어트리뷰션하고, 이벤트를 리포트합니다. 나중에 타 업체의 SDK를 제거합니다. | <ul><li>데이터 유효성 검증 가능. 즉, 앱스플라이어와 다른 공급업체의 데이터를 비교할 수 있습니다.</li><li>애드 네트워크에 이중 비용을 발생시킬 수 있는 이중 어트리뷰션. 다음의 예시 참고.</li><li>업무량 증가.</li></ul> |

4. 작업 범위에 있는 다른 모든 작업이 완료된 후, 앱스플라이어 SDK를 사용하여 앱 버전을 시장에 업데이트합니다. 신규 사용자는 앱스플라이어에 의해 어트리뷰션됩니다.   
   **참고**:
   * iOS, 구글 플레이, 그리고 모든 관련 안드로이드 아웃스토어 마켓에 사용할 앱을 업데이트해야 합니다.
   * 안드로이드 앱이 비공식 APK 사이트에 존재할 수도 있습니다. 웹에서 앱의 패키지 이름을 검색하여 확인하십시오.  APK 사이트는 최신 버전으로 업데이트할 때까지 다소 시간이 걸리므로, 앱스플라이어 SDK가 없는 구 버전을 인스톨하는 오가닉 유저가 유입될 수 있습니다.
   * 앱스토어에서 앱 업데이트가 완전히 반영되기까지 며칠이 걸릴 수도 있습니다. 이 기간 동안에 앱을 설치한 사용자에게는 이전 버전이 계속 제공될 수 있습니다.

</Accordion>

<div id="device-migrationoptional" />

### 디바이스 마이그레이션-선택사항

<div id="about-device-migration" />

<Accordion title="디바이스 마이그레이션 소개">

디바이스 마이그레이션은 기존 사용자 디바이스 ID(IDFA, IDFV, GAID, CUID)의 목록을 앱스플라이어로 업로드하는 프로세스입니다. 이 프로세스는 앱스플라이어 SDK를 포함하는 새 앱 버전을 출시하기 전에 수행해야 합니다. [디바이스 마이그레이션에는 두 가지 옵션,](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) [어트리뷰트 마이그레이션 또는 어트리뷰트되지 않은 마이그레이션이 있습니다.](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration)

디바이스 마이그레이션은 앱을 다운로드하고 이전 벤더에 의해 어트리뷰트된 기존 앱 사용자와 관련된 데이터 문제를 해결합니다. 예를 들어, 사용자가 원래 이전 벤더에서 SRN에 어트리뷰트되고 아직 기여 기간 내에 있는 경우 발생하는 SRN 이중 요금은 앱스플라이어에서 SRN에 의해 다시 청구되는 것입니다.

<div id="example" />

> 📄 **예시**
>
> * 6월 15일에 신규 사용자가 페이스북 앱에서 광고를 클릭하고 사용자의 앱을 설치했습니다.
> * 6월 24일에 사용자는 앱을 앱스플라이어 SDK 연동 버전으로 업데이트하고 실행했습니다. 앱스플라이어 측면에서 이 사용자는 실시간 어트리뷰션해야 하는 신규 사용자입니다.
> * 앱스플라이어는 사용자의 디바이스 ID로 메타 광고에 쿼리합니다. 사용자가 여전히 메타 광고의 28일 기여 기간 이내에 있기 때문에, 메타 광고는 해당 사용자를 셀프 어트리뷰션합니다. 이로 인해, 동일한 사용자에 대해 앱 소유주는 이중 부과됩니다.

디바이스를 마이그레이션하면 데이터는 앱스플라이어에서 다음과 같이 반영됩니다.

* **인스톨** **데이터:** 인스톨 데이터: <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window#reinstall">재인스톨</Anchor>과 유사하게, 마이그레이션된 디바이스는 인스톨 데이터를 갖지 않습니다. 마이그레이션된 디바이스 인스톨은 앱스플라이어에 표시되지 않습니다.
* **인앱 이벤트 및 세션 데이터:** 인앱 이벤트 및 세션 데이터: [어트리뷰션되지 않은 마이그레이션 방법](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration)의 경우, 오가닉으로 기록되고 표시됩니다. [어트리뷰션된 마이그레이션 방법](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration)을 사용하면, 해당 미디어소스와 캠페인에 어트리뷰션 됩니다.
* **리타겟팅:** 리타겟팅: 리어트리뷰션과 리인게이지먼트는 정상적으로 표시됩니다.
* 액티비티 데이터 정상적으로 표시됩니다.
* **리텐션 및 코호트 데이터:** 마이그레이션된 장치에는 인스톨 기록이 없습니다. 이와 같이, 이들은 어떠한 코호트와도 관련되어 있지 않으며, 리텐션 및 코호트 리포트에는 표시될 수 없습니다.

<div id="note" />

> 📘 **참고**
>
> 마이그레이션 날짜로부터 180일 이내에 앱을 실행하지 않으면 마이그레이션된 기기 데이터가 모두 삭제됩니다. 따라서 180일 이후에 앱을 실행하면 새로운 인스톨 로 기록됩니다.

</Accordion>

<div id="how-to-migrate-devices" />

<Accordion title="디바이스 마이그레이션 방법">

**디바이스를 마이그레이션하는 방법:**

1. 마이그레이션할 사용자 그룹을 결정합니다. 기존 사용자를 모두 마이그레이션할 수 있지만, 이 경우 앱스플라이어 에서 정확한 재 어트리뷰션 데이터 얻지 못할 수 있습니다. 또는 최근에 앱을 설치된 사용자만 마이그레이션할 수도 있습니다. 이 경우 기존 사용자에게 이중 요금이 부과될 수 있습니다.  
   **현재 재 1. 기간 2. 창 기간 동안 활동 중인 사용자를 마이그레이션하는 것을 권장합니다. 예를 들어 앱에 90일 리어트리뷰션 기간이 있는 경우 이전 90일 동안 세션이 하나 이상 있는 사용자를 마이그레이션합니다.**
2. [선택사항] 마케터/UA 관리자에게 디바이스 마이그레이션이 끝날 때까지 기존 마케팅 캠페인(SRN, 비-SRN 광고 네트워크, 온드 미디어 등)을 일시정지하도록 알리십시오.  
   캠페인을 일시정지하지 않기로 결정한 경우, 앱스플라이어 SDK를 사용하여 업데이트된 앱 버전이 앱 스토어에 릴리스되는 즉시 다른 벤더의 나머지 디바이스 ID를 마이그레이션합니다.
3. [어트리뷰트된](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) 또는 [어트리뷰트되지 않은](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration) 마이그레이션 구조를 사용하여 선택한 사용자 채우기를 기반으로 CSV 파일을 준비하십시오. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">샘플 CSV 참조</Anchor>
4. 앱스플라이어 CSM을 CSV로 전송하십시오.  
   사용자의 CSM은 디바이스 ID를 앱스플라이어로 마이그레이션합니다.

</Accordion>

<div id="attributed-migration" />

<Accordion title="어트리뷰트된 마이그레이션">

이 방법을 사용하여 앱스플라이어로 마이그레이션된 디바이스에는 인앱 이벤트가 있으며, 이전 어트리뷰션 벤더에서 보고된 미디어소스에 따라, 그리고 광고 네트워크의 데이터 리텐션 정책에 따라 매체 소스에 따라 세션이 기록되고 표시됩니다.

<div id="attributed-device-migration-csv-structure" />

#### 어트리뷰트된 디바이스 마이그레이션 CSV 구조

| 열  <br />name | 설명 | 필수 | 예시 |
| --- | --- | --- | --- |
| app\_id | 앱스플라이어 대시보드에 표시되는 앱 ID | 예 | <ul><li>Android: com.great.app1</li><li>iOS: id123456789</li></ul> |
| 플랫폼 | 디바이스 플랫폼: ios 또는 안드로이드 | 예 | <ul><li>iOS</li><li>안드로이드</li></ul> |
| device\_id | <ul><li>안드로이드: gaid, android\_id,</li><li>iOS: iOS: IDFV(사용 가능한 경우 권장됨) 또는 IDFA</li><li>다중 행에서 디바이스 ID 및 앱 ID의 동일한 조합을 복제하지 마십시오. 중복이 발생하면 파일의 마지막 발생이 사용됩니다.</li></ul> | 예 | <ul><li>**gaid** (소문자): 9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**android\_id** (소문자): f35aea8908254891</li><li>**IDFV** (대문자) A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA** (대문자) 9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android<ul><li>광고주 ID</li><li>android\_id</li><li>amazon\_aid</li></ul></li><li>iOS:<ul><li>idfa</li><li>idfv</li></ul></li><li>현재 OAID, IMEI와 같은 다른 식별자는 지원되지 않습니다.<br />구글 플레이 외 다른 곳에서의 안드로이드 사용자의 경우, 어트리뷰션 되지 않은 마이그레이션을 사용하십시오.</li></ul>**참고**<br />`android_id` 앱스플라이어 SDK 는 기본적으로 해당 정보를 수집하지 않습니다. 사용하시는 경우`android_id` 식별자로 사용되는 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">해당 정보를 SDK 연동 시 반드시 수집</Anchor> 하십시오. | 예 | <ul><li>광고주 ID</li><li>android\_id</li><li>idfa</li><li>idfv</li><li>amazon\_aid (소문자): df07c7dc-cea7-4a89-b328-810ff5acb15d</li></ul> |
| 설치 시간 | <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor> UTC 형식 으로 기록된 원래 앱 설치 시간 :  <br />**yyyy-mm-ddTHH:MM:SS.SSS** | 아니요 | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>다음 중 하나:<ul><li>앱스플라이어 파트너 ID</li><li>사용자정의 미디어소스(파트너 ID일 수 없음).</li></ul></li><li>앱스플라이어에서 요구하는 파트너 ID 목록을 얻는 방법:<ul><li><Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">모든 관련 연동 파트너를 활성화합니다.</Anchor></li><li>모든 활성 연동 목록에 대해 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">활성 연동 API 가져오기</Anchor>를 실행합니다.</li><li>API의 **media\_source\_name** 을 CSV의 **media\_source** 값으로 사용합니다.</li><li>예외:<ul><li>Apple Search Ads의 경우 **Apple Search Ads**를 사용합니다.</li><li>Twitter의 경우 **twitter**를 사용합니다.</li></ul></li></ul></li><li>형식: 값은 대소문자를 구분합니다.</li></ul> | 예 | 논오가닉: facebook\_int, googleadwords\_int<br /><br />오가닉: 오가닉 |
| integrated\_partner | <ul><li>미디어 소스가 연동된 파트너인지 아닌지 표시합니다. 오가닉인지 또는 사용자정의 미디어소스인지를 의미합니다.</li><li>형식: 값은 대소문자를 구분합니다.</li></ul> | 예 | <ul><li>네</li><li>아니요(media\_source가 커스텀인 경우)</li></ul> |
| campaign | 더 세부적인 어트리뷰션 상세 내역을 위해, 원래의 캠페인 이름을 제공하십시오.<br /><br />형식: 문자열 | 아니요 |  |
| campaign\_id | 더 세부적인 어트리뷰션 상세 내역을 위해, 원래의 캠페인 ID를 제공하십시오.<br /><br />형식: 공백이 허용되지 않는 문자열 | 아니요 |  |

**CSV 파일 규칙:**

* CSV 파일에는 여러 앱의 사용자 디바이스가 포함될 수 있습니다.
* 다중 행에서 디바이스 ID 및 앱 ID의 동일한 조합을 복제하지 마십시오. 중복이 발생하면 파일의 마지막 발생이 사용됩니다.
* 모든 컬럼 헤더 app\_id, platform, device\_id, id\_type, install\_time, media\_source, integrated\_partner, campaign, campaign\_id가 포함되어야 합니다. **참고**: 참고 : 필드의 순서는 중요하며 유지해야 합니다.
* 동일한 디바이스에 IDFV및 IDFA를 둘 다 추가할 수 있지만 별도의 행에 있어야 합니다. 별도의 행에 있는 모든 필드는 device\_id를 제외하고 동일해야 합니다.
* 각 행은 쉼표로 구분된 정확히 9개의 필드를 포함해야 합니다.
* 필수가 아닌 필드는 비워두십시오(공백).
* 파일은 최대 2천만 개의 행을 포함할 수 있습니다.
* 파일이 여러 개 있는 경우 각 파일에 고유한 이름을 할당하십시오.
* UTF-8을 사용하여 데이터를 인코딩합니다.
* [선택사항] ZIP 또는 GZIP을 사용하여 파일을 압축하십시오.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=0&single=true&output=csv">샘플 CSV 참조</Anchor>

</Accordion>

<div id="nonattributed-migration" />

<Accordion title="어트리뷰션 되지 않은 마이그레이션">

이 방법을 통해 앱스플라이어에 마이그레이션된 디바이스는 오가닉 사용자로 기록됩니다(그러나 표시되지는 않습니다). 이들의 인앱 이벤트와 세션도 또한 오가닉으로 기록되고 표시됩니다.

<div id="non-attributed-device-migration-csv-file-structure" />

#### 어트리뷰션되지 않은 디바이스 마이그레이션 CSV 파일 구조

| 옵션 | 열 | 사용하는 상황 | 예시 |
| --- | --- | --- | --- |
| 1 | 앱 ID + IDFA/GAID | <ul><li>모든 안드로이드 사용자가 GAID 식별자를 가진 경우.</li><li>iOS 사용자만 있는 경우.</li></ul> | [![device_migration_file_option_1.png](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png)](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png) |
| 2 | 앱 ID + 디바이스 ID + 디바이스 ID 유형 | <ul><li>안드로이드 사용자의 일부가 IMEI 또는 안드로이드 ID는 가지고 있으나, GAID는 갖지 않은 경우. (구글 플레이 외 앱 마켓(out-of store)이나 안드로이드 버전 4.4.2 이하)</li><li>안드로이드 ID는 16진법 형식이 필요합니다.</li></ul>**참고**:<ul><li>**ID 유형** 열 advertiserId(amazon\_aid도 지원함), idfa, idfv, android\_id, imei에 대해 정확한 문자열을 사용하십시오.</li><li>android\_id 또는 imei를 사용하고 나중에 앱스플라이어가 더 나은 식별자를 수신하는 경우 새 어트리뷰션이 기록될 수 있습니다.</li><li>`android_id` 그리고`imei` 앱스플라이어 SDK 는 기본적으로 이러한 정보를 수집하지 않습니다. 이러한 식별자 중 하나를 사용하는 경우 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">SDK 연동 에서 해당 식별자를 수집</Anchor> 해야 합니다.</li></ul> | [![device_migration_file_option_2.png](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png)](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png) |

**CSV 파일 규칙:**

* CSV 파일에는 여러 앱의 사용자 디바이스가 포함될 수 있습니다.
* 각 행에는 앱당 단일 디바이스 ID가 포함됩니다.
* 선택한 파일 구조 옵션에 따라 파일 열은 다음과 같아야 합니다(나열된 순서대로).
  * Option 1: app\_id,device\_id
  * Option 2: app\_id,device\_id,id\_type
* 소문자로 된 앱 ID
* 소문자로 된 안드로이드 ID
* 대문자로 된 IDFA/IDFV
* 최대 2,500만 행 허용

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">샘플 CSV 참조</Anchor>

</Accordion>

<div id="campaign-migration" />

### 캠페인 데이터 마이그레이션

기존 마케팅 캠페인을 앱스플라이어로 전환하여 앱스플라이어 어트리뷰션을 활성화하고 중복 비용 및 어트리뷰션 데이터 손실을 방지합니다.

**참고**: 일러두기: 한 번에 몇 개의 마케팅 캠페인만 마이그레이션하도록 선택할 수 있습니다. 이 경우, 미디어소스(예: 광고 네트워크 또는 에이전시), 지역 또는 캠페인에 의해 마이그레이션하려는 항목을 세그먼트화할 수 있습니다.

<div id="srns" />

<Accordion title="SRNs">

SRN은 MMP(Mobile Measurement Partner)가 특정 디바이스의 인게이지먼트에 대해 쿼리하는 경우 응답합니다. 만약 두 개의 MMP(예를 들어 앱스플라이어와 다른 어트리뷰션 업체)가 동일한 디바이스의 인스톨에 대해 같은 SRN에 쿼리한 경우, 이중 비용을 발생시킬 수도 있습니다.

**SRN 캠페인을 마이그레이션하는 방법**:

* 앱스플라이어에서 관련 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#앱스플라이어와-통합된-srn">SRN</Anchor>을 활성화하고 설정하십시오.

<div id="note-1" />

> 📘 **참고**
>
> * SRN은 여러 MMP를 실행할 수 있습니다(메타 광고 및 트위터 제외).
> * 메타 광고는 인앱 이벤트의 중복을 제거할 수 없습니다.

</Accordion>

<div id="nonsrn-ad-networks" />

<Accordion title="비-SRN 애드 네트워크">

광고 네트워크 어트리뷰션 링크는 사용자 광고 참여를 기록하며, 이후에 실제 앱 설치가 되는 광고 참여를 어트리뷰션하는 데 사용됩니다.

**비-SRN 광고 네트워크 캠페인을 마이그레이션하는 방법**:

1. 앱스플라이어에서 관련 광고 네트워크를 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">활성화</Anchor>하십시오.
2. 각 광고 네트워크에 대해 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">앱스플라이어 어트리뷰션 링크를 생성합니다.</Anchor>
3. 각 캠페인의 기존 링크를 앱스플라이어 어트리뷰션 링크로 전환합니다.

</Accordion>

<div id="owned-media" />

<Accordion title="소유 매체">

온드 미디어는 사용자가 다음에서 사용하는 어트리뷰션 링크를 참조합니다.

* 콘텐츠 공유하기
* 웹 투 앱
* 이메일
* SMS
* 소셜 미디어 포스트
* 블로그
* 인터넷 커뮤니티(Quora 등)
* 그 외 다수 ...

앱스플라이어 이러한 캠페인에 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크 링크를</Anchor> 사용합니다. . 원링크 커스텀 링크는 디바이스에 기반한 사용자를 올바른 앱스토어, 앱 또는 웹 URL/랜딩 페이지로 리디렉트합니다.

**현재 보유하고 있는 미디어 링크를 앱스플라이어 원링크 링크로 변경하려면 다음 단계를 따르세요** .

* 담당 고객 성공 관리자(CSM)에게 문의하시면 현재 사용 중인 채널 및 도구에 맞춰 소유 미디어 링크를 원링크 링크로 변환하는 데 도움을 받으실 수 있습니다.

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

SKAdNetwork(SKAN) 어트리뷰션의 경우, 변환 값은 SDK 하나만 업데이트할 수 있습니다. 그렇지 않으면, SKAN 데이터는 무의미하게 됩니다. 따라서 마이그레이션 후에 앱스플라이어 SDK만이 SKAN 변환 값을 업데이트합니다.

앱스플라이어에서 SKAN 전환 값 설정에 대해 자세히 알아봅니다.

</Accordion>

<div id="data-report-setup" />

### 데이터 리포트 설정

<div id="adapt-and-map-report-structures" />

<Accordion title="리포트 구조 적용 및 매핑">

시스템은 마이그레이션하기 전에 사용자가 설정한 리포트 구조, 필드 및 파라미터에 따라 현재 벤더의 어트리뷰션 데이터를 저장합니다. 앱스플라이어가 데이터를 올바르게 리포트하려면 현재 리포트 구조를 앱스플라이어 리포트 구조, 필드 및 파라미터에 적용하고 매핑해야 합니다.

**리포트 구조를 적용하고 매핑하는 방법:**

* 앱스플라이어 CSM에 문의하여 Adjust, Branch/Tune, 또는 Kochava에서 앱스플라이어로 리포트 데이터 구조를 빠르게 적용/마이그레이션하는 데 도움을 받으십시오.

</Accordion>

<div id="prepare-report-methods" />

<Accordion title="리포트 준비 방법">

여러 가지 방법을 사용하여 앱스플라이어에서 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-apis">원시</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/analytics-and-aggregate-reporting-apis">집약형</Anchor> 리포트 데이터를 가져올 수 있습니다. 방법을 숙지하고 관련된 사용자와 관련된 방법을 설정하십시오.

리포트 방법에는 다음이 포함됩니다.

* 대시보드
* 리포트 내보내기
* Push API
* Pull API
* 데이터 락커

</Accordion>
