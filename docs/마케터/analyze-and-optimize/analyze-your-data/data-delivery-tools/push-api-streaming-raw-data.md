---
title: Push API 스트리밍 로데이터
metadata:
  keywords:
    - Push API
    - Real-time
    - Installation and Conversion
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:19:42Z'
  edited_at: '2026-10-14T10:40:50Z'
  id: 207034356
  locale: ko
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/ko/articles/207034356
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 요약: 로데이터 어트리뷰션 이벤트를 서버 측 엔드포인트로 스트리밍합니다.

![6970_Push_API_image.png](https://files.readme.io/0bb5747a65a6ca6ed8f55f72f189b92e780649d55b766c5d295f5602745f04f5-4405028260241.png)

## Push API

Push API는 앱스플라이어 어트리뷰션 및 메시지로서의 SKAN(SKAdNetwork) 어트리뷰션으로 생성된 로데이터를 서버로 스트리밍합니다. 메시지 유형 및 콘텐츠를 선택하고 목적지 엔드포인트를 설정할 수 있습니다.

사용 가능한 메시지 유형, 데이터 신선도 및 필드는 다음 섹션에서 설명하는 어트리뷰션 프레임워크(앱스플라이어 또는 SKAN)에 따라 달라집니다.

<div id="appsflyer-attribution-messages" />

<Accordion title="앱스플라이어 어트리뷰션 메시지">

메시지 특성

| 특성 | 세부 정보 |
| --- | --- |
| 메시지 유형 구분 | <ul><li>메시지는 엔드포인트로 분리하거나(앱당 최대 6개 엔드포인트) 나열된 다음 필드 값을 검사하여 메시지 유형을 결정할 수 있습니다.<ul><li>event\_name</li><li>conversion\_type</li><li>캠페인 유형</li></ul></li><li>메시지 유형별 필드 값은 다음 표에 표시됩니다.</li></ul>**예시:**<br /><br />메시지에는 다음 사항이 포함됩니다.<ul><li>conversion\_type=인스톨</li><li>campaign\_type=organic</li><li>event\_name=인스톨</li></ul>표를 사용하여 이 이벤트가 오가닉 사용자의 인스톨 이벤트인지 확인합니다. |
| 데이터 최신성 | 앱스플라이어 플랫폼에 이벤트가 기록되는 즉시 메시지가 전송됩니다. 이 과정은 보통 1분 이내입니다. |
| 메시지 콘텐츠(필드) | <ul><li>메시지는 `key:value` 구조를 가집니다.</li><li>사용 가능한 앱스플라이어 속성 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#field-availability-by-reporting-tool">Push API</Anchor> 필드를 참조하십시오.</li><li>각 키는 로데이터 필드를 나타냅니다. <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#data-fields-dictionary">앱스플라이어의 로데이터 필드 설명</Anchor>을 참조하십시오.</li><li>공백 또는 null 키는 전송되지 않습니다.</li><li>이 예시에는 null 필드와 빈 필드를 모두 포함합니다. 실제 포스트백에는 비어 있지도 않고 null 필드도 없습니다. 제공된 예시는 JSON 형식입니다.<ul><li>[iOS](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=0&single=true&output=csv)</li><li>[안드로이드](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=233131974&single=true&output=csv)</li></ul></li></ul> |
| 타임 스탬프 필드 형식 | <ul><li>UTC 타임스탬프: `yyyy-mm-dd hh:mm:ss.sss`. 예를 들면, `2019-09-17 00:09:00.123`2019-09-17 00:09:00.123과 같이 표시됩니다. 이벤트가 도쿄 시간 18:00에 이루어졌습니다. UTC로 변환된 시간은 09:00입니다. 기록된 시간은 UTC 시간대 입니다.</li><li>선택한 시간대(앱 별) 타임스탬프: `yyyy-mm-dd hh:mm:ss.sss±th:tm`. 예를 들어: 이벤트가 도쿄 시간 18:00에 이루어졌습니다. 표시된 이벤트 시간은 18:00+09:00로 기록됩니다. 09:00은 도쿄 표준 시간대입니다.</li></ul> |

#### 사용 가능한 메시지 유형

<table><thead><tr><th>어트리뷰션 컨텍스트</th><th>메시지 유형</th><th>conversion_type 필드</th><th>campaign_type 필드</th><th>event_name 필드</th><th>event_type 필드</th></tr></thead><tbody><tr><td>유저 유입</td><td>인스톨\*</td><td>인스톨</td><td><p>논오가닉: UA</p><p>오가닉: 오가닉</p></td><td>인스톨</td><td><ul><li>인스톨</li><li>organic-install</li></ul></td></tr><tr><td>유저 유입 </td><td>install in-app events</td><td><span>인스톨</span></td><td><p>논오가닉: UA</p><p>오가닉: 오가닉</p></td><td>광고주가 정의한 이벤트 이름</td><td><ul><li>install-in-app-event</li><li>organic-install-in-app-event</li></ul></td></tr><tr><td>리타겟팅</td><td>리인게이지먼트</td><td>리인게이지먼트</td><td>리타겟팅</td><td>리인게이지먼트</td><td>리어트리뷰션</td></tr><tr><td>리타겟팅 </td><td>Re-engagement in-app events</td><td>리인게이지먼트</td><td>리타겟팅</td><td>광고주가 정의한 이벤트 이름</td><td>re-engagement-in-app-event</td></tr><tr><td>리타겟팅 </td><td>리어트리뷰션 </td><td>재설치 (Reinstall)</td><td>리타겟팅</td><td>리어트리뷰션</td><td>리어트리뷰션</td></tr><tr><td>유저 유입 </td><td>재설치</td><td>재설치 (Reinstall)</td><td><p>논오가닉: UA</p><p>오가닉: 오가닉</p></td><td>재설치 (Reinstall)</td><td><ul><li>재설치 (Reinstall)</li><li>organic-reinstall</li></ul></td></tr><tr><td>리타겟팅</td><td>Re-attribution in-app events</td><td>재설치 (Reinstall)</td><td>리타겟팅</td><td>광고주가 정의한 이벤트 이름</td><td>re-attribution-in-app-event</td></tr><tr><td colspan="6">광고 조회 어트리뷰션과 관련되는 일부 인스톨은 <a href="./about-raw-data-identifier-restrictions" target="_blank">제한된 미디어 소스</a>로 어트리뷰트됩니다. </td></tr></tbody></table>

#### 고유 필드

<table><thead><tr><th>표시 이름</th><th>Push API 이름</th></tr></thead><tbody><tr><td>선택된 통화\*</td><td>selected_currency</td></tr><tr><td>선택된 통화로 표시된 수익</td><td>revenue_in_selected_<br/>통화</td></tr><tr><td>선택된 통화로 표시된 비용</td><td>cost_in_selected_<br/>통화</td></tr><tr><td>선택된 시간대의 기기 다운로드 시간</td><td>device_download_time_selected_timezone</td></tr><tr><td>선택된 시간대의 어트리뷰트된 터치 시간</td><td>attributed_touch_time_selected_timezone</td></tr><tr><td>선택된 시간대의 인스톨 시간</td><td>install_time_selected_<br/>시간대</td></tr><tr><td>선택된 시간대의 이벤트 시간</td><td>event_time_selected_<br/>시간대</td></tr><tr><td>선택된 시간대(\*)</td><td>selected_timezone</td></tr><tr><td colspan="2">\* API 메시지가 전송될 때 적용되어 있는 앱 설정을 따릅니다.</td></tr></tbody></table>

</Accordion>

<div id="skan-attribution-messages" />

<Accordion title="SKAN 어트리뷰션 메시지">

이 섹션에서는 SKAN에 사용할 수 있는 메시지(리포트 유형)와 메시지를 식별하는 방법에 대해 설명합니다. 이 섹션을 읽은 다음 [SKAN 어트리뷰 엔드포인트 설정](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)을 읽으십시오.

관련 문서: SKAN 로데이터 필드 Push API 메시지는 동등한 구조 및 필드를 가집니다.

메시지 특성:

| 특성 | 세부 정보 |
| --- | --- |
| 메시지 유형 구분 | <ul><li>모든 메시지는 사용자가 설정한 1개의 엔드포인트로 전송됩니다.</li><li>메시지 유형을 결정하려면 event\_type 필드를 사용하십시오.<br />일러두기: event\_type 필드를 사용하여 event\_name 필드와 skad\_redownload 필드를 지정할 수도 있습니다.</li><li>event\_type 필드의 값은 다음의 [표에 표시됩니다](/docs/push-api-streaming-raw-data#skan-어트리뷰션에-대한-메시지-유형).</li></ul>예시:<br /><br />메시지에는 다음 사항이 포함됩니다.<ul><li>event\_type: skad-re-download</li></ul>이를 통해 다음을 확인할 수 있습니다.<ul><li>이것은 재다운로드 이벤트입니다.</li><li>event\_name: 인스톨</li><li>skad\_redownload: true</li></ul> |
| 데이터 최신성 | <ul><li>인스톨, 재다운로드 및 인앱 이벤트:<ul><li>매일 처리됨</li><li>앱스플라이어에서 iOS 포스트백을 받은 다음 날 엔드포인트로 전송됩니다</li><li>이벤트 메시지는 05:00–08:00 UTC에 받을 것으로 예상됩니다(정확한 시간은 변동됩니다)</li><li>예시: 예시: 월요일에 받은 포스트백은 화요일 05:00 UTC부터 시작하여 전송됩니다</li></ul></li><li>iOS의 포스트백 및 포스트백 사본: 메시지는 앱스플라이어에 도착한 직후에 전송됩니다.</li></ul> |
| 메시지 예시 | 스프레드시트에는 메시지 예시가 포함되어 있습니다. 제공된 예시는 JSON 형식입니다. SKAN 예시 메시지. |

#### SKAN 어트리뷰션에 대한 메시지 유형

| 메시지 유형 | event\_name 필드 | skad\_redownload 필드 | event\_type 필드 |
| --- | --- | --- | --- |
| 인스톨 | 인스톨 | <ul><li>가질 수 있는 값: false, blank, null.</li><li>필드가 메시지에 없으면 값을 false로 간주합니다.</li></ul> | skad-install |
| 다시 다운로드 | 인스톨 | True | skad-re-downloads |
| 인앱 이벤트 | 광고주가 설정한 이벤트 이름 | 광고주가 설정한 이벤트 이름 | skad-in-app-event |
| iOS의 포스트백 | 이 메시지에서는 사용할 수 없습니다 | 이따금 사용 가능합니다 | skad\_postback |
| <Anchor target="_blank" href="/marketers/ko/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">포스트백 복사</Anchor> | 이 메시지에서는 사용할 수 없습니다 | 이따금 사용 가능합니다 | skad-postback-copy |

</Accordion>

## Push API 엔드포인트 설정하기

> ❗️ **주의**
>
> 다음과 같은 이유로 앱스플라이어 어트리뷰트 데이터를 타사에 전송할 때 Push API를 사용하지 마십시오.
>
> * 사용자가 자신의 데이터를 타사에 보내지 않기로 선택한 경우 CCPA와 같은 프라이버시 규정의 위반으로 될 수 있습니다.
> * 일부 미디어소스는 해당 미디어소스가 제공하는 사용자 수준 데이터의 사용, 제3자 공유 또는 둘 다를 제한합니다. 미디어 소스의 사용 약관을 준수하십시오.
>   예를 들어 [X 광고,](https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html) [스냅챗,](https://www.snap.com/en-US/privacy/privacy-policy/) [핀터레스트.](https://policy.pinterest.com/en/privacy-policy)
>
> 참고:  일러두기: 이 주의사항은 SKAN 데이터에는 적용되지 않습니다. Push API를 사용하여 SKAN 데이터를 타사 엔드포인트로 전송합니다.

Push API를 설정하려면 다음 작업 목록을 완료하십시오.

#### Push API 설정 체크리스트

<table><thead><tr><th>단계 번호  </th><th>Appsflyer 어트리뷰션</th><th>SKAdNetwork 어트리뷰션:  </th></tr></thead><tbody><tr><td>1</td><td colspan="2"><p>활성 Push API 엔드포인트가 이미 있는 경우 이 단계를 건너뛸 수 있습니다.  </p><p><a href="./push-api-streaming-raw-data#serverside-requirements-your-server">서버 측 필요 사항</a>을 완료하십시오.</p></td></tr><tr><td>2</td><td>앱스플라이어 어트리뷰션의 경우 <a href="./push-api-streaming-raw-data#push-api-planning-checklist-for-appsflyer-attribution">Push API 계획 체크리스트</a>를 사용하여 엔드포인트 설정을 계획합니다. </td><td>적용 불가</td></tr><tr><td>3</td><td><a href="./push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">앱스플라이어 어트리뷰션 엔드포인트 설정하기</a></td><td><a href="./push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint">SKAdNetwork 어트리뷰션 엔드포인트 설정하기</a></td></tr></tbody></table>

<div id="serverside-requirements-your-server" />

<Accordion title="서버 측 필요 사항 (앱 개발사 서버)">

서버가 다음 요구 사항을 준수하는지 확인하십시오.

#### 서버 측 필요 사항

| 엔드포인트 URL | <ul><li>유효한 도메인 이름</li><li>앱당 최대 고유 엔드포인트 수:<ul><li>앱스플라이어: 6개의 엔드포인트</li><li>SKAdNetwork 3개의 엔드포인트</li></ul></li></ul> |
| --- | --- |
| 엔드포인트 리턴 코드 | 엔드포인트는 메시지를 수신하면 반드시 HTTP 200 상태 코드를 반환해야만 합니다. |
| 앱스플라이어 서버 등록 | 방화벽 및 보안 시스템에 앱스플라이어 서버 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-server-ip-address-ranges-allowlisting">IP 주소</Anchor>를 등록하여 엔드포인트와의 통신을 보장합니다. |
| TLS 버전 | <ul><li>TLS 1.1</li><li>TLS 1.2 이상 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-https-ssl-encryption-policy-support#outgoing-messages-appsflyer-as-client">지원되는 암호</Anchor> 참조</li></ul> |
| 포트 | 포트 80, 443 |

**참고**! 2초간 지속되는 시간 제한 메커니즘이 사용됩니다. 앱스플라이어가 이 시간 동안 OK 메시지를 받지 못한다면 앱스플라이어는 메시지 전송 실패로 간주합니다.

</Accordion>

<div id="push-api-planning-checklist-for-appsflyer-attribution" />

<Accordion title="앱스플라이어 어트리뷰선에 대한 Push API 계획 체크리스트">

* 이 체크리스트를 사용하여 앱스플라이어 어트리뷰션 엔드포인트 설정을 계획합니다. 그림 속의 숫자는 체크리스트의 행 번호와 같습니다.
* 이 섹션은 SKAdNetwork 어트리뷰션과 관련이 없습니다. [SKAdNetwork 어트리뷰션 설정](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)을 참고하십시오.

**엔드포인트**

[![PushAPI_us-en.png](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)

#### 엔드포인트 계획 체크리스트

| 아니오. | 설정 | 세부 정보 | 이 열에 계획한 설정을 기록합니다 |
| --- | --- | --- | --- |
| 1 | 방법 | POST 또는 GET |  |
| 2 | 엔드포인트 URL | - |  |
| 3 | 이벤트 메시지 유형 | <ul><li>적어도 하나의 이벤트 메시지 유형을 선택하십시오.</li><li>인앱 이벤트 메시지를 선택하려면, 인앱 이벤트를 기록해야 합니다. 그렇게 할 때까지는 인앱 이벤트 메시지를 선택할 수 없습니다.</li></ul>[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png) |  |
| 4 | <ul><li>필드</li><li>필드 목록은 모든 메시지 유형에 공통입니다.</li></ul> | **<span id="01H8E8DET2PBGQAKHJY40R1P9Z"></span>경고**<br />모두 선택하더라도 미래에 추가되는 메시지 필드는 자동으로 포함되지 않습니다. 새 필드를 포함하려면 선택을 수동으로 업데이트해야 합니다.<br /><br /><br /><br />필요한 필드를 선택하십시오.<ul><li>가장 일반적인 필드는 기본적으로 미리 선택되어 있습니다.</li><li>비어 있는 필드/null 필드는 전송하지 않습니다</li></ul> |  |
| 5 | 인앱 이벤트 유형 | 인앱 이벤트 기준으로 필터링하여 엔드포인트로 전송되는 트래픽을 줄입니다.<ul><li>하나 또는 여러개, 또는 모든 인앱 이벤트를 선택합니다. 참고! 만약 이벤트가 목록에 표시되지 않는다면, 검색하십시오.</li><li>인앱 이벤트는 한 번 이상 기록된 후에만 선택할 수 있습니다.  필요한 경우 <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>를 사용하여 이벤트를 실행하십시오.</li><li>[![mceclip1.png](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)</li></ul> |  |

</Accordion>

<div id="set-up-appsflyer-attribution-endpoint" />

<Accordion title="앱스플라이어 어트리뷰션 엔드포인트 설정하기">

API에 접근할 수 있는 권한이 있는 모든 팀원은 Push API 설정을 변경할 수 있습니다. 다른 계정 사용자는 설정을 볼 수만 있습니다.

#### 앱스플라이어 어트리뷰션 엔드포인트 추가 방법:

1. AppsFlyer에서 사이드바에서 **내보내기 > API 접근을 엽니다. Push API 섹션까지 아래로 스크롤합니다.**
2. **엔드포인트 추가 버튼을 클릭합니다.**
3. HTTP 메서드를 선택합니다: POST 또는 GET
4. **엔드포인트 URL**을 입력합니다.  이 URL이 안전하지 않음 메시지가 표시되면 앱스플라이어 지원팀에 문의하십시오.
5. 하나 이상의 이벤트 유형을 선택합니다. **참고**: 일러두기: 인앱 이벤트 메시지가 비활성화 상태라면 지금까지 인앱 이벤트가 기록되지 않았다는 것입니다.
6. 푸시 API 메시지에 포함될 필드를 선택합니다. 참고:
   * 항상 전송되는 필수 입력 필드: 앱 ID, 이벤트 이름, 이벤트 시간, IDFA (iOS) 또는 광고 ID (안드로이드)
   * 다음 그림에 표시된 컨트롤을 사용하여 선택적 필드를 선택하십시오. [![PushAPIFieldSelect1.jpg](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)
     * 가장 일반적인 필드는 기본적으로 미리 선택되어 있습니다. 선택은 취소할 수 있습니다.
     * 필요에 따라 옵션 필드를 선택하십시오.
     * 모든 옵션 필드를 삭제하려면 **모두 지우기**를 클릭하십시오.
     * 비어 있는 필드/null 필드와 이 필드에 연결된 키는 전송하지 않습니다. 임포트/파싱 절차를 계획할 때, 이 점을 고려하십시오.
7. 인앱 이벤트를 하나 또는 여러개 (최대 52개 이벤트) 선택하거나, **모두 선택** 합니다.
   * 목록은 이미 기록된 적이 있는 이벤트 유형들로 이루어져 있습니다. 이벤트가 누락된 경우, 테스트 기기를 사용하여 이 유형의 이벤트를 보내십시오.
8. **저장**을 클릭하세요.  
   Push API가 지금 활성화되었습니다. 전환 데이터가 엔드포인트로 전송됩니다.
9. 아래 설명된 절차를 통해 엔드포인트를 테스트 합니다.

#### 엔드포인트를 테스트하려면:

1. **테스트 전송을 클릭합니다.**   
   테스트 전송 메시지가 **테스트 전송** 버튼 아래에 표시됩니다.   
    테스트 메시지가 엔드포인트로 전송됩니다. 테스트에 실패하는 경우 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-server-ip-address-ranges-allowlisting">앱스플라이어 IP 주소가 등록</Anchor>되었는지 확인하십시오.    
   **참고**! 2초간 지속되는 시간 제한 메커니즘이 사용됩니다. 앱스플라이어가 이 시간 동안 OK 메시지를 받지 못한다면 앱스플라이어는 메시지 전송 실패로 간주합니다.
2. 엔드포인트가 테스트 메시지를 수신했는지 검증합니다.  
   [전송된 메시지 복사본은 다음과 같습니다.](https://docs.google.com/spreadsheets/d/e/2PACX-1vScQf189h3Ry0BU-ejbZYkMZCJRdXXYeOwuNxPEHwY77vCVYWW9P9xCTUSJKmTvVbp_yzLidXD0WGLm/pub?gid=0&single=true&output=csv)

</Accordion>

<div id="set-up-skadnetwork-attribution-endpoint" />

<Accordion title="SKAdNetwork 어트리뷰션 엔드포인트 설정하기">

API에 접근할 수 있는 권한이 있는 모든 팀원은 Push API 설정을 변경할 수 있습니다. 다른 계정 사용자는 설정을 볼 수만 있습니다.

**SKAdNetwork Push API 엔드포인트를 추가하는 방법:**

1. AppsFlyer에서 사이드바에서 **내보내기 > API 접근을 엽니다. Push API 섹션까지 아래로 스크롤합니다.**
2. **SKAdNetwork**를 어트리뷰트 엔터티로 선택합니다.
3. **엔드포인트 추가 버튼을 클릭합니다.**   
   **참고**: 앱당 SKAdNetwork 엔드포인트 1-3개를 정의할 수 있습니다.
4. HTTP 메서드를 선택합니다: POST 또는 GET
5. **엔드포인트 URL**을 입력합니다.  이 URL이 안전하지 않음 메시지가 표시되면 앱스플라이어 지원팀에 문의하십시오.
6. 비어 있는 필드/null 필드와 이 필드에 연결된 키는 전송하지 않습니다. 임포트/파싱 절차를 계획할 때, 이 점을 고려하십시오.
7. **저장**을 클릭하세요.  
   Push API가 지금 활성화되었습니다. 데이터가 엔드포인트로 전송됩니다.

</Accordion>

<div id="configure-authentication-token" />

<Accordion title="인증 토큰 설정">

고객은 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_tokens-app-app-id">푸시 API 인증 토큰을</Anchor> 사용하여 요청된 토큰을 포함한 사용자 정의 가능한 인증 헤더를 추가하여 푸시 API 메시지를 원활하게 통합하고 보안할 수 있습니다.  
각 앱 ID에 연결된 토큰 이름과 값을 정의하여 푸시 API 메시지와 함께 전송될 인증 헤더를 사용자 정의할 수 있습니다. 이를 통해 메시지는 안전할 뿐만 아니라 사용자의 특정 요구사항에 맞게도 조정됩니다.

</Accordion>

## 추가 절차—엔드포인트 관리

API에 접근할 수 있는 권한이 있는 모든 팀원은 Push API 설정을 변경할 수 있습니다. 다른 계정 사용자는 설정을 볼 수만 있습니다.

<div id="change-an-endpoint" />

<Accordion title="엔드포인트 변경">

**엔드포인트 설정 수정 방법:**

1. AppsFlyer에서 사이드바에서 **내보내기 > API 접근을 엽니다. Push API 섹션까지 아래로 스크롤합니다.**
2. 수정할 엔드포인트를 찾습니다.
3. 수정합니다.
4. **저장**을 클릭합니다.

</Accordion>

<div id="delete-an-endpoint" />

<Accordion title="엔드포인트 삭제">

**엔드포인트를 삭제하려면**:

1. AppsFlyer에서 사이드바에서 **내보내기 > API 접근을 엽니다. Push API 액세스 섹션까지 아래로 스크롤합니다.**
2. **엔드포인트 삭제**를 클릭합니다.
3. **저장**을 클릭하세요.  
   엔드포인트가 삭제되었습니다.

</Accordion>

## 문제 해결, 특성 및 제한 사항

<div id="test-message-fails" />

<Accordion title="테스트 메시지 실패">

테스트 메시지를 받지 못하고 IP 주소별로 서버에 대한 액세스를 제한하는 경우 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-server-ip-address-ranges-allowlisting">앱스플라이어 IP 주소를 모두 등록</Anchor>했는지 확인하십시오.

</Accordion>

<div id="duplicate-retargeting-inapp-events" />

<Accordion title="중복된 리타겟팅 인앱 이벤트">

유저 유입(UA) 리인게이지먼트 윈도우 내에, 리타겟팅 캠페인의 영향으로 구매 이벤트가 일어나는 경우, 리타겟팅 인앱 이벤트는 중복 기록됩니다. 이는 UA 미디어 소스와 리타겟팅 미디어 소스 모두에 수익을 어트리뷰션 하기위해 이루어집니다.

아래 둘 다 활성화한 경우에만 중복 이벤트를 얻을 수 있습니다.

* install in-app events
* 리타게팅 인앱 이벤트

<Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">인앱 이벤트 식별 및 중복 제거</Anchor>

</Accordion>

<div id="inapp-event-message-selection-is-disabled" />

<Accordion title="인앱 이벤트 메시지 선택란이 비활성화 상태입니다.">

[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)

* 인앱 이벤트 메시지는 최소 하나의 인앱 이벤트가 기록된 후에만 선택할 수 있습니다.
* 테스트 기기를 사용하여 인앱 이벤트를 생성하거나, <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API</Anchor> 를 사용하여 수동으로 이벤트를 생성하십시오.

</Accordion>

<div id="missing-push-messages-and-cloudfront" />

<Accordion title="누락된 푸시 메시지와 CloudFront">

엔드포인트로 아마존 CloudFront를 사용하고 있습니까? 그렇다면, CloudFront가 거부 코드 421를 가진 메시지를 거부하고 있는지 확인하십시오. 이 경우  <Anchor target="_blank" href="https://docs.aws.amazon.com/en_pv/AmazonCloudFront/latest/DeveloperGuide/cnames-https-dedicated-ip-or-sni.html">CloudFront에서 HTTPS 요청을 처리하는 방법 선택</Anchor> 안내를 참고하십시오.

</Accordion>

<div id="endpoint-error-messages" />

<Accordion title="엔드포인트 오류 메시지">

**증상:** 증상: 엔드포인트 URL을 설정할 때 *이 URL이 안전하지 않음* 메시지가 표시됩니다.

**필요한 조치**: 필요한 조치: 앱스플라이어 지원팀에 문의하십시오. 이때 앱 ID, 엔드포인트 URL 및 오류 메시지의 스크린샷을 제공하십시오.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="특징 및 제약 사항">

| **특징** | 비고 |
| --- | --- |
| <span id="ad-networks"></span>애드 네트워크 | 사용 불가 |
| <span id="agencies"></span>대행사 | 사용 불가 |
| <span id="appspecific-time-zone"></span>앱별 시간대 | 지원됨. |
| <span id="appspecific-currency"></span>앱별 통화 | 지원됨. |
| <span id="size-limitations"></span>사이즈 제한 | 적용 불가 |
| <span id="organic"></span>오가닉 | 예 |
| <span id="nonorganic"></span>논오가닉 | 예 |
| <span id="data-freshness"></span>데이터 최신성 | 연속 |
| <span id="historical-data"></span>과거 데이터 | 지원되지 않습니다. 데이터가 누락된 경우에는 Pull API를 사용하여 데이터를 가져오십시오. SKAN의 경우에는 데이터 락커를 통해 기록 데이터를 얻을 수 있습니다(데이터 락커 가용성 기간으로 제한됨). |
| <span id="account-owneruser-access"></span>계정 소유자/사용자 액세스 | 앱스플라이어 **계정 소유자**만 푸시 API 설정을 변경할 수 있습니다.<ul><li>각 앱스플라이어 계정에는 **한 명의** 계정 소유자만 있습니다. 이것은 첫 번째 앱스플라이어 사용자입니다(계정이 개설될 때 생성됨) .</li></ul>다른 계정 사용자는 Push API 설정을 볼 수는 있지만, 변경할 수 없습니다. |
| <span id="authentication-token-in-test-messages"></span>테스트 메시지의 인증 토큰 | [테스트 메시지](#엔드포인트를-테스트하려면) 헤더에는 인증 토큰이 포함되지 않습니다. |

</Accordion>

<div id="can-i-include-custom-headers-with-the-push-api-request" />

<Accordion title="푸시 API 요청에 커스텀 헤더를 포함할 수 있습니까?">

아니오. 푸시 API는 인증 토큰에 대해서만 `Authorization` 헤더를 사용하도록 지원합니다. `consumer-key`과 같은 추가 사용자 지정 헤더는 **지원되지 않습니다**.

추가 파라미터를 전달해야 한다면, 파라미터를 URL에 포함하세요. 예시:

```
https://your.server.com?consumer_key=abc456
```

</Accordion>

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">로데이터 전달 도구 비교</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_app-app-id">API를 사용하여 Push API 설정</Anchor>

<div data-zendesk-anchors="01H89PJFBPXVKJGGH18CJBJ41W=push-api 01H89PJFBP45FQDHT4YGS58NP8=appsflyer-attribution-messages available-message-types=%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EB%A9%94%EC%8B%9C%EC%A7%80-%EC%9C%A0%ED%98%95 01H89PJFBP9DEX520BDGC5PANQ=%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EB%A9%94%EC%8B%9C%EC%A7%80-%EC%9C%A0%ED%98%95 unique-fields=%EA%B3%A0%EC%9C%A0-%ED%95%84%EB%93%9C 01H89PJFBPBK09Q7CRPMM4G7PJ=%EA%B3%A0%EC%9C%A0-%ED%95%84%EB%93%9C 01H89PJFBQM4NKFSFF8XGMX9XT=skan-attribution-messages message-types-for-skan-attribution=skan-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%8C%80%ED%95%9C-%EB%A9%94%EC%8B%9C%EC%A7%80-%EC%9C%A0%ED%98%95 01H89PJFBQBFCK5QVWW2X09H28=skan-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%8C%80%ED%95%9C-%EB%A9%94%EC%8B%9C%EC%A7%80-%EC%9C%A0%ED%98%95 set-up-push-api-endpoints=push-api-%EC%97%94%EB%93%9C%ED%8F%AC%EC%9D%B8%ED%8A%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H89PJFBQZ2FW3ST5V4FW91GS=push-api-%EC%97%94%EB%93%9C%ED%8F%AC%EC%9D%B8%ED%8A%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H89PJFBQ6WP7ERP0DJ69QZ1G=%EC%A3%BC%EC%9D%98 push-api-setup-checklist=push-api-%EC%84%A4%EC%A0%95-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 01H89PJFBQ625A7G3QT5HQJXMW=push-api-%EC%84%A4%EC%A0%95-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 01H89PJFBQGW8ZV76Z0HTNX2AB=serverside-requirements-your-server serverside-requirements=%EC%84%9C%EB%B2%84-%EC%B8%A1-%ED%95%84%EC%9A%94-%EC%82%AC%ED%95%AD 01H89PJFBQ2BC5GHX403RD2RAT=%EC%84%9C%EB%B2%84-%EC%B8%A1-%ED%95%84%EC%9A%94-%EC%82%AC%ED%95%AD 01H89PJFBQ4FXB7ABMFVHX326H=push-api-planning-checklist-for-appsflyer-attribution endpoint-planning-table=%EC%97%94%EB%93%9C%ED%8F%AC%EC%9D%B8%ED%8A%B8-%EA%B3%84%ED%9A%8D-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 01H89PJFBQJXWWPQDKZ387VYX3=%EC%97%94%EB%93%9C%ED%8F%AC%EC%9D%B8%ED%8A%B8-%EA%B3%84%ED%9A%8D-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 01H89PJFBQZE6KJDHXRB8GK7TF=set-up-appsflyer-attribution-endpoint add-an-appsflyer-attribution-endpoint=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%97%94%EB%93%9C%ED%8F%AC%EC%9D%B8%ED%8A%B8-%EC%B6%94%EA%B0%80-%EB%B0%A9%EB%B2%95 h_01JFSS65G8GTZNMY257QCV922M=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%97%94%EB%93%9C%ED%8F%AC%EC%9D%B8%ED%8A%B8-%EC%B6%94%EA%B0%80-%EB%B0%A9%EB%B2%95 test-the-endopoint=%EC%97%94%EB%93%9C%ED%8F%AC%EC%9D%B8%ED%8A%B8%EB%A5%BC-%ED%85%8C%EC%8A%A4%ED%8A%B8%ED%95%98%EB%A0%A4%EB%A9%B4 h_01JFSS6YVP1WFWXSZ7HP7GTDA2=%EC%97%94%EB%93%9C%ED%8F%AC%EC%9D%B8%ED%8A%B8%EB%A5%BC-%ED%85%8C%EC%8A%A4%ED%8A%B8%ED%95%98%EB%A0%A4%EB%A9%B4 01H89PJFBQQS31C6AF245SSJ61=set-up-skadnetwork-attribution-endpoint h_01HSDW5XQ28T3SQJTN5PBSBCFT=configure-authentication-token additional-procedures%E2%80%94managing-endpoints=%EC%B6%94%EA%B0%80-%EC%A0%88%EC%B0%A8%EC%97%94%EB%93%9C%ED%8F%AC%EC%9D%B8%ED%8A%B8-%EA%B4%80%EB%A6%AC 01H89PJFBQ7WV3NM7JR5Z9QEFB=%EC%B6%94%EA%B0%80-%EC%A0%88%EC%B0%A8%EC%97%94%EB%93%9C%ED%8F%AC%EC%9D%B8%ED%8A%B8-%EA%B4%80%EB%A6%AC 01H89PJFBQ9RZXNHGNNYV5MP7P=change-an-endpoint 01H89PJFBQGE1WESD7ZEMBEFNE=delete-an-endpoint troubleshooting-traits-and-limitations=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD 01H89PJFBQJDGT1FVHKG9DETHJ=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD 01H89PJFBQAAZYF7YWKC7TP884=test-message-fails 01H89PJFBQHQJSHE09GC599AQ6=duplicate-retargeting-inapp-events 01H89PJFBRDET8T8CTAP1GW0J9=inapp-event-message-selection-is-disabled 01H89PJFBRH58FX1FTH37DP3HC=missing-push-messages-and-cloudfront 01H89PJFBR3CJSR2AEFP3HT5JE=endpoint-error-messages 01H89PJFBRZXXEMPBGBPB35MQ9=specifications-and-limitations h_01JQY6KXYBGXTSVDC18H5CZCWR=can-i-include-custom-headers-with-the-push-api-request h_01HE7SH7XFMPJ13DKCZ04RCJDD=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
