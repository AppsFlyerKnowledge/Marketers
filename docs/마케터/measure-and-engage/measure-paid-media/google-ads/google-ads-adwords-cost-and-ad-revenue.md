---
title: Google Ads(AdWords)—비용 및 광고 수익
metadata:
  keywords:
    - Advertisers
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-20T10:01:42Z'
  edited_at: '2026-10-14T10:32:11Z'
  id: 4417309205521
  locale: ko
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ko/articles/4417309205521
---
> **요약: 한 눈에 보기: 앱스플라이어에서 구글 애즈 비용 및 광고 수익 데이터를 활성화합니다.**

<div id="cost-clicks-and-impressions" />

## 비용, 클릭 수, 노출 수

비용 연동은 다음의 집약형 데이터를 제공합니다.

* 캠페인, 광고 세트, 지역/국가 및 채널 수준에 대한 비용 데이터입니다. 지원되는 기준, 지표 및 기능에 대한 세부 정보를 얻으려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요.  
  **참고:** 비용 데이터를 사용하려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> 구독이 필요합니다.
* 클릭 수에 대한 데이터, 노출 횟수, 보강된 데이터(키워드, 캠페인 이름, 광고 세트).

> 📘 **참고사항**
>
> * MCC 계정이 지원됩니다.
> * 스냅챗의 캠페인 설정이 iOS 또는 안드로이드 앱용인지 확인하세요. 둘 다는 아닙니다.
> * 비용, 클릭수, 노출수에 대한 데이터는 현재 Google Ads API의 제한사항으로 인해 사전 등록 캠페인에 사용할 수 없습니다.

앱스플라이어 대시보드에서 구글 애즈 비용, 클릭 및 노출 데이터를 확인하려면 구글 애즈 파트너 연동 설정 페이지를 통해 연결하십시오. 연결이 완료되면 앱스플라이어는 모든 현재 캠페인에 대한 구글 애즈 비용 금액, 클릭 수 및 노출 수를 쿼리하기 시작합니다.

<Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">Google Ads에서 비용을 설정하는</Anchor> 방법에 대해 자세히 알아보세요.

Google에서 클릭 및 뷰를 정의하는 방법에 대한 자세한 정보를 읽으십시오.

<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6163740">Google Ads 제한사항에</Anchor> 대해 자세히 알아보세요.

**설정 후 몇 시간 내에 데이터가 들어와야 합니다**.

> 👍 **팁**
>
> 사용자는 구글 애즈 대시보드의 오른쪽 상단에 표시되는 이메일 주소를 확인하여 올바른 구글 애즈 계정으로 로그인했는지 확인할 수 있습니다.
>
> ![short.png](https://files.readme.io/670a6e36e9bb8c3bfe2a14649d29e2d1c52ee3205c147160036ea57bbb24ef53-51912707985553.png)
>  만약 해당 구글 애즈 계정이 MCC 계정의 하위 계정이라면, 우측 상단의 ID는 MCC 계정 ID이고, 하위 계정 ID는 좌측 상단 코너에 있습니다.
>
> 만약 올바른 계정이 아니라면, 계정에서 로그아웃 한 후 다른 구글 계정의 이메일 주소를 사용하여 다시 로그인하십시오.

<div id="cost-data-sync-status" />

### 비용 데이터 동기화 상태

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태</Anchor>와 앱스플라이어가 비용(및 광고 수익) 연동 상태 대시보드 또는 개별 애드 네트워크 대시보드에서 일치하는 비용 데이터를 가져온 마지막 시간을 확인합니다.

구글 애즈는 비용 데이터를 가져올 수 있도록 여러 계정을 동기화하는 것을 허용합니다. 동기화된 각 계정에 대해 앱스플라이어는 비용 연동 상태 및 앱스플라이어가 일치하는 비용 데이터를 가져온 마지막 시간을 표시합니다.

<div id="stopping-google-cost-sync" />

### 구글 비용 동기화 중지하기

**구글 비용 동기화를 중지하려면, 구글 계정 연결을 제거하십시오.**

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">비용 연동 탭으로 이동하여 Action 열에서 계정 위로 마우스를 가져가 연결 삭제를 클릭합니다.</Anchor> 삭제되면 앱스플라이어가 비용 수신을 중지합니다. 연결 삭제는 과거 데이터에 영향을 주지 않습니다.

<div id="recording-ad-revenue-with-google-ads" />

## 구글 애즈 광고 수익 기록

Google Ads(AdWords) 수익 연동은 2020년 11월 30일 현재 더 이상 사용되지 않습니다. 광고 수익 데이터의 경우 AdWords 고객은 <Anchor target="_blank" href="/marketers/ko/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>으로 마이그레이션해야 합니다.

<div id="faq" />

<Accordion title="자주 묻는 질문">

| **왜 비용 데이터를 볼 수 없습니까?**<br /><br />데이터가 표시되지 않는 데는 몇 가지 이유가 있을 수 있습니다.<ul><li>로그인 할 때 올바른 구글 계정이 사용되는지 확인하는 것이 중요합니다.<br />잘못된 구글 계정을 사용하여 로그인하면 비용 데이터를 끌어오거나 표시할 수 없습니다. 이런 경우, 반드시 구글 앱 권한에서 앱을 제거하고 올바른 계정으로 로그인해야만 합니다. 이렇게 하려면 다음 단계를 수행하십시오.<ol><li>다음 URL을 클릭하십시오: <Anchor target="_blank" href="https://myaccount.google.com/permissions">https://myaccount.google.com/permissions</Anchor></li><li>구글에서 AppsFlyer Cost를 제거하고 다시 로그인하십시오.</li></ol></li><li>경우에 따라 대행사 비용 통합이 사용 설정되어 있지만 로그인한 대행사 사용자가 올바른 Google Ads 고객 ID에 액세스할 수 없기 때문에 비용이 차감되지 않습니다. 이로 인해 광고주에게 불완전한 비용 데이터가 표시됩니다.</li></ul>비용 탭에 로그인하는 대행사 사용자가 통합 탭에 설정된 Google Ads 고객 ID에 액세스할 수 있는지 확인합니다.<br /><br />[<Image alt="" src="https://files.readme.io/2d17b3dad78e02c76253f30db0c15c18eb837b531becabc07ccad274258c2c61-49938966132753.png" width="457px" />](https://files.readme.io/2d17b3dad78e02c76253f30db0c15c18eb837b531becabc07ccad274258c2c61-49938966132753.png)<ul><li>iOS 검색 또는 안드로이드 랜딩 페이지 캠페인에서 공백 또는 특수 문자를 사용하면 비용 데이터를 클릭 데이터와 일치시키는데 문제가 생기고 비용 보고가 누락될 수 있습니다.</li><li>비용이 이미 수집된 후 대행사가 비용 통합을 비활성화했지만 광고주에게 여전히 활성 비용 통합이 있는 경우 데이터는 대행사가 통합을 비활성화한 날부터 광고주와 연결됩니다.</li></ul> |
| --- |
| **지역 기반 클릭 데이터는 어디에 있나요?**<br /><br />어떤 경우에는 앱스플라이어가 구글로부터 지역별 클릭 데이터를 부분적으로만 받습니다. 이러한 상황이 발생하면 앱스플라이어는 지리 정보가 없는 다른 구글 소스를 통해서라도 누락된 클릭 정보를 완성합니다. 따라서 지역 기준으로 조회했을 때, 구글 캠페인의 총 클릭 수가 다른 조회 기준에서 확인했을 때의 같은 수치와 일치하지 않을 수 있습니다. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| 비활성 및 활성 캠페인 | <ul><li>인스톨을 위한 앱 캠페인(ACI 캠페인 유형)</li><li>참여를 위한 앱 캠페인(ACE 캠페인 유형)</li></ul> |
|  |  |

</Accordion>

> 📄 **참고 항목**
>
> * iOS 14 관련 고려 사항은 <Anchor target="_blank" href="/marketers/ko/docs/get-skan-postback-data-from-google-ads">Google Ads SKAdNetwork와 앱스플라이어의 상호운용성</Anchor>을 참조하세요.

<div data-zendesk-anchors="cost-clicks-and-impressions=%EB%B9%84%EC%9A%A9-%ED%81%B4%EB%A6%AD-%EC%88%98-%EB%85%B8%EC%B6%9C-%EC%88%98 h_01HDP2SMHJ26S1BCER3KKZ8H14=%EB%B9%84%EC%9A%A9-%ED%81%B4%EB%A6%AD-%EC%88%98-%EB%85%B8%EC%B6%9C-%EC%88%98 h_01HDP2SMHJB5YE5PCWVJVBAKHD=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HDP2SMHJF86QK9CJTVABKTYW=%ED%8C%81 cost-data-sync-status=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%83%81%ED%83%9C h_01HDP2SMHJT8Z6DP7BHC0Y5RRN=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%83%81%ED%83%9C stopping-google-cost-sync=%EA%B5%AC%EA%B8%80-%EB%B9%84%EC%9A%A9-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%A4%91%EC%A7%80%ED%95%98%EA%B8%B0 h_01HDP2SMHJPEDKKZF9SBXW56KG=%EA%B5%AC%EA%B8%80-%EB%B9%84%EC%9A%A9-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%A4%91%EC%A7%80%ED%95%98%EA%B8%B0 recording-ad-revenue-with-google-ads=%EA%B5%AC%EA%B8%80-%EC%95%A0%EC%A6%88-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EA%B8%B0%EB%A1%9D h_01HDP2SMHKC9TSZZZPFFNK8TPH=%EA%B5%AC%EA%B8%80-%EC%95%A0%EC%A6%88-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EA%B8%B0%EB%A1%9D h_01HDP2SMHK8NH6M4T1A2Y79P55=faq h_01HDP2SMHKPDEE07H8WAP212TZ=traits-and-limitations h_01HDP2XBSEJVQ5G0MD0V5R05CM=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
