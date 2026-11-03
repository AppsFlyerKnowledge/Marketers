---
title: Salesforce Marketing Cloud MobilePush 연동 설정
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-14T06:37:05Z'
  edited_at: '2026-10-14T10:40:29Z'
  id: 10590769196817
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/10590769196817
---
> **요약: 요약: 앱스플라이어 연동 파트너인 Salesforce Marketing Cloud MobilePush는 마케팅, 성장 및 인게이지먼트 팀을 위한 유저 인게이지먼트 플랫폼입니다.**

## 개요

Salesforce Marketing Cloud MobilePush를 사용하면 크로스 채널 소비자 데이터를 기반으로 타겟 푸시 메시지를 작성하여 보낼 수 있습니다. 이렇게 하면 앱 사용을 장려하고 ROI를 높일 수 있습니다. 사용자는 MobilePush를 사용하면 유저가 보는 제품에서 각 페이지에서 보낸 시간에 이르기까지 유저가 앱을 탐색하는 방법을 알아볼 수 있습니다. MobilePush를 연동하면 다음 이점이 있습니다:

* 인게이지먼트 및 mCommerce 유도
* 가치 있는 유저 통찰력 획득
* 크로스 채널 캠페인을 쉽게 구축
* 메시지 세분화 및 예약

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 미디어소스</Anchor>는 타사와의 데이터 공유를 제한합니다. 따라서 제한된 이벤트에 대한 포스트백은 포스트백을 보내기 위해 구성된 선택에 관계없이 이 파트너에게 전송되지 않습니다.

## Salesforce Marketing Cloud MobilePush 설정

대부분의 설정은 Salesforce에서 수행됩니다(1-4단계). 5단계는 앱스플라이어에서 수행됩니다.

### 1단계:

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_get_started.htm&type=5">MobilePush SDK 설정 구현</Anchor>

### 2단계: 2단계: 푸시 알림 프로비저닝

### 3단계: 3단계: 앱 푸시 알림 활성화

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-configureforpush.html">푸시 알림 구현</Anchor>

### 4단계: 4단계: 앱 푸시 알림 설정

* 푸시 메시지를 작성하여 모바일 장치로 전송

> 📘 **참고사항**
>
> Salesforce Marketing Cloud에서 푸시 알림을 생성할 때 앱스플라이어가 올바른 PID 및 캠페인 속성으로 올바르게 어트리뷰션할 수 있도록 <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_custom_keys.htm&type=5">커스텀 키</Anchor>를 추가해야 합니다.

### 3단계: 5단계: 앱스플라이어에서 푸시 알림 설정

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications-ios#addpushnotificationdeeplinkpath-recommended">원링크를 사용하여 iOS SDK 설정(이 링크의 3단계)</Anchor>

> 📘 **참고사항**
>
> `AF_xxxxxxxxx`4단계AF\_xxxxxxxxx에서 입력한 커스텀 키 [AF\_xxxxxxxxx](/docs/salesforce-marketing-cloud-mobilepush-integration-setup#4단계-4단계-앱-푸시-알림-설정)가 `addPushNotificationDeepLinkPath` 함수에 입력한 것과 같은 값인지 확인합니다.

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01H9HWK3F5TQZ8YQZBHGBZACPG=%EA%B0%9C%EC%9A%94 h_01H9HWK5DM87JTDVFND0KB965G=%EC%A4%91%EC%9A%94 setting-up-salesforce-marketing-cloud-mobilepush=salesforce-marketing-cloud-mobilepush-%EC%84%A4%EC%A0%95 h_01H9HWK3F52YGQPX4B82N40PPD=salesforce-marketing-cloud-mobilepush-%EC%84%A4%EC%A0%95 step-1-set-up-mobilepush-sdk=1%EB%8B%A8%EA%B3%84 h_01H9HWK3F5HCVZ0225MFRYRW5Q=1%EB%8B%A8%EA%B3%84 step-2-provision-for-push-notifications=2%EB%8B%A8%EA%B3%84-2%EB%8B%A8%EA%B3%84-%ED%91%B8%EC%8B%9C-%EC%95%8C%EB%A6%BC-%ED%94%84%EB%A1%9C%EB%B9%84%EC%A0%80%EB%8B%9D h_01H9HWK3F5RNCZG340E0CT5XJC=2%EB%8B%A8%EA%B3%84-2%EB%8B%A8%EA%B3%84-%ED%91%B8%EC%8B%9C-%EC%95%8C%EB%A6%BC-%ED%94%84%EB%A1%9C%EB%B9%84%EC%A0%80%EB%8B%9D step-3-enable-app-push-notifications=3%EB%8B%A8%EA%B3%84-3%EB%8B%A8%EA%B3%84-%EC%95%B1-%ED%91%B8%EC%8B%9C-%EC%95%8C%EB%A6%BC-%ED%99%9C%EC%84%B1%ED%99%94 h_01H9HWK3F5E4W8FG35V4JTFN7F=3%EB%8B%A8%EA%B3%84-3%EB%8B%A8%EA%B3%84-%EC%95%B1-%ED%91%B8%EC%8B%9C-%EC%95%8C%EB%A6%BC-%ED%99%9C%EC%84%B1%ED%99%94 step-4-set-up-app-push-notifications=4%EB%8B%A8%EA%B3%84-4%EB%8B%A8%EA%B3%84-%EC%95%B1-%ED%91%B8%EC%8B%9C-%EC%95%8C%EB%A6%BC-%EC%84%A4%EC%A0%95 h_01H9HWK3F5K8V8AVADXNNG25GY=4%EB%8B%A8%EA%B3%84-4%EB%8B%A8%EA%B3%84-%EC%95%B1-%ED%91%B8%EC%8B%9C-%EC%95%8C%EB%A6%BC-%EC%84%A4%EC%A0%95 h_01H9HWK3F5VG2GBCE93B69AADH=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD step-5-set-up-push-notifications-in-appsflyer=3%EB%8B%A8%EA%B3%84-5%EB%8B%A8%EA%B3%84-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%ED%91%B8%EC%8B%9C-%EC%95%8C%EB%A6%BC-%EC%84%A4%EC%A0%95 h_01H9HWK3F5YJ71YCWHV4B02VYP=3%EB%8B%A8%EA%B3%84-5%EB%8B%A8%EA%B3%84-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%ED%91%B8%EC%8B%9C-%EC%95%8C%EB%A6%BC-%EC%84%A4%EC%A0%95 h_01H9HWK3F5T67NSPE9CVPS1KTA=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-1" />
