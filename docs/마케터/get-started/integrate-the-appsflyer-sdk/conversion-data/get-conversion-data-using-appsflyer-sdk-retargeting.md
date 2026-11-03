---
title: 앱스플라이어 SDK를 사용하여 전환 데이터 가져오기–리타겟팅
metadata:
  keywords:
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
  created_at: '2021-11-09T10:17:47Z'
  edited_at: '2026-10-14T10:35:35Z'
  id: 4410481260817
  locale: ko
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/ko/articles/4410481260817
---
> **한눈에 보기:** 리어트리뷰션과 리인게이지먼트가 SRN 및 비 SRN 유저 여정에 대한 전환 데이터에 어떻게 반영되는지 알아보세요.

## 리타겟팅 전환

리타겟팅에는 리어트리뷰션 또는 리인게이지먼트의 두 가지 유형의 전환이 포함됩니다.

> 👍 **팁**
>
> 리타겟팅을 위한 전환 데이터가 항상 전환 유형을 명확하게 나타내는 것은 아닙니다. [대체 전환 데이터 소스](#대체-전환-데이터-소스) 참조.

## SRN을 사용한 리어트리뷰션

SRN을 통해 유저가 리어트리뷰션되는 경우 전환 데이터 페이로드는 이것이 리타겟팅 캠페인임을 나타내지 않습니다. SRN은 어트리뷰션 링크를 사용하지 않으므로 어트리뷰션 링크에 `is_retargeting=true` 파라미터를 설정할 방법이 없습니다. **리타겟팅을 지원하는 SRN**의 경우, 앱스플라이어는 유저를 리어트리뷰션해야 하는지 여부를 결정합니다.

이것은 SDK 수준에서 인스톨이 리타겟팅 캠페인에서 발생하는지 확인할 방법이 없다는 것을 의미합니다. 유일한 방법은 리타겟팅 캠페인을 나타내도록 캠페인 이름을 설정하는 것입니다.

> 📘 **참고**
>
> 리타겟팅을 나타내도록 캠페인 이름을 설정하는 것은 **완벽한 방법이 아닙니다**. [자세한 내용은 예제](#유저-유입-및-리어트리뷰션의-혼합-예시)를 참조하십시오.

## 일반 애드 네트워크를 통한 리어트리뷰션

애드 네트워크에 대한 어트리뷰션은 어트리뷰션 링크에 의존합니다. 일반 어트리뷰션 링크든 원링크든 리타겟팅을 사용하면 어트리뷰션 링크에는 항상 `is_retargeting=true` 파라미터가 설정되어 있습니다.

<div id="retargeting-campaign-with-criteo" />

<Accordion title="Criteo를 통한 리타겟팅 캠페인">

#### 어트리뷰션 링크

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

#### 전환 데이터 페이로드

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "criteo_int",
      "retargeting_conversion_type": "re-attribution",
      "adset_id": null,
      "campaign_id": null,
      "af_reengagement_window": "30d",
      "install_time": "2018-12-01 23:13:03.126",
      "adgroup_id": null,
      "redirect": "false",
      "af_sub5": null,
      "click_time": "2018-11-18 20:02:31.559",
      "agency": null,
      "cost_cents_USD": "0",
      "is_retargeting": "true",
      "af_cpi": null,
      "af_click_lookback": "30d",
      "af_siteid": null,
      "idfa": "68**********************************",
      "http_referrer": null,
      "orig_cost": "0.0",
      "af_sub4": null,
      "adset": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* `retargeting_conversion_type` 파라미터 - 이 파라미터는 리타겟팅 유형을 나타냅니다. 리어트리뷰션, 리인게이지먼트 또는 없음일 수 있습니다.
* `is_retargeting: true` 파라미터 - 이 파라미터는 인스톨이 리어트리뷰션된 인스톨임을 나타냅니다
* `af_reengagement_window`: 리인게이지먼트 어트리뷰션 윈도우는 이벤트가 **재참여한 유저**에게 어트리뷰션될 수 있는 일수입니다. 이는 리어트리뷰션 전환이므로 이 파라미터는 중복됩니다.

</Accordion>

## 디퍼드 딥링킹을 사용한 리어트리뷰션

종종 리어트리뷰션의 정의에 따라 앱을 설치하지 않은 리어트리뷰션된 유저를 딥링크하려고 합니다. 예를 들어 앱을 삭제한 유저를 다시 불러오는 것을 목표로 하는 캠페인을 설정합니다. 캠페인이 제품 또는 서비스를 홍보하고 여러분은 광고하는 제품 또는 서비스와 관련된 콘텐츠를 유저에게 제공하려고 합니다.

이것을 디퍼드 딥링킹이라고 부릅니다. 디퍼드 딥링킹을 위한 전환 데이터 페이로드는 `onConversionDataSuccess` 메서드에서 비롯됩니다.

<div id="deferred-deep-linking-with-srns" />

<Accordion title="SRN의 디퍼드 딥링킹">

SRN 캠페인에 정의된 딥링크 파라미터는 SRN 외부에서 사용할 수 없습니다. 여기에는 `af_dp` 파라미터가 포함되며, 앱의 스킴 경로가 있습니다. 따라서 디퍼드 딥링킹을 구현하려면 SRN 캠페인에 추가 로직을 적용해야 합니다. `onConversionSuccess` 응답에 캠페인, 광고 세트, 광고 그룹과 같은 데이터를 사용하여 프로그래밍 방식으로 유저를 리디렉션합니다.

#### Meta 광고와의 디퍼드 딥링킹에 대한 전환 데이터

<Tabs>
<Tab title="안드로이드">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"Non-organic",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

</Tab>

<Tab title="iOS">

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,  
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

</Tab>
</Tabs>

getConversionData 응답에서 캠페인, 광고 세트 등과 같은 데이터를 사용하여 프로그래밍 방식으로 유저를 리디렉션하고 관련 콘텐츠를 제공합니다.

> 📄 **예시**
>
> 이 앱은 스포츠웨어를 전문으로 하는 이커머스 앱입니다. 앱을 설치하지 않은 유저는 광고에 참여하고 앱을 설치합니다. 앱이 실행되면 SDK가 전환 데이터를 반환합니다. 개발자는 앱이 앱 내에서 **여름 러닝화 컬렉션**(캠페인) 활동을 열도록 하고 **여성용 러닝화** 카테고리(광고 세트)를 제공합니다.

</Accordion>

<div id="deferred-deep-linking-with-attribution-links" />

<Accordion title="어트리뷰션 링크를 사용한 디퍼드 딥링킹">

유저를 딥링크하는 방법에는 세 가지가 있습니다.

#### URI 스킴

URI 스킴을 사용할 때 어트리뷰션 링크와 원링크 모두에 대해 어트리뷰션 링크와 페이로드는 다음과 같습니다.

**어트리뷰션 링크**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**원링크**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**페이로드**

```json
{
      "af_deeplink": true,
      "campaign": "campaign_name",
      "media_source": "media_source_name",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-30 23:59:09",
      "install_time": "2018-12-30 23:59:39.330",
      "agency": null,
      "cost_cents_USD": "0",
      "adset": "AD_SET_NAME",
      "ad_id": "AD_ID",
      "af_siteid": null,
      "http_referrer": null,
      "af_cpi": null,
      "af_sub5": null,
      "af_sub4": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink: true` - 이 파라미터가 나타나고 true로 설정되면 `scheme` 및 `host` 필드를 찾습니다.
* `scheme` 및 `host` - 이 필드는 어트리뷰션 링크에서 `af_dp` 파라미터를 가져오며 유저가 딥링크되어야 하는 스킴과 액티비티를 나타냅니다

#### iOS 유니버설 링크 및 안드로이드 앱 링크

이것은 딥링킹을 수행하는 세 가지 방법 중 다른 두 가지입니다.

유니버설 링크 또는 앱 링크를 사용할 때 원링크 및 페이로드는 다음과 같습니다.

**원링크**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**페이로드**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "Non-organic",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* `shortlink`필드 - 유저가 유입된 특정 원링크를 나타내는 필드입니다. 개발자가 액티비티를 시작하고 콘텐츠를 제공하는 방법을 알 수 있도록 도와줍니다. `campaign`와 같은 다른 필드도 이 목적으로 사용할 수 있습니다.

  > 🚧 **중요!**
  >
  > 긴 원링크를 사용할 때 페이로드에 `shortlink` 필드가 나타나지 않습니다.
  >
  > 두 경우 모두(짧거나 긴 원링크) 액티비티를 나타내는 커스텀 파라미터를 추가하는 것이 좋습니다. 예를 들어 `&deep_link_activity=shoes_cateogry`


> 📘 **참고**
>
> 유니버설 링크 및 앱 링크 사용은 원링크에서만 가능합니다.

</Accordion>

## SRN을 사용한 리인게이지먼트

리어트리뷰션 캠페인과 무척 유사하게 유저가 SRN을 통해 리인게이지먼트할 때 전환 데이터는 이것이 리인게이지먼트 캠페인임을 나타내지 않습니다. 리인게이지먼트 캠페인을 나타내도록 캠페인 이름을 설정할 수 있습니다.

## 일반 애드 네트워크를 통한 리인게이지먼트

여기에서도 전환 데이터 페이로드는 유저가 리인게이지먼트 캠페인에서 왔다는 것을 나타내지 않습니다. 이 제한을 극복하려면 리인게이지먼트를 나타낼 수 있게 캠페인 이름을 설정해야 합니다.

## 딥링킹을 통한 리인게이지먼트

리인게이지먼트의 주요 부분은 유저를 특정 액티비티로 보내는 것입니다. 예를 들어 일부 제품이나 판매를 광고하는 경우입니다. 이 경우 광고를 클릭한 유저를 이 제품 또는 판매에 대한 앱 액티비티로 보내려고 합니다.

이렇게 하려면 딥링킹을 사용합니다. 딥링킹에서 전환 데이터는 정말 중요합니다. 개발자가 유저 경험을 커스터마이즈하고 올바른 액티비티로 보내는 데 필요한 정보를 보유합니다.

<div id="reengagement-deep-linking-with-srns" />

<Accordion title="리인게이지먼트: SRN을 사용한 딥링킹">

리인게이지된 유저가 SRN에서 온 경우 전환 데이터를 사용할 수 없습니다. 개발자는 SRN 메서드를 사용하여 앱 실행 시 가져와야 합니다.

</Accordion>

<div id="reengagement-deep-linking-with-ad-networks" />

<Accordion title="리인게이지먼트: 애드 네트워크를 사용한 딥링킹">

유저가 리인게이지하고 앱이 실행되면 `onAppOpenAttribution` 메서드에서 다음 전환 데이터를 사용할 수 있습니다.

iOS와 안드로이드에서 단축 버전의 원링크를 사용할 때, 전환 데이터는 링크상에 있는 모든 파라미터의 구조화된 맵입니다.

예시:

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* 앱 개발자는 `af_dp` 및 캠페인 이름과 같은 파라미터를 사용하여 유저를 특정 액티비티로 보내고 관련 콘텐츠를 제공할 수 있습니다.

> 🚧 **중요!**
>
> 단축 버전의 원링크를 사용하는 것을 권장합니다. 더 자세히 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/understand-onelink-short-vs-long-urls">여기</Anchor>를 클릭하십시오.

단축 버전의 원링크를 사용하는 또 다른 이유는 긴 버전이 반환하는 전환 데이터 구조 때문입니다. 긴 버전을 사용할 때 전환 데이터는 긴 원링크 전체를 포함하는 `link`라는 단일 필드가 있는 맵입니다.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

## 대체 전환 데이터 소스

* Push API는 리어트리뷰션 또는 리인게이지먼트를 나타내는 상세한 전환 페이로드를 제공합니다. Push API 페이로드에는 `re_targeting_conversion_type`라는 필드가 포함됩니다. 이 필드는 전환 유형(리어트리뷰션 또는 리인게이지먼트)을 나타냅니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/push-api-streaming-raw-data">Push API 가이드</Anchor>를 참조하십시오.
* 로데이터 리포트에는 전환 유형에 대한 지표도 포함되어 있습니다. 리타겟팅 전환에 대한 로데이터 리포트에는 ***이벤트 이름*** 열이 있습니다. 이 열의 값은 전환 유형에 따라 ***리인게이지먼트*** 또는 ***리어트리뷰션***입니다.

## 유저 유입 및 리어트리뷰션의 혼합 예시

> 📄 **예시**
>
> 1. 어떤 유저가 앱을 설치했다가 삭제합니다. 인스톨 행동으로 인해 이 유저는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 윈도우</Anchor>에 들어갑니다. Meta 광고에서 유저 유입(리타겟팅 아님) 캠페인을 설정합니다. 또한 앱스플라이어와 Meta 광고와의 연동을 설정하여 리타겟팅을 허용합니다.
>
>    리어트리뷰션 윈도우에서 유저는 광고를 보고 클릭한 다음 앱을 다시 설치합니다. 앱스플라이어의 관점에서 이 유저는 리어트리뷰션된 유저입니다.
>
>    이는 두 가지 요인에 기인합니다.
>
>    1. Meta 광고를 사용한 설정을 통해 리타겟팅이 가능함
>    2. 유저가 리어트리뷰션 윈도우 안에 있음
>    이 경우 캠페인 이름은 리어트리뷰션을 표시하지 않습니다.
> 2. 동일한 예를 들어 보겠습니다. 이 경우에는 유저가 리어트리뷰션 윈도우 밖에 있습니다. 이 경우 인스톨은 신규 논오가닉 인스톨입니다.
> 3. 다른 예를 들어보겠습니다. Meta 광고에서 리타겟팅 캠페인을 설정했습니다. 일부 유저가 캠페인을 방문하여 앱을 설치합니다. 그러나 이러한 유저는 처음으로 앱을 설치합니다. 이러한 유저는 리어트리뷰션된 유저로 간주되지 않습니다. 대신 앱스플라이어는 이들을 유저 유입 캠페인에서 온 유저로 간주합니다.

<div data-zendesk-anchors="retargeting-conversion=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%A0%84%ED%99%98 h_01EHQ74JS84509GT6M93SZA4HX=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%A0%84%ED%99%98 reattribution-with-srns=srn%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%9C-%EB%A6%AC%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 reattribution-with-regular-ad-networks=%EC%9D%BC%EB%B0%98-%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EB%A5%BC-%ED%86%B5%ED%95%9C-%EB%A6%AC%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 attribution-link=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC conversion-data-payload=%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%8E%98%EC%9D%B4%EB%A1%9C%EB%93%9C reattribution-with-deferred-deep-linking=%EB%94%94%ED%8D%BC%EB%93%9C-%EB%94%A5%EB%A7%81%ED%82%B9%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%9C-%EB%A6%AC%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 conversion-data-for-deferred-deep-linking-with-facebook=meta-%EA%B4%91%EA%B3%A0%EC%99%80%EC%9D%98-%EB%94%94%ED%8D%BC%EB%93%9C-%EB%94%A5%EB%A7%81%ED%82%B9%EC%97%90-%EB%8C%80%ED%95%9C-%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0 uri-schemes=uri-%EC%8A%A4%ED%82%B4 ios-universal-links-and-android-app-links=ios-%EC%9C%A0%EB%8B%88%EB%B2%84%EC%84%A4-%EB%A7%81%ED%81%AC-%EB%B0%8F-%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EC%95%B1-%EB%A7%81%ED%81%AC reengagement-with-srns=srn%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%9C-%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8 reengagement-with-regular-ad-networks=%EC%9D%BC%EB%B0%98-%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EB%A5%BC-%ED%86%B5%ED%95%9C-%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8 reengagement-with-deep-linking=%EB%94%A5%EB%A7%81%ED%82%B9%EC%9D%84-%ED%86%B5%ED%95%9C-%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8 alternative-conversion-data-sources=%EB%8C%80%EC%B2%B4-%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4 examples-of-mixed-user-acquisition-and-reattribution=%EC%9C%A0%EC%A0%80-%EC%9C%A0%EC%9E%85-%EB%B0%8F-%EB%A6%AC%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%9D%98-%ED%98%BC%ED%95%A9-%EC%98%88%EC%8B%9C" />
