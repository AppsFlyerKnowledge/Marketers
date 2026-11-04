---
title: 세션 횟수 계산
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-03-14T12:13:13Z'
  edited_at: '2026-10-14T10:35:21Z'
  id: 360000520785
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/360000520785
---
> **한눈에 보기:** 요약: 세션 지표는 광고주가 특정 기간 동안 앱 사용자 인게이지먼트를 측정하는 데 사용합니다.

<Image alt="DAU_example.jpg" src="https://files.readme.io/97b845b9e04809dc6b670746c81cf1ca59dce11f492194ee7e7895ada01c0b86-360016015278.jpg" width="461px" />

<div id="sessions-counting-principles" />

## 세션 집계 원칙

사용자가 수행한 세션 수(일명 출시)는 중요한 지표이며 앱에 대한 사용자 인게이지먼트의 척도로 사용됩니다. 여러 리포트 및 대시보드를 통해 사용할 수 있습니다. 세션은 다음 지표를 도출하는 데 사용됩니다.

* 일일 활성 사용자(DAU)
* 월간 활성 사용자 (MAU)
* 잔존율
* 기본 설정인 3-앱 열기를 사용하는 로열 유저

**참고!** 오가닉 세션의 경우 지표는 액티비티 및 코호트 대시보드에서 사용할 수 있지만 개요 대시보드에서는 사용할 수 없습니다.

<div id="sessions-calculation" />

### 세션 계산

세션 지표는 SDK에서 리포트한 *af\_app\_opened* 이벤트를 사용하여 계산됩니다.

*af\_app\_opened 이벤트*는 데이터 락커를 통해 사용할 수 있는 로데이터 세션에서 *실행*으로 표시됩니다. 세션은 다른 리포트 도구에서는 사용할 수 없습니다. 이해를 돕기 위해 본 기사에서는 *af\_app\_opened*라는 용어를 사용합니다.

**세션 리포트**

다음 중 하나가 발생하면 SDK에서 세션을 리포트합니다.

* 사용자가 앱을 실행한 경우.
* 앱을 백그라운드에서 포그라운드로 가져올 때. 개발자는 setMinTimeBetweenSessions를 호출하여 리포트 작동을 변경할 수 있습니다.
* 안드로이드 앱에서 개발자의 명시적 세션 리포트입니다. 예를 들어, 이것은 항상 백그라운드에 있는 유틸리티 앱에 의해 구현됩니다.

**세션 지표**

<div id="minimum-time-between-sessions-mechanism" />

## 세션 메커니즘 간의 최소 시간

메커니즘은 세션 계수에 영향을 줍니다. **참고!** 세션 사이의 최소 시간이 1시간 이상이고 사용자가 하루에 여러 번 앱을 실행지 않으면 DAU 및 리텐션과 같은 일부 세션 관련 지표가 영향을 받을 수 있다는 점을 고려하십시오. 사용자가 일반적으로 하루에 한 번 앱을 실행하는 앱의 경우 특히 그렇습니다.

<div id="description-and-example" />

<Accordion title="설명 및 예시">

흐름은 다음과 같습니다. 세션이 카운트됨 → 카운트다운 타이머가 시작됨 → 타이머가 카운트다운되는 동안 리포트된 세션은 무시됩니다.

**예시**

| 사례 예시 | 세션 리포트 시간(00:00 이후의 분 수) | 계수된 세션 수 | 무시된 세션 수 |
| --- | --- | --- | --- |
| A | 0, 10, 20, 30 | 4 | 없음 |
| B | 0, 1, 9, 11 | 2 | 1, 9 |
| C | 0, 10, 15, 21 | 3 | 15 |

</Accordion>

<div id="timer-setting" />

<Accordion title="타이머 설정">

* 기본값: 1-60분
* 사용 가능한 값은 다음과 같습니다.

  * 1-60분
  * 1-24시간

**세션 타이머 사이에 허용되는 최소 시간을 설정하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **설정** > **앱 설정을** 선택합니다.
2. **세션 간 최소 시간**을 설정합니다.
3. **설정 저장**을 클릭하세요.   
   변경 사항은 1시간 이내에 적용됩니다.

</Accordion>

<div id="note" />

<div id="sessions-related-topics" />

## 세션 관련 주제

<div id="retargeting-sessions" />

<Accordion title="리타게팅 세션">

* 리타게팅 세션은 2020년 7월 12일부터 사용할 수 있습니다.
* 리타게팅 세션은 다음에서 사용 가능합니다.
  * 개요 대시보드의 리타게팅 및 통합 보기 유형.
  * 관련된 코호트 뷰, 즉 리타게팅 및 통합된 뷰. 
    * 통합 화면에서는, 세션이 UA와 리타겟팅 미디어 소스에 어트리뷰션 되었을 경우, 리타겟팅 미디어 소스가 우선시되며 UA 미디어 소스는 표시되지 않습니다.
    * 데이터 최신성: 매일 10:00 UTC
  * 데이터 락커: 데이터 락커: 리타게팅 세션 리포트를 사용 가능으로 설정할 수 있습니다. 리인게이지먼트 및 리어트리뷰션 세션을 모두 포함합니다.
    * 데이터 최신성: 6시간 지연
* 리인게이지먼트 기간 동안 세션은 UA와 리타게팅 미디어 소스 모두에 어트리뷰트됩니다. 유사하게, 다른 리인게이지먼트 인앱이벤트는 이중으로 어트리뷰트됩니다.
* Google Ads와 X 광고의 경우 중복 포스트백을 방지하기 위해 af\_app\_opened 이벤트가 한 번 전송됩니다.

</Accordion>

<div id="sessions-postbacks-to-partners" />

<Accordion title="파트너에 대한 세션 포스트백">

파트너 세션 포스트백을 보내 계된 각 세션에 대해 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#매핑-방법">포스트백</Anchor>을 전송할 수 있습니다.

* 참고! 데이터 락커를 통해 사용할 수 있는 앱스플라이어 로데이터 리포에서 이 이벤트는 *출시*로 반영됩니다.
* 이것은 대용량 이벤트이며 많은 파트너가 수신을 원하지 않는다는 점을 고려하십시오.

</Accordion>

<div id="session-reporting-by-the-app-sdk" />

<Accordion title="앱(SDK)에 의한 세션 리포트">

앱 사이드: SDK는 앱이 열리거나 SDK *setMinTimeBetweenSessions* 설정을 고려한 후 포그라운드로 가져올 때마다 *af\_app\_opened*를 보냅니다.

계수된 세션은 다른 인앱이벤트와 동일한 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model">어트리뷰션 규칙</Anchor>을 사용하여 어트리뷰트됩니다.

<div id="explicit-sessions-reporting-by-the-developer-android-apps-only" />

#### **개발자의 명시적 세션 리포트(안드로이드 앱만 해당)**

* 백그라운드에서 계속 작동하는 앱은 세션을 리포트하기 위해 개발자가 구현한 일부 논리가 필요할 수 있습니다. 예를 들어 배터리 세이버, 런처, 화면 잠금 및 바이러스 백신 앱과 같은 유틸리티 앱을 들 수 있습니다. 이러한 유형의 앱의 경우 매일 자정에 또는 앱에 적절한 다른 간격으로 세션을 리포트하는 것이 좋습니다.
* 다른 경우 사용자가 메모리 지우기 버튼 누르기 등과 같은 일부 인앱 작업을 수행할 때 세션을 계수할 수 있습니다.

<div id="setting-minimum-time-between-app-launches" />

#### **앱 실행 사이의 최소 시간 설정**

SDK에서 두 세션이 별도로 리포트될 수 있도록 두 세션 사이에 경과할 수 있는 최소 시간을 설정합니다.

***이벤트를 의미하는 setMinTimeBetweenSessions*** af\_app\_opened사용하여 각 세션이 보고되도록 세션 간에 발생해야 하는 최소 시간을 제어합니다.

* [기본값] 5초. 최소 5초 지나서 다른 세션을 리포트해야 함을 의미합니다.
* API를 사용하면 세션 사이에 필요한 최소 시간을 설정할 수 있습니다.

iOS SDK 참조

<Tabs>
<Tab title="안드로이드">

안드로이드 SDK 참조를 확인하세요.

</Tab>

<Tab title="iOS">

</Tab>

<Tab title="Unity">

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="sessions-counting-principles=%EC%84%B8%EC%85%98-%EC%A7%91%EA%B3%84-%EC%9B%90%EC%B9%99 h_01HB8NDPNKERK1RR1Y09V2R2CC=%EC%84%B8%EC%85%98-%EC%A7%91%EA%B3%84-%EC%9B%90%EC%B9%99 sessions-calculation=%EC%84%B8%EC%85%98-%EA%B3%84%EC%82%B0 h_01HB8NDPNKFW6S28A3TC7W5J3C=%EC%84%B8%EC%85%98-%EA%B3%84%EC%82%B0 minimum-time-between-sessions-mechanism=%EC%84%B8%EC%85%98-%EB%A9%94%EC%BB%A4%EB%8B%88%EC%A6%98-%EA%B0%84%EC%9D%98-%EC%B5%9C%EC%86%8C-%EC%8B%9C%EA%B0%84 h_01HB8NDPNKF32E34M3CBJ6GMP8=%EC%84%B8%EC%85%98-%EB%A9%94%EC%BB%A4%EB%8B%88%EC%A6%98-%EA%B0%84%EC%9D%98-%EC%B5%9C%EC%86%8C-%EC%8B%9C%EA%B0%84 h_01HB8NDPNKERP5YVEXMPKP620B=description-and-example h_01HB8NDPNK6R2P682EPSPQ8MGH=timer-setting sessions-related-topics=%EC%84%B8%EC%85%98-%EA%B4%80%EB%A0%A8-%EC%A3%BC%EC%A0%9C h_01HB8NDPNKPTJX56Q2SVAB6V6T=%EC%84%B8%EC%85%98-%EA%B4%80%EB%A0%A8-%EC%A3%BC%EC%A0%9C h_01HB8NDPNMX2JTFHVTN14MVCCW=retargeting-sessions h_01HB8NDPNM5Z9ZHADD32EG66BJ=sessions-postbacks-to-partners h_01HYARHNQCWEHAFQ6B3FHZ0KTK=%EC%84%B8%EC%85%98-%EA%B4%80%EB%A0%A8-%EC%A3%BC%EC%A0%9C h_01HB8NDPNM0Z7D1ZS7G952SSKK=session-reporting-by-the-app-sdk explicit-sessions-reporting-by-the-developer-android-apps-only=%EA%B0%9C%EB%B0%9C%EC%9E%90%EC%9D%98-%EB%AA%85%EC%8B%9C%EC%A0%81-%EC%84%B8%EC%85%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EC%95%B1%EB%A7%8C-%ED%95%B4%EB%8B%B9 h_01HB8NTFMR3Y9GHFP3EWMAATHY=%EA%B0%9C%EB%B0%9C%EC%9E%90%EC%9D%98-%EB%AA%85%EC%8B%9C%EC%A0%81-%EC%84%B8%EC%85%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EC%95%B1%EB%A7%8C-%ED%95%B4%EB%8B%B9 setting-minimum-time-between-app-launches=%EC%95%B1-%EC%8B%A4%ED%96%89-%EC%82%AC%EC%9D%B4%EC%9D%98-%EC%B5%9C%EC%86%8C-%EC%8B%9C%EA%B0%84-%EC%84%A4%EC%A0%95 h_01HB8NTMC1JYPDWYG9YC8RNSEQ=%EC%95%B1-%EC%8B%A4%ED%96%89-%EC%82%AC%EC%9D%B4%EC%9D%98-%EC%B5%9C%EC%86%8C-%EC%8B%9C%EA%B0%84-%EC%84%A4%EC%A0%95" />
