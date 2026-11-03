---
title: 'X Ads(이전 명칭: Twitter Ads) FAQ 및 불일치'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:34:59Z'
  edited_at: '2026-10-14T10:38:29Z'
  id: 4410464352017
  locale: ko
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/ko/articles/4410464352017
---
> **한눈에 보기:**

## X Ads 자주 묻는 질문 및 불일치

<div id="who-can-perform-the-twitter-setup-on-appsflyer" />

<Accordion title="앱스플라이어에서 설정은 누가 할까요?">

앱스플라이어와 X Ads 간의 연동을 승인하는 사용자는 X Ads 계정 관리자 액세스 권한이 있어야 합니다.

</Accordion>

<div id="what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer" />

<Accordion title="앱스플라이어에서 어트리뷰션을 위해 선택된 X Ads 계정이 없으면 어떻게 됩니까?">

모든 어트리뷰션은 선택한 계정의 캠페인을 위한 것입니다. 계정을 선택하지 않으면 인앱 이벤트 매핑이 X Ads 구성 창에 계속 표시되더라도 인앱 이벤트 또는 속성이 X Ads로 전송되지 않습니다.

</Accordion>

<div id="do-the-account-owner-and-the-team-members-see-the-same-twitter-data" />

<Accordion title="계정 소유자와 팀원 모두 동일한 X Ads 데이터를 볼 수 있나요?">

아니요. 계정 소유자는 연결된 모든 X Ads 계정을 볼 수 있습니다. 팀원은 연결된 X Ads 계정만 볼 수 있습니다.

</Accordion>

<div id="how-do-i-disconnect-twitter-from-appsflyer" />

<Accordion title="앱스플라이어와 X Ads의 연결을 해제하려면 어떻게 해야 합니까?">

X Ads 계정에서 앱스플라이어의 연결을 해제할 수 있습니다. 다음 안내에서는 데스크톱 또는 노트북 브라우저를 사용하여 X Ads 계정에 로그인했다고 가정합니다.

1. X Ads에 로그인합니다.
2. 좌측 메뉴에서 **더 보기** > **설정 및 개인정보 보호**를 클릭합니다.
3. **보안 및 계정 액세스** > **앱 및 세션** > **연결된 앱**으로 이동하십시오.
4. 앱스플라이어를 클릭합니다.
5. **액세스 취소(Revoke Access)** 를 클릭합니다.

이제 앱스플라이어 계정으로 돌아가 <Anchor target="_blank" href="/marketers/ko/docs/x-ads-formerly-twitter-ads-integration-setup">원하는 경우 다른 X Ads 계정을 연결</Anchor>할 수 있습니다.

</Accordion>

<div id="is-it-possible-to-attribute-installs-to-multiple-twitter-accounts" />

<Accordion title="여러 X Ads 계정에 설치를 어트리뷰션할 수 있습니까?">

예, 하지만 X Ads에 대한 몇 가지 조치가 필요합니다. 그리고 약간의 백그라운드 작업을 해야합니다.

하나의 **핸들** (X 사용자라고도 함)만 앱스플라이어 계정에 연결할 수 있습니다. 한 사용자가 이 핸들을 연결시키면, 해당 사용자의 X Ads 계정이 앱스플라이어 대시보드의 X Ads 연동 페이지에 표시됩니다.

팀원 중 한 명도 X Ads 계정을 가지고 있는 경우, 이는 해당 팀원이 귀하와 다른 핸들을 가지고 있으며 해당 핸들을 앱스플라이어에 연결할 수 없음을 의미합니다. 왜냐하면 **처음 연결한 사용자의 핸들이 이미 앱스플라이어 계정에 연결되어 있기 때문입니다.** 팀 멤버의 X Ads 계정 또한 앱스플라이어에 표시되도록 하기 위해서는, **팀 멤버의 X Ads 계정에서, 처음 연결한 사용자에게 계정 관리자(account administrator) 액세스를 부여해야 합니다.**

팀 멤버가 Jenny이고, 그녀의 핸들(트위터 계정)은 @jenny 라고 가정합니다. 처음 연결한 사용자의 핸들(트위터 계정)은 @nivi이며, 이 계정은 이미 앱스플라이어에 연결되어 있습니다. 팀 멤버 Jenny의 트위터 광고 계정 또한 앱스플라이어에 표시되도록 하기 위해서는, **팀 멤버 Jenny의 X Ads 계정에서, 처음 연결한 사용자 계정 @nivi에게 계정 관리자 액세스를 부여해야 합니다.** 반드시 팀 멤버 Jenny가 이미 연결된 계정 @nivi에게 X Ads 계정 액세스를 부여해야 하며, 반대의 경우는 안 됩니다. Nivi의 계정에 액세스가 부여되고 나면, 앱스플라이어가 Nivi의 핸들(트위터 계정)에 연결된 모든 연관 계정을 확인할 수 있고 팀 멤버 Jenny의 계정도 이에 포함됩니다.

1. Jenny가 <Anchor target="_blank" href="http://ads.twitter.com/">ads.twitter.com</Anchor>에 로그인합니다.
2. **계정(Account)** 을 클릭하고 **계정 액세스 권한 편집(Edit access to account)** 을 선택합니다.  

   ![twitter_assign_account2.PNG](https://files.readme.io/cd2aa0b7a700fd0eee8754ac850adb99cc22b1c42d0d94f18d31ca71901ff31f-50903273809937.png)
3. Jenny는 자신의 X Ads 계정에 계정 관리자로 접속할 수 있는 권한을 @nivi에게 부여합니다.  

   [![twitter_edit_access_to_account.png](https://support.appsflyer.com/hc/article_attachments/51858129584401)](https://support.appsflyer.com/hc/article_attachments/51858104747537)
4. Jenny는 앱스플라이어 계정에 로그인하고 X Ads 옵션>> 활성 연동으로 이동합니다
5. 이 단계에서, Jenny는 자신의 X Ads 계정 또한 나타난 것을 볼 수 있습니다.
6. Jenny는 이제 그녀의 X Ads 계정을 볼 수 있으며, 연동을 설정할 수 있습니다. 계정 관리자는 연결된 모든 X Ads 계정을 볼 수 있습니다.  

   Jenny의 화면:

   ![jennys_ads_account.png](https://files.readme.io/73e3ca9be6090bfd47acb675e4faa634721d9aa75f5ebb8cf736fd56dd9e336b-50903273813137.png)

   어드민 계정의 화면:

   ![jennys_ads_account__1_.png](https://files.readme.io/d744c0e2de60011a0395a407607ec90f4fac04f76787b430cf1a74eda2342e66-50903273813649.png)

</Accordion>

<div id="any-special-instructions-for-agencies" />

<Accordion title="에이전시에 대한 특별한 가이드가 있습니까?">

네.  
네.에이전시가 새로운 X Ads 캠페인을 생성할 때, 캠페인 이름은 에이전시 이름과 함께 밑줄로 시작해야 합니다 (예시: "AgencyName\_Campaign1"). "AgencyName\_Campaign1").

> 📘 **참고**
>
> 앱스플라이어와 X Ads 간의 연결을 설정하려면, 광고주는 에이전시가 X Ads 트래픽을 실행할 수 있도록 X Ads 권한을 구성해야 합니다.

더 자세한 내용은 <Anchor target="_blank" href="/partners/ko/docs/about-agency-accounts#srn-설정">여기</Anchor>에서 확인하세요.

</Accordion>

<div id="do-you-make-twitters-raw-data-available-to-agencies" />

<Accordion title="대행사가 X Ads 로데이터를 사용할 수 있나요?">

X Ads 로데이터는 에이전시 서비스 약관이 에이전시를 제3자로 간주하기 때문에 에이전시에 제공하지 않습니다.

</Accordion>

<div id="im-clicking-save-close-but-twitters-configuration-is-not-saved-help" />

<Accordion title="저장 및 닫기를 클릭했지만 X Ads 구성이 저장되지 않았습니다! 도와주세요!">

과거에 X Ads를 통한 인스톨을 어트리뷰션하는, 다른 어트리뷰션 파트너와 앱을 연결한 적이 있는 경우는, 앱스플라이어 대시보드에서 X Ads를 설정할 때 다음과 같은 오류 메시가 나타납니다.

`{ "error":  **}` 오류: 앱이 다른 어트리뷰션 제공업체와 연결되어 있습니다. 앱스플라이어와 연결하십시오.**

또는 다음 오류 메시지가 나타날 수도 있습니다.

`{ "error":  **}` 오류: X Ads 구성을 저장하는 동안 오류가 발생했습니다.**

계정 선택이 저장되지 않는다면, 아마도 X Ads에서 문의하신 X Ads 계정을 다른 제공업체와 연결했을 수 있습니다. 해결하기 위해서는 다음 방법을 따르십시오.

* 다른 제공업체를 제거하기 위해서 X Ads에 문의합니다.
* 활성 계정(active account)의 이름을 선택합니다.
* **저장하고 닫기**를 클릭합니다.
* 여전히 문제가 해결되지 않으면, 이전 측정 제공업체으로 연락하여 계정에 연결된 이전 X Ads 태그를 제거해달라고 요청하세요.

</Accordion>

<div id="how-can-i-set-up-retargeting-campaigns-with-twitter" />

<Accordion title="어떻게 X Ads에 리타겟팅 캠페인을 설정할 수 있습니까?">

X 광고 리타게팅 캠페인을 구성하는 방법에 대한 자세한 내용을 보려면 여기를 클릭하십시오.

</Accordion>

<div id="does-retargeting-affect-inapp-events-sending-to-twitter" />

<Accordion title="리타게팅이 X Ads로 전송된 인앱 이벤트에 영향을 줍니까?">

네. 리타겟팅이 켜져 있으면, 앱스플라이어는 트위터의 요청에 따라 af\_app\_opened 이벤트 포스트백을 X Ads로 전송하지 않습니다.  
X Ads 설정 창에서 이 항목을 허용하더라도, af\_app\_opened 포스트백은 리타겟팅과 함께 전송되지 않음을 주의하십시오.

</Accordion>

<div id="how-can-i-stop-measuring-twitter-attributions" />

<Accordion title="X Ads 어트리뷰션을 어떻게 중지할 수 있습니까?">

X Ads와의 연동을 중단하려면 모든 계정을 선택 해제하고 **저장하고 닫기**를 클릭하세요.

</Accordion>

<div id="can-an-agency-measure-twitter-attributions-for-advertisers" />

<Accordion title="광고주를 위해 에이전시가 X Ads 어트리뷰션을 측정할 수 있습니까?">

네!  
예!앱스플라이어와 X Ads 간의 연결을 설정하려면, 광고주는 앱스플라이어 대시보드의 X Ads 파트너 페이지에서 활성 계정을 선택해야 하며, 최소 하나의 X Ads 계정이 확인되어야 합니다.  
그 이후에, 에이전시는 에이전시 대시보드에서 직접 X Ads 계정과 연결해야합니다.

</Accordion>

<div id="can-an-agency-configure-inapp-events-for-twitter" />

<Accordion title="에이전시가 X Ads용 인앱이벤트를 설정할 수 있습니까?">

에이전시는 X Ads 용 인앱이벤트를 설정할 수 없습니다. 메타 광고와 비슷하게, 광고주가 설정해야만 합니다.

</Accordion>

<div id="for-how-long-do-you-keep-twitter-s-userlevel-data" />

<Accordion title="X Ads의 사용자 수준 데이터를 얼마나 오래 보유합니까?">

X Ads는 어트리뷰션 제공업체가 설치 후 3개월이 지나면 사용자 수준 데이터를 삭제하도록 요구합니다. 즉, 사용자가 앱을 설치한 후 3개월 이후에 수행한 이벤트는 오가닉으로 집계됩니다.

과거 종합 데이터는 동일하게 유지됩니다.

</Accordion>

<div id="why-do-i-see-duplicated-cost-data" />

<Accordion title="왜 중복된 비용 데이터가 보이죠?">

X Ads에서는 한 캠페인에 여러 앱을 추가할 수 있습니다. X Ads는 앱스플라이어에 한 캠페인의 총 비용을 보고하고, 앱스플라이어에서는 각 앱 아래 앱별 캠페인 비용이 아니라 이 총 캠페인 비용 데이터가 나타납니다.

예를 들어, 안드로이드 앱과 iOS 앱 둘 다에 한 트위터 캠페인을 집행하는데 백만원이 들면, 앱스플라이어 대시보드에는 안드로이드 앱과 iOS 앱에 트위터 캠페인 비용이 백만원으로 표기됩니다. 비용이 (예를 들어,) 50만원씩 나뉘어지 않습니다.

비용 중복을 피하기 위해, 라인 아이템/캠페인별 한 앱만 정의하는 것이 좋습니다.

</Accordion>

<div id="im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message" />

<Accordion title="X Ads 계정을 앱스플라이어에 연결하려 했으나 에러 메시지를 받았습니다.">

앱스플라이어로부터 어트리뷰션 데이터를 받기 위해서는 X Ads 계정이 활성화된 광고 계정이어야 합니다.

**문제 해결하기**

1. X Ads에서 로그아웃합니다.
2. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동**을 선택합니다.
3. X Ads를 검색하여 선택합니다.
4. **연동(Integration)** 탭에서, **파트너 활성화** 토글을 켜세요.
6. X Ads 계정으로 로그인합니다.

</Accordion>

## X Ads와 앱스플라이어 간의 수치 차이

앱스플라이어와 X Ads는 가깝게 협업하고 있지만, X Ads 대시보드와 앱스플라이어 대시보드/리포트 사이에 수치 차이가 발생할 수 있습니다.

아래는 광고주가 알아야 하는, 수치 차이에 대한 흔한 이유들입니다.

| 1. 일으키다. 2. 발생시키다. | X Ads | 앱스플라이어 |
| --- | --- | --- |
| **어트리뷰션 기간** | X Ads는 클릭-쓰루와 뷰-쓰루 어트리뷰션 모두 사용자가 어트리뷰션 윈도우를 설정할 수 있게 허용합니다. 기본 설정으로는 클릭-쓰루 14일, 뷰-쓰루 1일 입니다. | 만약 X Ads에 대한 앱스플라이어 어트리뷰션 룩백 윈도우를 X Ads에서의 값과 다르게 설정해두었다면, 수치 차이가 발생할 수 있습니다. |
| 멀티-채널 소스 어트리뷰션 | X Ads의 어트리뷰션은 다른 소스에 상관없이, 위에 설명된 대로 작동합니다. |  |
| 시간대 차이 | X Ads의 시간대는 광고주의 앱이 설정된 시간대로 지정됩니다. | 앱스플라이어의 기본 시간대는 UTC±00:00 이지만, 광고주가 원하는대로 어떤 시간대로도 설정될 수 있습니다. |
| **인스톨 시간 차이** | X Ads는"engagement time"으로 불리는 클릭 시간을 기준으로 인스톨을 표시합니다. | 앱스플라이어는 앱 최초 실행 시간을 표시합니다. |
| **어트리뷰션 터치 유형** | X Ads의 어트리뷰션은 자체 클릭과 노출을 기반으로 합니다. | 앱스플라이어는 클릭-쓰루 어트리뷰션을 뷰-쓰루 어트리뷰션보다 우선합니다. 만약 X Ads가 광고 노출을 집계했고, 앱스플라이어는 클릭-쓰루 어트리뷰션 윈도우 내의 또 다른 클릭을 인지했다면, 앱스플라이어 대시보드에서는 다른 소스에서의 클릭으로 어트리뷰션 됩니다. X Ads에서는, 해당 광고 노출로 어트리뷰션되고 X Ads 대시보드에 표시됩니다. |
| **X Ads 데이터 공유 설정** | X Ads는 사용자가 <Anchor target="_blank" href="https://twitter.com/settings/account/personalization">자신의 개인 정보를 제 3자에 공유 금지 설정</Anchor>을 허용합니다. 이 데이터는 그들이 상호작용한 광고도 포함합니다.<br /><br />X Ads 대시보드의 수치는 데이터 공유를 금지한 사용자를 포함한 모든 인게이지먼트를 반영합니다. | 앱스플라이어는 이런 X Ads 사용자들을 통합 데이터에서 표시하지만, 사용자 단계 로데이터에서는 리포트하지 않습니다 (<Anchor target="_blank" href="/marketers/ko/docs/x-ads-formerly-twitter-ads-setup-guide-overview#x-ads-사용자-개인정보-보호">상세 설명</Anchor>). |
| **X Ads 리인게이지먼트 로직** | X Ads는 순 사용자 수를 계산합니다. 유저가 동일 캠페인에 두 번 이상 참여하는 경우, X Ads는 유저 참여 건수를 전환한 건으로 표기합니다. | 앱스플라이어는 각 리인게이지먼트 건을 계수하며, 이 경우, 전환을 복수 건으로 기록합니다. |

> 📘 **참고**
>
> <Anchor target="_blank" href="/marketers/ko/docs/implement-validation-rules-to-prevent-fraud">앱스플라이어의 유효성 검증 규칙</Anchor>에 따라, 일부 설치는 X Ads에 표시되지만 앱스플라이어 대시보드에는 표시되지 않기 때문에, 대시보드에서 결과가 다를 수 있습니다.

<div data-zendesk-anchors="twitter-ads-faq-and-discrepancies=x-ads-%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8-%EB%B0%8F-%EB%B6%88%EC%9D%BC%EC%B9%98 h_01HE7S15F9YR28FBA1TYCE3N0X=x-ads-%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8-%EB%B0%8F-%EB%B6%88%EC%9D%BC%EC%B9%98 h_01HE7S15F9NSQJSP268B0WF0JP=who-can-perform-the-twitter-setup-on-appsflyer h_01HE7S15F9PFZ8CATJC5YWC6QP=what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer h_01HE7S15F989Y94YFJ7TGK7QN5=do-the-account-owner-and-the-team-members-see-the-same-twitter-data h_01HE7S15F9GNWTK2N50GAHN52Q=how-do-i-disconnect-twitter-from-appsflyer h_01HE7S15F9CE4F29R97EVCG791=is-it-possible-to-attribute-installs-to-multiple-twitter-accounts h_01HE7S15F9G4M44CB2Q1KQMJPJ=any-special-instructions-for-agencies h_01HE7S15F9VG8XMJE7YSNN245P=%EC%B0%B8%EA%B3%A0 h_01HE7S15F9A7BBAW8BNN6H4AKQ=do-you-make-twitters-raw-data-available-to-agencies h_01HE7S15F9MM26SGKMAPGDH9F8=im-clicking-save-close-but-twitters-configuration-is-not-saved-help h_01HE7S15F923NKTTCS3Z1C40B5=how-can-i-set-up-retargeting-campaigns-with-twitter h_01HE7S15F931EWS48QVCQYPBCH=does-retargeting-affect-inapp-events-sending-to-twitter h_01HE7S15F98VN1TS99751S34C5=how-can-i-stop-measuring-twitter-attributions h_01HE7S15F9MEKBKAQ3NA76TFKY=can-an-agency-measure-twitter-attributions-for-advertisers h_01HE7S15F921V3T885F39VSPCQ=can-an-agency-configure-inapp-events-for-twitter for-how-long-do-you-keep-twitter%E2%80%99s-userlevel-data=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F90RXSWJ7HV3GSJB65=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F9B39KV628NSD29P6P=why-do-i-see-duplicated-cost-data h_01HE7S15F9N3CCJEMAD2QB38F9=im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message discrepancies-between-twitter-and-appsflyer=x-ads%EC%99%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EA%B0%84%EC%9D%98-%EC%88%98%EC%B9%98-%EC%B0%A8%EC%9D%B4 h_01HE7S15F9YWCY883DP9TEGQXK=x-ads%EC%99%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EA%B0%84%EC%9D%98-%EC%88%98%EC%B9%98-%EC%B0%A8%EC%9D%B4 h_01HE7S15FAPS2696J3KQG3P3ME=%EC%B0%B8%EA%B3%A0-1" />
