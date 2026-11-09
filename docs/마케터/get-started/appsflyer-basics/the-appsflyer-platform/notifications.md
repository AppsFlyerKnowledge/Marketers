---
title: 알림
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
  created_at: '2025-03-24T10:10:37Z'
  edited_at: '2026-10-14T10:28:54Z'
  id: 33732395637905
  locale: ko
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/ko/articles/33732395637905
---
> **한눈에 보기:** 플랫폼을 통해 중요한 앱스플라이어 계정 알림을 관리할 수 있습니다.

계정에서 특정 이벤트 발생 시 알림을 수신하도록 설정할 수 있습니다. **알림 설정**에서 알림을 수신할지 여부를 선택할 수 있습니다.

<div id="accessing-and-configuring-notification-preferences" />

## 알림 기본 설정에 접근하고 설정하기

<div id="to-access-notifications" />

### 알림 액세스 방법:

* 화면 상단 표시줄에서 계정(이메일 주소) 아래 드롭다운 메뉴를 펼치고 **알림**을 클릭합니다.
* 플랫폼 내의 벨 아이콘에서 > **설정 아이콘**으로 이동합니다.

<div id="configuring-notifications" />

### 알림 설정

알림 수신을 선택하려면 사용 가능한 알림 목록에서 알림을 켜십시오.

알림 수신을 중지하려면 알림을 끄십시오.

참고: 일부 알림은 이메일을 통해서만 제공됩니다. 이메일 전용 알림 탭에는 이러한 [알림](/docs/notifications#이메일-전용-알림) 설정이 포함되어 있습니다.

<div id="what-notifications-can-i-receive" />

## 어떤 알림을 받을 수 있나요?

다음 알림 카테고리가 제공됩니다:

* 계정 및 계획 관리
* 청구 또는 거래 문제
* 프라이버시 관련 알림
* 인사이트 및 설정
* 협업 기능

참고: 일부 알림은 이메일 전용으로 제공됩니다. 보다 자세한 내용은 [여기](/docs/notifications#email-notification)에서 확인하세요.

특정 알림을 수신하려면 다음 조건을 충족해야 합니다.

* **해당 알림이 귀사의 앱스플라이어 계정에서 사용 가능해야 합니다.** 회사 계정에서 알림을 사용할 수 없는 경우, 해당 알림을 활성화하는 스위치가 표시되지 않습니다.
  * 예를 들어, 귀사가 앱스플라이어 Push API 기능을 구독하지 않은 경우, 이 기능과 관련된 스위치는 표시되지 않습니다.
* **사용자 권한에 따라 사용할 수 있습니다.** 알림이 특정 기능 관련되어 있고, 해당 기능에 대한 접근 권한이 부여되지 않은 경우, 알림을 활성화하는 스위치가 표시되지 않습니다.
  * 예를 들어 연동 파트너 추가/편집 권한이 없는 경우 연동 파트너 구성과 관련된 알림을 켜고 끄는 스위치가 활성화되지 않습니다.

<div id="when-will-i-receive-notifications" />

## 알림은 언제 받을 수 있나요?

특정 알림 수신을 설정한 경우, 해당 알림의 트리거 이벤트가 발생하면 이메일을 받게 됩니다. 단, 해당 트리거 이벤트가 사용자가 권한을 가진 **앱 및 미디어 소스**에 적용되는 **경우에만** 이메일이 전송됩니다.

<div id="example" />

<Accordion title="예시">

다음은 예시 시나리오입니다.

* 귀사는 앱스플라이어에 3개의 앱을 추가했습니다. 추가한 앱: 앱 A, 앱 B, 앱 C.
* 각 앱은 Google Ads 및 TikTok의 2가지 미디어 소스(연동 파트너)와 연동이 활성화되어 있습니다. 활성화된 연동 파트너: Google Ads와 TikTok
* 귀사의 앱스플라이어 사용자는 다음 권한이 있습니다.
  * 연동 파트너 추가 및 편집
  * 앱 C의 데이터 액세스
  * Google Ads 데이터 액세스
* 연동 파트너 설정에 변경 사항이 있을 때 알림을 수신하도록 선택했습니다.

결과:

* 앱 A 및 B에 대한 연동 파트너 설정 변경 사항이 있는 경우 알림을 받지 **않습니다**.
* 앱 C에 대한 TikTok 설정 변경이 있을 때 알림을 받지 **않습니다**.
* 앱 C에 대한 Google Ads 설정이 변경되면 알림을 받게 **됩니다**.

</Accordion>

<div id="where-will-i-receive-notifications" />

## 알림은 어디서 받을 수 있나요?

알림은 [벨](/docs/notifications#bell-notification) 아이콘, [이메일](/docs/notifications#email-notification), 또는 [슬랙](/docs/notifications#slack-notification) 연동을 통해 받을 수 있습니다. 

<div id="bell-notification" />

<Accordion title="벨 알림">

벨 아이콘 알림은 계정 메뉴(이메일 주소 드롭다운) 왼쪽의 상단 바에서 찾을 수 있습니다.

기어 아이콘을 클릭하면 [알림 기본 설정](/docs/notifications#알림-기본-설정에-접근하고-설정하기)으로 이동합니다.

</Accordion>

<div id="email-notification" />

<Accordion title="이메일 알림">

알림은 앱스플라이어 계정과 연결된 이메일 주소로 이메일로 전송됩니다.

일부 알림은 이메일을 통해서만 제공됩니다. 이 알림 설정은 **이메일 전용 알림** 탭에서 찾을 수 있습니다.

<div id="note" />

> 📘 **참고**
>
> 모든 앱스플라이어 알림 이메일은 [notifications@appsflyer.com](mailto:notifications@appsflyer.com)에서 발송됩니다.

<div id="email-only-notifications" />

#### 이메일 전용 알림

다음 표에는 사용 가능한 **이메일 전용 알림**과 알림을 트리거하는 이벤트가 나와 있습니다.

| 알림 | 이벤트 트리거 |
| --- | --- |
| 연동 파트너 설정 변경 | <ul><li>새로운 연동 파트너가 활성화됨</li><li>기존 연동 파트너가 비활성화됨</li><li>기존 연동 파트너의 설정이 변경됨</li></ul> |
| Push API 실패 | 12시간 이내에 앱의 Push API 메시지 중 5% 이상이 실패하는 경우 |
| 오디언스 연결 실패 | 확인이 필요한 오디언스 파트너 연결 오류가 있습니다. |
| 광고 수익 연동 일시 중지 | 경고 상태가 30일 이상 지속되면 광고 수익 연동이 일시 중지됩니다. |
| 광고 수익 데이터 실패 | 광고 수익 연동에 데이터가 수신되지 않음 |
| 연동 파트너 비용 설정 변경 | 팀원이 비용 연동 설정을 변경함 |
| SKAN 연결 실패 | 앱스플라이어와의 Google Ads 또는 Meta SKAN 연동에 문제가 발생했으며, 사용자 확인이 필요합니다. 현재 연동을 삭제하고 다시 로그인해야 할 수 있습니다. |

</Accordion>

<div id="slack-notification" />

<Accordion title="슬랙 알림">

**슬랙 알림 설정하기**

슬랙 알림을 설정하려면 먼저 슬랙에 연결해야 합니다:

1. 알림 기본 설정 페이지에서 페이지 오른쪽 상단에 있는 **연동** 버튼을 클릭하세요.
2. 슬랙 알림 커넥터로 **연결**을 클릭하세요.
3. 권한 요청을 검토하고 승인하십시오.
   1. **Slack 관리자일 경우:**
      1. 슬랙에서 Slack Workspace를 클릭하세요.  
         <Image align="center" alt="" src="https://a.slack-edge.com/8e8e4/helpcenter/img/workspace-picker@2x.jpg" width="263px" />
         참고: 연결하려는 Slack Workspace가 올바른지 확인하세요.
      2. **Tools & settings** -> **Manage apps**로 이동하세요.
      3. **Admin panel**에서 **Requests**를 선택하세요,
      4. **Needs review** 탭에서 앱스플라이어 앱 요청 옆에 있는 세 개의 점을 클릭하세요.
      5. **Approve**를 클릭한 한 다음, 표시되는 팝업에서 승인을 완료합니다.
      6. **앱스플라이어 연동 페이지로 돌아가서** 허용 **버튼을 클릭하세요.**
   2. **슬랙 관리자가 아닐 경우:**  
      1. 슬랙을 앱스플라이어에 연결하기 위해 슬랙 관리자에게 권한을 요청하세요.
      2. 슬랙 관리자가 위의 모든 단계를 **수행해야 합니다**. .
      3. 관리자의 권한 요청 이전에는 슬랙 커넥터가 보류 상태로 전환됩니다.
      4. 슬랙 관리자가 연결을 승인하면 **연결** 을 클릭하여 연동을 시작하고 대기 중에서 연결됨으로 전환합니다.

</Accordion>

<div data-zendesk-anchors="accessing-email-notifications=%EC%95%8C%EB%A6%BC-%EA%B8%B0%EB%B3%B8-%EC%84%A4%EC%A0%95%EC%97%90-%EC%A0%91%EA%B7%BC%ED%95%98%EA%B3%A0-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01HKA254W4XDVNP816N46N59ZV=%EC%95%8C%EB%A6%BC-%EA%B8%B0%EB%B3%B8-%EC%84%A4%EC%A0%95%EC%97%90-%EC%A0%91%EA%B7%BC%ED%95%98%EA%B3%A0-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 to-access-notifications=%EC%95%8C%EB%A6%BC-%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%A9%EB%B2%95 h_01JQ66J4YSCSX7ZGG81XHGJ3MM=%EC%95%8C%EB%A6%BC-%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%A9%EB%B2%95 configuring-notifications=%EC%95%8C%EB%A6%BC-%EC%84%A4%EC%A0%95 h_01HKA254W497H0SKTZ33CVSA4P=%EC%95%8C%EB%A6%BC-%EC%84%A4%EC%A0%95 what-notifications-can-i-receive=%EC%96%B4%EB%96%A4-%EC%95%8C%EB%A6%BC%EC%9D%84-%EB%B0%9B%EC%9D%84-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 h_01HKA254W47XRG1D3HZ6VBZ2BH=%EC%96%B4%EB%96%A4-%EC%95%8C%EB%A6%BC%EC%9D%84-%EB%B0%9B%EC%9D%84-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 when-will-i-receive-notifications=%EC%95%8C%EB%A6%BC%EC%9D%80-%EC%96%B8%EC%A0%9C-%EB%B0%9B%EC%9D%84-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 h_01JQ66BX52MV5WQ7RXH6SY3QHK=%EC%95%8C%EB%A6%BC%EC%9D%80-%EC%96%B8%EC%A0%9C-%EB%B0%9B%EC%9D%84-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 h_01JQ6EYTZ13FHYERT48K3J25SV=example where-will-i-receive-notifications=%EC%95%8C%EB%A6%BC%EC%9D%80-%EC%96%B4%EB%94%94%EC%84%9C-%EB%B0%9B%EC%9D%84-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 h_01HKA254W4Z95M335V7KWAJA6N=%EC%95%8C%EB%A6%BC%EC%9D%80-%EC%96%B4%EB%94%94%EC%84%9C-%EB%B0%9B%EC%9D%84-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 h_01JQ667RAW19658DVMZNFXNAJK=bell-notification h_01JQ667RAWCAVYBZD3J0T8XH2G=email-notification h_01JJGTDQFM1WE9G3XWSN9S7Z02=%EC%B0%B8%EA%B3%A0 emailonly-notifications=%EC%9D%B4%EB%A9%94%EC%9D%BC-%EC%A0%84%EC%9A%A9-%EC%95%8C%EB%A6%BC h_01JQ6EQR8JRBZ2ECJ7SHHWDWFC=%EC%9D%B4%EB%A9%94%EC%9D%BC-%EC%A0%84%EC%9A%A9-%EC%95%8C%EB%A6%BC h_01JQ667RAW48YQ64VXW899EW3X=slack-notification" />
