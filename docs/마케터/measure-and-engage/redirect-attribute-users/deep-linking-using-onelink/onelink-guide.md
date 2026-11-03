---
title: 원링크 가이드
metadata:
  keywords:
    - Marketers
    - start
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-10-19T08:53:16Z'
  edited_at: '2026-10-14T10:36:56Z'
  id: 115005248543
  locale: ko
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ko/articles/115005248543
---
> **한눈에 보기:** 디바이스, 운영 체제, 채널 또는 플랫폼에 관계없이 온드(owned) 미디어 또는 페이드(paid) 미디어 유저를 앱 유저로 전환하는 어트리뷰션, 리디렉션 및 딥링킹 기능을 사용하여 링크를 생성합니다. 이렇게 생성된 링크는 웹사이트, 배너, 소셜 미디어 게시물, 이메일, 문자 메시지 등 다양한 온드 미디어에서 유저에게 최상의 경험을 제공할 것입니다.

## 원링크 소개 동영상

<Embed title="YouTube 동영상 플레이어" typeOfEmbed="youtube" url="https://www.youtube.com/embed/golT4p9D8MA" providerUrl="https://www.youtube.com" />

## 장점

원링크가 제공하는 앱스플라이어 고객 경험 및 딥링킹 제품군 을 활용하면, 모든 주요 채널에서 모바일 마케팅 캠페인을 측정하기 위한 링크를 생성할 수 있습니다. 생성한 링크를 통해 다음을 수행할 수 있습니다.

* 다양한 온라인 및 오프라인 터치 포인트에서 고객과 상호 작용
* 클릭에서 앱 인스톨에 이르기까지 모든 터치포인트의 유저에게 최상의 컨텍스트 경험을 제공하여 전환율 증가
* 캠페인 결과에 대한 정확한 어트리뷰션 및 측정값 얻기
* 디바이스, 운영 체제, 채널 또는 플랫폼에 관계없이 앱이 없는 신규 유저를 올바른 앱 스토어 또는 웹 URL로 보내기.
* 앱을 인스톨한 기존 유저를 앱에 직접 보내기 (App Links, Universal Links 및 URI 스키마 사용)
* 특정 인앱 페이지 또는 경험으로 유저를 딥링킹

해당 제품군은 등록한 플랜에 상관없이 무료입니다.

## 유저 경험

원링크가 제공하는 앱스플라이어 고객 경험 및 딥링킹 제품군을 사용하면 유저가 어디에서 왔는지에 관계없이 최적의 경험을 제공하는 링크를 생성할 수 있습니다. 다음과 같은 고객 경험을 설정할 수 있습니다.

* **소셜-투-앱**: 소셜미디어에서 유저를 참여시키고, 소셜미디어 피드에서 앱으로 발송하세요.
* **앱 - 앱**: 다른 앱에서 사용자를 귀사의 앱으로 유도하세요.
* <Anchor target="_blank" href="/marketers/ko/docs/convert-your-mobile-web-visitors-to-app-users">**웹 - 앱**</Anchor>: 스마트 배너와 스마트 스크립트를 사용하여 모바일 웹사이트 방문자를 새로운 모바일 앱 사용자로 전환하세요.
* **QR - 앱**: 오프라인 고객 경험 중 주요 지점에서 QR 코드를 스캔하여 앱 인스톨을 유도합니다. 또한 데스크톱 사이트, TV 및 CTV 광고에 QR 코드를 삽입하여 유저를 귀사의 앱으로 안내할 수 있습니다.
* **이메일 - 앱**: 이메일 서비스 제공업체(ESPs)를 사용하여 이메일을 통해 유저를 (유저를 앱에) 참여시키고 받을 편지함에서 앱으로 발송하세요.
* **텍스트 - 앱**: SMS 문자메시지 및 메시징 캠페인을 위한 링크를 생성하여 문자 메시지를 통해 유저를 (유저를 앱에) 참여시키세요.
* **앱 추천**: 앱 초대 링크를 생성하여 유저와 인플루언서가 다른 사람을 귀사의 앱으로 초대하거나 특정 인앱 콘텐츠(예: 문서)를 공유할 수 있습니다.
* **커스텀**: 기타: 데스크톱 또는 모바일, 온라인, 오프라인, 온드(owned) 미디어, 페이드(paid) 미디어 등 유저 여정이 어디에서 시작하든, 원링크를 사용하여 유저를 올바른 곳으로 쉽게 보낼 수 있습니다./span>

## 원링크 설정하기

앱스플라이어 UI를 사용하여, 링크에서 앱 인스톨까지 원하는 고객 경험을 제공하려면 다음이 필요합니다.

* 조직 내에서 서로 다른 두 가지 역할(마케터와 개발자)을 맡는 담당자들이 함께 작업합니다.
* 모든 링크의 핵심 라우팅 로직을 나타내는 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">원링크 템플릿을 생성</Anchor>하여 다음으로 리디렉션합니다.
  * 앱을 인스톨하지 않은 신규 유저를 올바른 앱 스토어 또는 웹 URL으로 리디렉션
  * 안드로이드 App Links, iOS Universal Links 및 URI 스키마를 통해 앱을 설치한 기존 유저를 앱으로 리디렉션
    * 이러한 설정이 정의되지 않은 경우, 앱을 설치하지 않은 새 유저와 동일한 기본 설정(웹 URL 또는 앱 스토어)이 유저에게 적용됩니다.**참고**: 원링크 템플릿은 엔드 유저가 클릭할 수 있는 링크가 아니며, 여러 커스텀 링크를 생성하기 위한 기본 양식입니다. 템플릿을 기반으로 유저가 클릭할 수 있는 여러 개의 원링크 커스텀 링크를 생성할 수 있습니다. 앱 생애주기(테스트 기간 제외)에서 원링크 템플릿 하나 혹은 둘 이상 필요한 경우는 드뭅니다.
* <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">원링크 링크 만들기</Anchor>. 광고에 표시되는 클릭 가능한 링크 또는 스캔 가능한 QR 코드입니다. 링크 설정 중에 원하는 고객 경험을 정의하고 원하는 파라미터를 추가합니다.

다음 표에는 마케터 및 개발자가 담당할 작업에 대한 세부 정보를 설명하고 해당 리소스에 대한 링크를 제공합니다.

| 작업 | 상세 정보 | 자료 |
| --- | --- | --- |
| 원링크 템플릿 만들기 | <ul><li>마케터/제품 관리자가 앱스플라이어에서 템플릿을 설정합니다.</li><li>안드로이드 개발자는 기존 유저를 위한 앱 오픈 방법)을 설정합니다. (안드로이드 App Links 및 URI 스키마)</li><li>iOS 개발자는 기존 유저를 위한 앱 오픈 방법을 설정합니다. (iOS Universal Links 및 URI 스키마)</li></ul> | <ul><li>앱스플라이어 대시보드</li><li><Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">마케터 지침</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">안드로이드</Anchor> 및 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup">iOS</Anchor> 개발자 지침</li></ul> |
| 원링크 링크 만들기 | <ul><li>마케터/제품 관리자가 앱스플라이어에서 링크를 설정하고, 이때 원하는 고객 경험을 선택하고 원하는 어트리뷰션 또는 딥링킹 파라미터를 추가합니다.</li><li>안드로이드 및 iOS 개발자는 딥링킹을 위해 UDL 방식을 구현합니다. (딥링킹이 필요한 경우)</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">마케터 지침</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_unified_deep_linking">안드로이드</Anchor> 및 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_unified_deep_linking">iOS</Anchor> 개발자 지침</li><li>샘플 앱 (Github)</li></ul> |

## 추가 옵션

UI에서 먼저 일부 또는 전체 설정을 완료한 후에 아래에 설명된 추가 기능을 구현하는 것이 좋습니다.

**참고**: 일러두기: 프리미엄 기능인 원링크 API를 제외한 모든 기능은 앱스플라이어의 <Anchor target="_blank" href="/marketers/ko/docs/account-management-plans-payments-and-billing">제로 및 그로쓰 플랜</Anchor>에 포함됩니다.

* <Anchor target="_blank" href="/marketers/ko/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">원링크 API</Anchor> 그리고 <Anchor target="_blank" href="/marketers/ko/docs/perform-onelink-bulk-actions-via-csv">대량 링크 생성</Anchor>: 여러 개의 캠페인을 한 번에 확장 및 실행하고, 수천 개의 원링크를 빠르고 쉽게 작성하여 시간과 노력을 절약하고 캠페인 및 마케팅 노력에 집중할 수 있도록 합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/export-onelink-urls">원링크 URL 내보내기</Anchor>: 앱스플라이어 유저 인터페이스에서 생성된 원링크 URL을 모두 다운로드합니다. (SDK, 원링크 API 또는 대량 업로드를 통해 생성된 원링크 URL은 포함되지 않음)
* <Anchor target="_blank" href="/marketers/ko/docs/measuring-push-notification-re-engagement-campaigns">푸시 알림 리인게이지먼트 캠페인 측정</Anchor>: 원링크와 푸시 알림을 활용해 모바일 사용자의 리인게이지먼트를 측정하세요.
* <Anchor target="_blank" href="/marketers/ko/docs/cross-promotion-attribution-for-marketers">크로스 프로모션 어트리뷰션</Anchor>: 한 회사의 앱을 사용하는 사람은 같은 회사의 다른 앱을 설치할 가능성이 높습니다.  SDK 메서드를 이용하여 크로스 프로모션 캠페인을 쉽게 만들고 측정하는 법에 대해 알아보세요.
* <Anchor target="_blank" href="/marketers/ko/docs/understand-onelink-short-vs-long-urls">긴 URL</Anchor>: 원링크 커스텀 링크에 파라미터를 추가하거나 스프레드시트에 귀하가 생성한 간단한 수식을 적용하여 많은 원링크 커스텀 링크를 생성합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/redirect-app-users-to-a-website">앱-투-웹 리디렉션</Anchor>: 유저를 앱에서 웹사이트 또는 소셜 미디어 페이지로 리디렉션합니다.

## 문제 해결 및 FAQ

<Anchor target="_blank" href="/marketers/ko/docs/onelink-troubleshooting-and-faq">원링크 문제해결 가이드</Anchor>를 확인하시고, 원링크 커스텀 링크 리디렉션/작동 문제를 테스트하고 디버깅하기 위한 솔루션을 신속하게 찾으세요.

## 제한 사항

* 원링크는 메타 앱 링크만 허용되는 메타 모바일 앱 인스톨 목표에서는 지원되지 않습니다.

<div data-zendesk-anchors="introduction-video=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%86%8C%EA%B0%9C-%EB%8F%99%EC%98%81%EC%83%81 h_01HGE1D5JZ4Y603BD55W2P7DPW=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%86%8C%EA%B0%9C-%EB%8F%99%EC%98%81%EC%83%81 benefits=%EC%9E%A5%EC%A0%90 h_01HGE1D5JZJGY8BZX8ZTSXQ635=%EC%9E%A5%EC%A0%90 experiences=%EC%9C%A0%EC%A0%80-%EA%B2%BD%ED%97%98 h_01HGE1D5JZV65E9YWG424HYRNW=%EC%9C%A0%EC%A0%80-%EA%B2%BD%ED%97%98 setup=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01HGE1D5K0RKHHV9SVH4VREMXQ=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 additional-options=%EC%B6%94%EA%B0%80-%EC%98%B5%EC%85%98 h_01HGE1D5K2VCKYJY3Y8MKYVT2V=%EC%B6%94%EA%B0%80-%EC%98%B5%EC%85%98 troubleshooting-and-faq=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%EB%B0%8F-faq h_01HGE1D5K24FG3F8G54DYTK599=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%EB%B0%8F-faq limitations=%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HGE1D5K2M0VMJPMP4EJ0QGPY=%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD" />
