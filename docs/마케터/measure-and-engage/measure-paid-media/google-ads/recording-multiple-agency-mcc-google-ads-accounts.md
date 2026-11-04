---
title: 다수의 에이전시/MCC 구글 애즈 계정 기록하기
metadata:
  keywords:
    - Advertisers
    - Multiple Agencies
    - MCC
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-09-28T11:11:04Z'
  edited_at: '2026-10-14T10:26:35Z'
  id: 115004970386
  locale: ko
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ko/articles/115004970386
---
> **한눈에 보기:** 요약: 트래픽이 올바르게 어트리뷰트되도록 다른 Google Ads 계정에 대한 기록을 설정합니다.

<div id="introduction" />

## 소개

구글 애즈 트래픽은 종종 다양한 계정에서 유입됩니다. (예, 구글 애즈에 특화된 에이전시 또는 앱 소유자의 조직 내 다양한 지역 담당 팀) 올바른 당사자에게 잘 어트리뷰션되도록, 서로 다른 Google Ads 계정의 기록 설정 방법을 이해하는 것이 중요합니다.

본 기사는 에이전시 측정부터 MCC 및 MCC의 MCC를 사용까지 과정을 설명합니다.

<div id="note" />

> 📘 **참고사항**
>
> 아래 설명은 **오직** 구글 애즈 새 API를 사용하는 고객들에게만 적용됩니다.

<Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-agencies">구글 애즈 캠페인 에이전시 계정 설정 관련 상세 내용은 여기를 클릭하십시오.</Anchor>

<div id="important-definitions" />

## 중요한 정의

* **링크 ID (Link ID)** – **구글 애즈에 등록된 모바일 앱의 고유 식별자**.

<div id="note-1" />

> 📘 **참고사항**
>
> 동일한 앱의 안드로이드와 iOS 버전이라도 서로 다른 링크 ID가 필요합니다.

* **고객 ID (Customer ID)** – **구글 애즈 계정의 고유 식별자**.  
  모든 계정은 다수의 링크 ID를 광고할 수 있습니다. 예: 회사의 모든 앱. 앱스플라이어 대시보드에 이미 등록된 앱에 대해 에이전시 계정을 연결할 때, 최대 10개의 고객 ID를 지정할 수 있습니다.
* **MCC** - 구글 애즈 관리자 계정 (MCC, 과거 My Clients Center라고 불려짐)은 구글 애즈에서 **다수의 구글 애즈 계정을 다루는 도구**입니다.  
  MCC 계정을 사용하면, 여러 계정을 연결하여 단일 위치에서 모두를 확인할 수 있습니다. (<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186?hl=en&ref_topic=7554904">더 보기</Anchor>)

<div id="setting-up-google-ads-recording" />

## 구글 애즈 기록 설정하기

앱스플라이어는 앱 당 하나의 링크 ID를 등록할 수 있습니다. **여러 계정이 하나의 앱을 다루는 경우, 계정들은 모두 동일한 링크 ID를 사용해야 합니다.** 이것은 어트리뷰션 목적으로 앱스플라이어 대시보드에 설정되어야 합니다.

<div id="sharing-google-link-id-with-another-account" />

### 구글 링크 ID를 다른 계정과 공유하기

하나의 구글 애즈 계정을 가지고 있거나, 구글 애즈 트래픽을 운영하는 에이전시와 협업을 계획 중인 앱 소유자는 다음 방법을 사용해야만 합니다.

앱 소유자는 아래에 표시된 스크린샷 처럼, 고객 ID로 구별되는 다른 어떤 계정과도 링크 ID를 공유할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-agencies#에이전시를-위한-google-ads-어트리뷰션-설정">에이전시와 링크 ID 공유하기</Anchor> 관련 추가 내용을 참고하십시오.

<div id="important" />

> 🚧 **중요**
>
> * 만약 MCC가 하위 계정의 기록 관리자(Recording Manager)인 경우, MCC에서 하위 계정으로 링크 ID를 공유할 필요가 없습니다. 하지만 만약 MCC 아래의 하위 계정이 자신의 기록 관리자라면, MCC는 반드시 하위 계정의 기록 관리자와 링크 ID를 공유해야만 합니다.
> * 전환 가져오기(Importing Conversions): 만약 MCC가 기록 관리자라면, 하위 계정을 위해 MCC가 전환을 가져와야 합니다. 하지만 만약 MCC 아래의 하위 계정이 자신의 기록 관리자라면, 하위 계정도 반드시 전환을 가져와야 합니다.

<div id="note-2" />

> 📘 **참고사항**
>
> * 구글 애즈 대시보드에서 3개의 점을 클릭 >> ***연결된 계정*** >> ***타사 앱 분석 세부 정보*** [![](https://files.readme.io/bb36fb31e18577f1a7d4e57f5122e51a3edf5b5e4da94f90ab78281707c91f57-51858059772945.png)](https://files.readme.io/bb36fb31e18577f1a7d4e57f5122e51a3edf5b5e4da94f90ab78281707c91f57-51858059772945.png)
> * 다른 계정은 "공유"를 승인해야 합니다.
> * 이에 따라, 다른 계정은 해당 앱에 대한 구글 애즈 캠페인을 운영하도록 승인 받았습니다.

<div id="tip" />

> 👍 **팁**
>
> 앱스플라이어는 각 계정들이 직접 링크 ID를 생성하는 것보다, 광고주의 기본 계정에서 다른 계정으로 링크 ID를 공유할 것을 추천합니다. 이는 가장 빠른 옵션이며, 협업이 종료되었을 때 광고주와 에이전시 간의 분리도 간단하게 가능합니다.

## MCC

에이전시 또는 다수의 구글 애즈 계정을 관리하는 대형 광고주는 종종 MCC (My Client Center)를 사용하여 단일 위치에서 모든 계정을 확인합니다.

MCC를 설정하는 중에, MCC 또는 하위 계정이 전환을 관리하는지를 설정할 수 있습니다.

[![MCC_1_new.png](https://files.readme.io/8c51c51d1808271a73f93f7a4002332447ef61d91fed2480045c81cc5773fc8b-51858059773073.png)](https://files.readme.io/8c51c51d1808271a73f93f7a4002332447ef61d91fed2480045c81cc5773fc8b-51858059773073.png)

필요한 경우, 나중에 이 설정을 수정할 수 있습니다.

![mmc-googleads-settings.png](https://files.readme.io/077df22cde5479a95c19faa7e37c946088bb95794cb64a9f053f31066875d751-51858050900625.png)

<div id="mcc-of-mccs" />

## MCC 중 MCC

다수의 에이전시와 협업하는 대형 광고주는 MCC의 MCC를 사용할 수도 있습니다. 일반 MCC 계정과 비슷합니다. 광고주 또는 최상위 단계의 MCC에서 링크 ID를 생성하는 것이 권장됩니다. 이 구조에 대한 올바른 설정을 수행하려면, 하위 계정이 올바른 단계의 MCC (아마, 가장 높은 단계의 MCC)를 기록 관리자로 선택해야합니다. 이렇게 설정된 경우, 링크 ID는 하위 계정으로 공유될 필요가 없고, 최고 단계 MCC에서의 전환 가져오기로 충분합니다.

<div id="tip-1" />

> 👍 **팁**
>
> MCC와 계정 계층 구조 관련 추가 정보는 아래의 링크를 참조하십시오.
>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7456530">계정을 관리자 계정에 연결하기</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7519925?hl=en&ref_topic=7554359">관리자 계정의 계층 구조 보기</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/topic/7554359?hl=en&ref_topic=6031997">고객 계정 사용하기</Anchor>
>
> 계정 구조 및 권장 사항에 대해서는 구글 담당자와 상의하십시오.

<div id="opening-a-google-ads-campaign" />

## 구글 애즈 캠페인 개설하기

MCC는 구글 애즈 캠페인을 직접 개설할 수 없습니다. 이는 반드시 일반 구글 애즈 하위 계정에서 이루어져야 합니다.

전환 기록에는 다음 두가지 방법이 있습니다.

1. **MCC 계정이 하위 계정 기록을 관리** 같은 회사에서 다양한 팀이 있을 때 흔합니다. 예: 같은 회사 내, 지역별 Google Ads 계정.  
   MCC가 모든 하위 계정의 기록을 설정을 보유합니다(기록 관리자). 기록 설정에 대한 모든 변경은 MCC 단계에서만 가능하며, 모든 하위 계정은 자동적으로 이를 승계합니다.  
   MCC에서 전환 가져오기를 해야 하며, 이는 한 번만 진행하면 모든 하위 계정을 포함합니다. 또한 MCC에서 하위 계정으로 공유되는 링크 ID를 가집니다.
2. **하위 계정이 자체 기록을 관리** 계정이 자신을 서빙하는 하나의 단체 외에는 아무도 연결되지 않은 경우에 흔합니다. 예: 하나의 에이전시가 다양한 광고주 고객 계정을 서빙할 때.  
   이런 경우, 전환 가져오기는 모든 하위 계정에서 별도로 이루어져야 합니다. 앱스플라이어는 앱당 하나의 링크 ID만 기록하므로, 반드시 광고주 또는 MCC가 하위 계정으로 링크 ID를 공유해야 합니다.

구글 애즈로 전환 가져오기는 인스톨 또는 인앱 이벤트 어떤 전환일지라도 반드시 첫번째 사례가 일어난 이후에만 가져올 수 있습니다.

<div data-zendesk-anchors="introduction=%EC%86%8C%EA%B0%9C important-definitions=%EC%A4%91%EC%9A%94%ED%95%9C-%EC%A0%95%EC%9D%98 setting-up-google-ads-recording=%EA%B5%AC%EA%B8%80-%EC%95%A0%EC%A6%88-%EA%B8%B0%EB%A1%9D-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 sharing-google-link-id-with-another-account=%EA%B5%AC%EA%B8%80-%EB%A7%81%ED%81%AC-id%EB%A5%BC-%EB%8B%A4%EB%A5%B8-%EA%B3%84%EC%A0%95%EA%B3%BC-%EA%B3%B5%EC%9C%A0%ED%95%98%EA%B8%B0 mcc-of-mccs=mcc-%EC%A4%91-mcc opening-a-google-ads-campaign=%EA%B5%AC%EA%B8%80-%EC%95%A0%EC%A6%88-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EA%B0%9C%EC%84%A4%ED%95%98%EA%B8%B0" />
