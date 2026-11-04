---
title: SDK에서 안드로이드 OAID 구현
metadata:
  keywords:
    - China
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2020-02-27T20:21:05Z'
  edited_at: '2026-10-14T10:36:49Z'
  id: 360006278797
  locale: ko
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/ko/articles/360006278797
---
> **요약:** 안드로이드 OAID를 수집하여 타사 안드로이드 앱 스토어의 설치에 기여합니다.

<div id="about-oaid" />

## OAID 소개

OAID(익명 장치 식별기 열기)는 사용자가 재설정할 수 있는 안드로이드 장치의 고유 식별자입니다. 이는 IMEI와 같이 재설정할 수 없는 장치 식별자에 대한 개인 정보 보호 대안으로 MSA(모바일 보안 연합), 중국 정보 통신 연구소 및 장치 제조업체에서 도입되었습니다.

OAID는 일반적으로 Google Play 서비스를 사용할 수 없는 기기(즉, Google 광고 ID가 존재하지 않는 기기)에서 광고 측정 및 설치 속성에 사용됩니다.

<span id="supported-devices"></span>OAID는 MSA에서 제공하는 SDK를 사용하는 모든 장치 또는 Huawei 모바일 서비스 (HMS) 코어 SDK를 사용하는 Huawei 장치에서 읽을 수 있습니다.

<div id="integration" />

## 연동

OAID 통합은 3단계로 구성됩니다.

1. SDK를 통합하여 OAID(MSA SDK 또는 Huawei HMS SDK)를 생성하고 제공합니다.
2. 앱스플라이어 OAID 플러그인 모듈을 통합합니다.
3. 앱스플라이어 SDK를 통합합니다.

**참고**:

* 중국에서 사용하려는 앱의 경우 MSA SDK를 사용해야 합니다.
* Huawei 장치에서 전 세계적으로 사용하려는 앱의 경우 Huawei HMS 라이브러리를 사용해야 합니다.

<div id="msa-sdk" />

<Accordion title="MSA SDK">

**MSA SDK를 통합하고 사용하려면**:

1. [MSA 웹사이트](http://www.msa-alliance.cn/col.jsp?id=120)의 지침에 따라 앱을 등록하세요.
   * 등록하면 SDK를 다운로드할 수 있습니다.
   * 등록 프로세스의 일부로 앱에 추가해야 하는 인증서 파일을 받게 됩니다.
2. 개발자에게<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#msa-sdk-integration">통합 지침</Anchor>을 따르도록 합니다.

</Accordion>

<div id="huawei-hms-sdk" />

<Accordion title="Huawei HMS SDK">

**Huawei HMS SDK를 통합하고 사용하려면**:

* 개발자에게<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#huawei-hms-sdk-integration">통합 지침</Anchor>을 따르도록 합니다.

</Accordion>

<div id="additional-information" />

## 추가 정보

<div id="opting-out-of-oaid-collection" />

<Accordion title="OAID 수집 거부">

OAID 통합이 완료되면 SDK는 자동으로 OAID 수집을 시도합니다. 특정 사용자에 대한 OAID 수집을 방지하려면 개발자에게 다음을 사용하도록 지시하십시오.

<Tabs>
<Tab title="안드로이드">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid">setCollectOAID(false) API</Anchor>또는<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>

<Tab title="유니티">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectoaid">setCollectOAID(false) API</Anchor>또는<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>
</Tabs>

<div id="setting-oaid-manually" />

<Accordion title="OAID 수동 설정">

앱이 이미 OAID를 수집하는 경우, 앱스플라이어 OAID 플러그인 통합을 건너뛰고<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#setting-oaid-manually">setOaidData API</Anchor>를어 사용하여 OAID 값을 앱스플라이어 SDK에 수동으로 설정할 수 있습니다.

</Accordion>

</Accordion>

<div data-zendesk-anchors="about-oaid=oaid-%EC%86%8C%EA%B0%9C h_01HG8PXBZS1SN3SY3AAH1EKMNP=oaid-%EC%86%8C%EA%B0%9C integration=%EC%97%B0%EB%8F%99 h_01HG8PXBZS26P9X1TQ7J4WQNF5=%EC%97%B0%EB%8F%99 h_01HG8PXBZSM0QYQE4C9S1FBFB1=msa-sdk h_01HG8PXBZS3HP9X1AZ7HQ8C34Y=huawei-hms-sdk additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HG8PXBZSW5HNTTDRQ7DFFF4D=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HG8PXBZS8Z3MTQWFN5R6FFA8=opting-out-of-oaid-collection h_01HG8PXBZSYNS8R1PCW4YXHFBA=setting-oaid-manually" />
