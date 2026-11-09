---
title: 추천 엔터테인먼트 앱 이벤트
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-04-25T10:44:33Z'
  edited_at: '2026-10-14T10:26:23Z'
  id: 360019699898
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/360019699898
---
> **한눈에 보기:** 요약: 엔터테인먼트 앱에 대해 제안된 인앱 이벤트를 기록하여 사용자 여정 내내 사용자의 품질을 측정합니다.

## <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="100px" /> Entertainment

주문형 콘텐츠(on-demand contents)에 대한 사용자의 요구가 증가하면서, 엔터테인먼트 어플리케이션 시장은 경쟁이 매우 치열해졌습니다. 기록할 것을 제안하는 대표적인 이벤트는 사용자 구독, 스트리밍 콘텐츠, 콘텐츠 다운로드 및 저장입니다.

이벤트 기록으로 다음을 확인할 수 있습니다.

* 사용자가 소비하는 콘텐츠
* (사용자가 요구하는 콘텐츠에 따른) 캠페인 성과
* 사용자 인게이지먼트와 사용도

이러한 이벤트는 다음 스마트 TV에서 실행되는 엔터테인먼트 앱에도 해당됩니다.

* 안드로이드 스마트 TV
* 애플 TV (tvOS)
* 아마존 파이어 TV

<div id="important" />

> 🚧 **중요!**
>
> * 인앱 이벤트 구현과 관련한 마케터용 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">지침</Anchor>을 반드시 읽어보십시오.
> * 구현 프로세스를 간소화하려면 당사의 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=entertainment">인앱 이벤트 생성기</Anchor>를 사용하십시오. 이 도구에는 본 문서에서 설명한 일반적인 인앱 이벤트가 모두 포함되어 있으며 사용자는 비즈니스 요구사항에 따라 이벤트를 수정할 수 있습니다. 완료되면 파일을 개발사와 공유하십시오.
> * 본 문서에 포함된 각 권장 이벤트에 대해 iOS, 안드로이드 및 Unity 개발자를 위한 <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=entertainment&view=code">코드 샘플</Anchor>이 있습니다.
> * 개발사에 대한 자세한 지침은 **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">앱스플라이어 개발자 허브</Anchor>** 에서 확인할 수 있습니다.
>
> 인앱 이벤트 기록에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 가이드를</Anchor> 참조하십시오.

<Image align="center" alt="Flowchart_for_recommended_events entertainment_app_user_journey" src="https://files.readme.io/4cce1846cd799226493b914bc36d0944192a3c6e5290ac461b22ed712265f59f-360020063177.png" />

<div id="recommended-structures-for-predefined-events" />

## 사전 정의된 이벤트에 권장되는 구조

다음 섹션에서는 엔터테인먼트 수직 구조에 일반적인 이벤트 구조 목록을 제공합니다. 각 구조에는 사용할 미리 정의된 이벤트 이름과 제안된 이벤트 파라미터가 포함됩니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="complete-registration-af_complete_registration" />

<Accordion title="가입 완료(af_complete_registration)">

**목적**

앱을 설치하고 등록 프로세스를 완료한 사용자 수와 사용자가 선호하는 등록 방법에 대해 알아봅니다.

**트리거**

사용자가 등록 프로세스를 완료한 시간

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_registration\_method | 사용자가 등록을 위해 선택한 방법 | 페이스북, 구글, 이메일 |

</Accordion>

<div id="login-af_login" />

<Accordion title="로그인 (af_login)">

**목적**

등록된 사용자의 잔존율 파악

**트리거**

사용자가 성공적으로 로그인한 시간

**이벤트 파라미터**

추가 파라미터 없이 전송 가능

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="체험 시작 (af_start_trial)">

**목적**

많은 스트리밍 서비스는 프리미엄 기능을 써볼 수 있도록 사용자에게 체험 기간을 제공합니다. 이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 얼마나 많은 사용자가 무료 체험에 참여하는지 파악
* 평가판이 프로모션의 일부인지 파트너와의 협업인지 여부
* 사용자에게 시험 기간을 사용하도록 유도한 프로모션

**트리거**

사용자가 무료 체험에 참여하고 시작한 시기

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| trial\_method | 시험판 활성화 방법 | 새 휴대폰 무료, 통신사 무료, 프로모션, 쿠폰 코드 |
| trial\_method\_identifier | 무료 체험 방법 식별자 | 통신사 이름(예: **Vodafone**)<br /><br />파트너 이름, 예를 들어 **메타 광고**<br /><br />쿠폰 코드(예: **TRA123**) |

<div id="note" />

> 📘 **참고사항**
>
> 이 이벤트를 Meta ads StartTrial 이벤트와 매핑하고 수익을 연관시키려면 af\_revenue 대신 af\_price 파라미터를 사용하세요.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="구독 (af_subscribe)">

**목적**

구독은 스트리밍 서비스의 핵심입니다. 이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 사용자를 구독까지 유도한 캠페인이 무엇인지 알 수 있습니다.
* 평가판의 사용자 수를 구독 사용자와 비교합니다.
* 구독에서 창출되는 수익 금액을 파악하여 캠페인 및 미디어소스에 어트리뷰트할 수 있습니다.

**트리거**

* 사용자가 성공적으로 구독 신청을 했을 때
* 구독이 갱신되었을 때

추가 정보는 당사의 구독 어트리뷰션-개요를 참조하십시오.

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| new\_subscription | 신규 구독인지 구독 갱신인지 여부 | true / false |
| af\_coupon\_code | 구독 중에 사용된 쿠폰 코드 | 3MonthsSubscription |
| coupon\_code\_value | 초기 가격 대비 쿠폰 할인 금액 | 10% |
| <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#revenue-events">af\_수익</Anchor> | 구독 관련 수익 | 5.95 |
| af\_통화 | 구독 결제 통화 | USD |
| subscription\_method | 구독에 사용된 결제 수단 | 신용카드, 전자 지갑, PayPal |
| expiration\_date | 구독 만료 날짜 | 2018/07/18 |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## 사용자 지정 이벤트에 대한 권장 구조

다음 섹션에서는 사용자 지정 이벤트 이름과 사용하도록 제안된 이벤트 파라미터를 포함한 이벤트 구조 목록을 제공합니다. 인앱 이벤트에는 비즈니스 요구를 충족하는 이벤트 파라미터가 포함될 수 있습니다.

<div id="media-play-media_play" />

<Accordion title="미디어 재생(media_play)">

**목적**

사용자가 제공하는 미디어를 재생하는 이벤트를 기록합니다. 이런 미디어는 예를 들어 비디오, 음악, TV 쇼 또는 라디오 쇼 등이 될 수 있습니다.

이 이벤트 기록에 의해 다음을 확인할 수 있습니다.

* 유형 및 콘텐츠별 미디어 사용
* 가장 인기 있는 스트리밍 콘텐츠의 언어
* 스트리밍 콘텐츠의 최소, 최대, 평균 재생 시간

**트리거**

미리 정의된 시간(예: 2분 후 스트리밍된 콘텐츠).

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_콘텐츠\_유형 | 스트리밍되는 콘텐츠 유형 | tv show, music |
| af\_content\_id | 스트리밍되는 콘텐츠의 ID | 092, E34 |
| af\_content | 콘텐츠 제목(예: 노래 제목, TV 쇼 제목, 에피소드 등) | Title of content |
|  | 미디어의 총 지속시간(예: 비디오의 총 길이). | 5 |
| 언어 | 콘텐츠 언어 |  |

</Accordion>

<div id="media-minutes-media_minutes" />

<Accordion title="미디어 사용 시간(media_minutes)">

**목적**

미디어 사용 시간(media minutes)은 사용자가 주어진 콘텐츠를 얼마나 사용했는지를 나타냅니다. 이 지표는 사용자의 서비스 사용량을 추정할 수 있기 때문에 수익 지표 다음으로 스트리밍 업계에서 가장 중요한 지표입니다. 또한 전반적인 서비스의 사용률과 어떤 콘텐츠가 가장 인기가 있는지 알 수 있습니다. 이 이벤트는 다음과 같은 점에서 도움이 될 수 있습니다.

* 서비스를 광범위하게 활용하는 사용자를 알 수 있습니다.
* 어떤 미디어 유형 및 콘텐츠가 인기 있는지 알 수 있습니다.

**트리거**

다음 중 하나입니다.

* 사용자가 미디어 스트리밍을 완료할 때
* 사용자가 미디어 스트리밍을 중단할 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| minutes\_consumed | 사용자가 미디어를 본 시간(분). 예를 들어 비디오의 총 길이는 5분이 될 수 있지만 사용자는 3분만 볼 수 있습니다. | 3 |
| af\_콘텐츠\_유형 | 스트리밍되는 콘텐츠 유형 | tv show, music |
| af\_content\_id | 스트리밍되는 콘텐츠의 ID | 092, E34 |
| af\_content | 콘텐츠 제목(예: 노래 제목, TV 쇼 제목, 에피소드 등) | Title of content |
|  | 미디어의 총 지속시간(예: 비디오의 총 길이). | 5 |
| 언어 | 콘텐츠 언어 |  |

</Accordion>

<div id="media-downloaded-media_downloaded" />

<Accordion title="다운로드한 미디어(media_downloaded)">

**목적**

미디어 재생 및 미디어 다운로드를 기록하고 이 둘을 비교하여 사용자 선호도를 강조합니다. 사용자가 스트리밍으로 재생하는 것을 선호하는 미디어와 다운로드해서 재생하는 것을 선호하는 미디어를 알 수 있습니다.

**트리거**

사용자가 미디어 다운로드를 시작할 때

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_콘텐츠\_유형 | 콘텐츠 유형 | tv show, music |
| af\_content\_id | 콘텐츠 ID | 092, E34 |
| af\_content | 콘텐츠 제목(예: 노래 제목, TV 쇼 제목, 에피소드 등) | Title of content |
|  | 미디어의 총 지속시간(예: 비디오의 총 길이). | 5 |
| 언어 | 콘텐츠 언어 |  |

</Accordion>

<div id="media-saved-media_saved" />

<Accordion title="저장된 미디어(media_saved)">

**목적**

사용자 선호도를 강조하는 데 도움이 됩니다.

**트리거**

사용자의 기기에 미디어를 저장할 때마다

**이벤트 파라미터**

| 이름 | 설명 | 예시 값 |
| --- | --- | --- |
| af\_콘텐츠\_유형 | 콘텐츠 유형 | tv show, music |
| af\_content\_id | 콘텐츠 ID | 092, E34 |
| af\_content | 콘텐츠 제목(예: 노래 제목, TV 쇼 제목, 에피소드 등) | Title of content |
|  | 미디어의 총 지속시간(예: 비디오의 총 길이). | 5 |
| 언어 | 콘텐츠 언어 |  |

</Accordion>

<div data-zendesk-anchors="entertainment=-entertainment h_01HGTAX1B0KT8Q6PRE41JCPJ60=-entertainment h_01HGTAX1B0K2RKYGPFFARM0E1B=%EC%A4%91%EC%9A%94 recommended-structures-for-predefined-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAX1B05C7G67RJPSG3YF66=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EA%B6%8C%EC%9E%A5%EB%90%98%EB%8A%94-%EA%B5%AC%EC%A1%B0 h_01HGTAX1B0CN19DY7PAR27YATD=complete-registration-af_complete_registration h_01HGTAX1B0MG1MTD7QXBCK6JHN=login-af_login h_01HGTAX1B0GTJ6ZWRNW5SEJVE9=start-trial-af_start_trial h_01HGTAX1B1XW0RAV8WPP0HF8HD=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HGTAX1B1AHHGW6SMXST1KXQE=subscription-af_subscribe recommended-structures-for-custom-events=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAX1B1ATFH70K2BJZ7XW13=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B6%8C%EC%9E%A5-%EA%B5%AC%EC%A1%B0 h_01HGTAX1B1WRQ39H27KPRFZH9W=media-play-media_play h_01HGTAX1B15Z24J8JKKAQH2Z2S=media-minutes-media_minutes h_01HGTAX1B1JPY44SYM59K0M9H2=media-downloaded-media_downloaded h_01HGTAX1B1FXF1DRC91VYRCGMP=media-saved-media_saved" />
