---
title: 마케터용 크로스 프로모션 어트리뷰션
metadata:
  keywords:
    - tracking
    - Advertisers
    - Cross Promotion
    - cross-promotion
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2017-08-30T13:26:03Z'
  edited_at: '2026-10-14T10:26:30Z'
  id: 115004481946
  locale: ko
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ko/articles/115004481946
---
> **한눈에 보기:** 요약: 소유한 다른 앱에서 앱을 프로모션하는 크로스 프로모션 캠페인의 인스톨 성과를 측정합니다.

![CrossPromo_userJourney](https://files.readme.io/4ecc5b536021355247c51f1a19b23d71623da9f9578387622d6c6f0a57d4801b-4404615401489.png)

<div id="about-cross-promotion" />

## 크로스 프로모션 소개

크로스 프로모션 캠페인은 기존 앱을 홍보하거나 회사에서 출시한 새 앱으로 사용자를 안내하는 최상의 방법 중 하나입니다. 크로스 프로모션이 온드 미디어에서 광고되므로 [기기 ID 매칭](/docs/cross-promotion-attribution-for-marketers#크로스-프로모션-어트리뷰션하기)을 사용하여 새 인스톨을 결정적으로 어트리뷰트할 수 있습니다.

다음 이미지는 온드 미디어(**af\_cross\_promotion**) 및 기타 미디어소스에서 실행되는 캠페인에 대한 지표 분석이 포함된 프로모션한 앱의 대시보드를 보여 줍니다. 크로스 프로모션 캠페인의 인스톨 수와 전환율이 다른 미디어소스에 비해 훨씬 높은 것을 알 수 있습니다.

[![CrossPromo_mediaSource](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)

<div id="how-does-cross-promotion-work" />

### 크로스 프로모션은 어떻게 작동합니까?

1. 사용자는 회사가 소유한 기존 앱에서 크로스 프로모션 광고를 받게 됩니다. 그 광고는 회사의 또 다른 앱을 홍보하고 있습니다. 앱 광고소재는 배너, 동영상 또는 클릭 가능한 객체입니다.
2. [선택 사항] SDK는 크로스 프로모션 노출을 <Anchor target="_blank" href="/marketers/ko/docs/cross-promotion-attribution-for-developers">기록하고 앱스플라이어로 보냅니다</Anchor>.
3. 사용자가 크로스 프로모션 광고를 클릭합니다.
4. SDK는 클릭을 기록하고 사용자를 앱 스토어의 프로모션한 앱 페이지로 리디렉션합니다. SDK에서 기록한 클릭에는 이미 기기 광고 ID가 포함되어 있습니다.
5. 프로모션한 앱을 인스톨하고 실행하면, [앱스플라이어 대시보드](/docs/cross-promotion-attribution-for-marketers#프로모션한-앱-대시보드)의 미디어소스 **af\_cross\_promotion**에 새로 등록한 사용자가 표시됩니다.
   * 미디어 소스 값을 변경하려면 개발자가 원하는 값과 함께 pid라는 커스텀 파라미터를 추가해야 합니다. **참고**: 참고: 안드로이드의 경우 SDK V6.4.2+에서만 작동합니다.
   * 인스톨을 유도하는 앱인 소스 앱이 이 미디어소스의 **사이트 ID**로 나타납니다.

<div id="attributing-cross-promotion" />

## 크로스 프로모션 어트리뷰션하기

앱스플라이어를 통해 어트리뷰션 방법으로 기기 ID 매칭을 사용하여 크로스 프로모션 캠페인에서 발생하는 인스톨을 기록하고 어트리뷰트할 수 있습니다. 노출과 클릭을 모두 어트리뷰트할 수 있으므로 <Anchor target="_blank" href="/marketers/ko/docs/about-conversion-rates#마케팅-퍼널-단계-및-전환율-1">클릭률</Anchor> 또는 인스톨/노출 비율을 계산할 수 있습니다.

매칭에 사용되는 기기 식별자는 다음에 따라 달라집니다.

* 유저의 기기 및 OS 버전
* 소스 앱에서 앱스플라이어 SDK 버전

| 크로스 프로모션에 대한 기기 ID 매칭 | 기기/OS 버전 | SDK 버전 | 참고 |
| --- | --- | --- | --- |
| IDFA | iOS 9 – 14.4 | V5.0.0 이상 |  |
| IDFV | iOS 14.5 이상 | V6.0.2+ | IDFV는 자동 수집되며 개발사가 별도로 할 작업은 없습니다. |
| GAID | 구글 플레이 서비스 기능을 갖춘 안드로이드 기기 |  |  |
| OAID, 안드로이드 ID, IMEI, Fire ID | 구글 플레이 서비스 기능이 없는 안드로이드 기기 |  |  |

<div id="setting-up-cross-promotion" />

## 크로스 프로모션 설정

크로스 프로모션 어트리뷰선을 설정하는 과정은 마케터와 개발사가 협력하여 앱스플라이어 SDK에 추가 코드를 구현해야 할 것을 필요로 합니다.

마케터와 개발자의 흐름은 다음과 같습니다:

| 단계 | 역할 | 작업 | 세부 정보 |
| --- | --- | --- | --- |
| 1 | 마케터 | 크로스 프로모션 캠페인을 실행할 기존 앱을 결정합니다. | 인스톨로 어트리뷰트된 소스 앱이 프로모션한 앱의 대시보드에 **사이트 ID**로 표시됩니다. |
| 2 | 마케터 | 룩백 윈도우, 광고 세트 이름 및 구독자 파라미터와 같은 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">추가 파라미터</Anchor>를 추가할지 여부를 결정합니다. 추가 파라미터 이름과 값을 개발사에 보냅니다. |  |
| 3 | 개발자 | SDK에서 코드를 구현합니다. | 개발자 문서는 <Anchor target="_blank" href="/marketers/ko/docs/cross-promotion-attribution-for-developers">여기</Anchor>에서 확인할 수 있습니다. |
| 4 | 마케터 | [프로모션한 앱의 대시보드](/docs/cross-promotion-attribution-for-marketers#프로모션한-앱-대시보드)에서 크로스 프로모션 캠페인의 트래픽을 보고 그에 따라 캠페인을 최적화합니다. |  |
| 5 [선택 사항] | 마케터 | [사용자정의 대시보드](/docs/cross-promotion-attribution-for-marketers#커스텀-대시보드)를 만들어 크로스 프로모션 트래픽을 비교하고 계정 사용자와 데이터를 공유할 수 있습니다. |  |

<div id="viewing-cross-promotion-data" />

## 크로스 프로모션 데이터 보기

<div id="promoted-app-dashboard" />

### 프로모션한 앱 대시보드

프로모션한 앱의 대시보드를 사용하면 프로모션한 앱에 최상의 트래픽을 보내는 소스 앱을 확인할 수 있습니다.

**소스 앱의 트래픽 비교 방법:**

1. **Overview(개요)** 로 이동합니다.
2. **af\_cross\_promotion** 미디어 소스(또는 커스텀 미디어 소스)를 선택합니다.

<div id="analysis" />

#### 분석

동일한 프로모션한 앱에 대해 광고를 서비스하는 여러 기존 앱의 인스톨, 클릭, 노출 및 전환율 데이터를 보고 선호도 분석을 수행할 수 있습니다. 전환율이 가장 좋은 소스 앱(사이트 ID)은 프로모션한 앱과 가장 유사하며 사용자가 다운로드하고 설치할 확률이 가장 높습니다. 이러한 통찰력을 바탕으로 크로스 프로모션 캠페인을 최적화할 수 있습니다.

<div id="example" />

> 📄 **예시**
>
> 당신은 PlayIt Gaming International의 게임 앱 마케터입니다. 여러분은 당구라는 새로운 앱을 출시했습니다. 기존 앱 중 하나에서 실제로 당구 광고를 클릭하는 사용자가 몇 명인지 확인하기 위해 크로스 프로모션 테스트를 실행하기로 결정합니다. 이 캠페인은 볼링에서 7.92%의 전환율로 잘 진행되므로 골프에도 광고하기로 결정합니다.
>
> 대시보드를 보면 골프 전환율이 18.22%로 볼링 전환율보다 훨씬 높은 것을 알 수 있어 이를 통해 Golfing과 홍보 앱인 BIlliards 사이의 선호도가 더 높다는 것을 확인할 수 있습니다.
>
> [![CrossPromo_conversionRate](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)
>
> 이러한 통찰력을 바탕으로 캠페인을 다음과 같이 최적화할 수 있습니다.
>
> * 골프에 대한 전면적인 크로스 프로모션 캠페인을 실행합니다.
> * 클릭뿐만 아니라 <Anchor target="_blank" href="/marketers/ko/docs/measure-view-through-engagements#뷰쓰루-어트리뷰션-흐름">노출 어트리뷰트</Anchor>도 시작합니다. 처음에 클릭만 측정하도록 캠페인을 설정했으므로 클릭하지 않고 광고를 본 후 나중에 설치하는 사용자의 설치는 논오가닉이 아닌 오가닉 설치로 간주됩니다. 이는 각 소스 앱의 캠페인 성과에 대한 완전한 그림을 아직 가지고 있지 않다는 것을 의미합니다.

<div id="custom-dashboard" />

### 커스텀 대시보드

프로모션된 앱의 대시보드를 통해 어떤 소스 앱이 트래픽을 가장 잘 발생시키는지 완벽하게 파악할 수 있습니다. 그러나 여러 앱을 홍보하는 데 사용되는 단일 기존 앱의 성능을 평가하려면 어떻게 해야 할까요? 이를 위해서는 필요한 작업을 수행할 수 있게 사용자정의 대시보드가 있어야 합니다.

<Anchor target="_blank" href="/marketers/ko/docs/custom-dashboards">사용자정의 대시보드</Anchor>를 사용하면 크로스 프로모션 트래픽을 포함하여 여러 프로모션된 앱의 정보를 한 곳에서 볼 수 있습니다. 또한 사용자정의 대시보드를 통해 계정 사용자들과 데이터를 쉽고 빠르게 공유할 수 있습니다.

<div id="example-1" />

> 📄 **예시**
>
> 귀하는 eCommerce Apps, Ltd.의 마케터이며, Shoes라는 매우 성공적인 앱을 가지고 있습니다. 이제 Accessories, Jackets and Coats, Sport Shoes 등 3가지 새로운 앱을 출시합니다. Shoe 앱에서 크로스 프로모션 캠페인을 실행하여 어느 새로운 앱이 가장 잘 홍보되는지 확인하려고 합니다.
>
> 사용자 기반을 3개의 세그먼트로 나눕니다.
>
> 3개의 프로모션된 앱 모두에 대한 지표를 한 곳에서 보기 위해 사용자정의 대시보드를 만듭니다. 아래 이미지에서 Sport Shoes는 20.23%의 전환율을 보이고 있는데, 이는 Sport Shoes가 현재 홍보하고 있는 다른 2개 앱에 비해 선호도가 훨씬 높다는 것을 의미합니다.
>
> ![CrossPromo_customWidget](https://files.readme.io/9363a68994956bc19115f6f9babb9acb0c7d4fe75478683b2a45720987486956-4404613319953.png)

<div data-zendesk-anchors="about-crosspromotion=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EC%86%8C%EA%B0%9C h_01HE7RXZ2CZCYENE4K40W5YSHF=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EC%86%8C%EA%B0%9C how-does-crosspromotion-work=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C h_01HE7RXZ2CE5EQV42Y4B9SK4FN=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C attributing-crosspromotion=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%ED%95%98%EA%B8%B0 h_01HE7RXZ2CWB2GZ8HV6447RVV1=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%ED%95%98%EA%B8%B0 setting-up-crosspromotion=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EC%84%A4%EC%A0%95 h_01HE7RXZ2C9JGFYV8K8FECFFJN=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EC%84%A4%EC%A0%95 viewing-crosspromotion-data=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01HE7RXZ2CE9NWMQ1PT3G98QVN=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 promoted-app-dashboard=%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98%ED%95%9C-%EC%95%B1-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C h_01HE7RXZ2CQG9M35Y2FJNPZWDA=%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98%ED%95%9C-%EC%95%B1-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C analysis=%EB%B6%84%EC%84%9D h_01HE7RXZ2CVQD8H0J6EVRJM5T7=%EB%B6%84%EC%84%9D h_01HE7RXZ2CW1P0QNA8FFXP5KBS=%EC%98%88%EC%8B%9C custom-dashboard=%EC%BB%A4%EC%8A%A4%ED%85%80-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C h_01HE7RXZ2C7N3DKNPF898WM4AD=%EC%BB%A4%EC%8A%A4%ED%85%80-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C h_01HE7RXZ2C51KJMP795QYS26YK=%EC%98%88%EC%8B%9C-1" />
