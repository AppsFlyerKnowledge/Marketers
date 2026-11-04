---
title: Pinterest 마케팅 파트너 연동
metadata:
  keywords:
    - Pinterest
    - PMP
    - Advertisers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-12-08T16:05:33Z'
  edited_at: '2026-10-14T10:29:56Z'
  id: 217408966
  locale: ko
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/ko/articles/217408966
---
> **한눈에 보기:** Pinterest 마케팅 파트너(PMP)가 Pinterest에 어트리뷰션된 사용자의 설치 데이터를 수신할 수 있도록 지원합니다.

모든 PMP는 공식 PMP여야 하며, 백엔드에서 앱스플라이어의 승인도 받아야 합니다.

앱스플라이어가 PMP에 포스트백을 보내려면 앱스플라이어 계정 이름을 값으로 가진 af\_mp= 파라미터를 어트리뷰션 링크에 추가해야 합니다.

<div id="note" />

> 📄 **예시**
>
> <Tabs>
> <Tab title="안드로이드">
>
> ```http
> https://app.appsflyer.com/com.king.candycrushsaga?pid=pinterest_int&clickid={click_id}
> &af_adset={ad_group_name}&af_adset_id={ad_group_id}&af_ad={creative_name}&af_ad_id=
> {creative_id}&af_siteid={publisher}&c={campaign_name}&af_c_id={campaign_id}&af_ad=
> {ad_group_id}&af_ad_id={creative_id}&sha1_advertising_id={sha1_advertising_id}&tracking=
> {limit_ad_tracking}&appid={app_id}&timestamp={click_timestamp}&af_mp=bidalgo
> ```
>
> </Tab>
>
> <Tab title="iOS">
>
> ```http
> https://app.appsflyer.com/id340954503?pid=pinterest_int&clickid={click_id}
> &af_adset={ad_group_name}&af_adset_id={ad_group_id}&af_ad={creative_name}&af_ad_id=
> {creative_id}&af_siteid={publisher}&c={campaign_name}&af_c_id={campaign_id}&af_ad=
> {ad_group_id}&af_ad_id={creative_id}&sha1_advertising_id={sha1_advertising_id}&tracking=
> {limit_ad_tracking}&appid={app_id}&timestamp={click_timestamp}&af_mp=bidalgo
> ```
>
> </Tab>
> </Tabs>
>

지원되는 PMP 파트너는 다음과 같습니다.

* Bidalgo
* Bidsaas(Bidalgo)

<div data-zendesk-anchors="01JFSZQG46FGJJTK893PKSKA2W=%EC%98%88%EC%8B%9C" />
