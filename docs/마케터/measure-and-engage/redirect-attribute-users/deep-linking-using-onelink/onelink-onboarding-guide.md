---
title: OneLink 온보딩 가이드
metadata:
  keywords:
    - Marketers
    - set up
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-08-21T11:48:39Z'
  edited_at: '2026-10-14T10:33:41Z'
  id: 27699299657617
  locale: ko
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ko/articles/27699299657617
---
> **간단히 보기**: 사용자 디바이스, 운영 체제, 채널, 플랫폼에 관계없이 캠페인에서 강력하고 사용자 맞춤화된 리디렉션, 딥링킹, 어트리뷰션을 위해 원링크를 사용하여 최대 전환과 수익을 달성하세요.

## ![53010_원링크.jpg](https://files.readme.io/c0d24ab87126bf765a89a25077b07d8678159cdb6f1b68eddc14a4cd2759b12a-30192941047185.jpg)

## 원링크 정보

<Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">앱스플라이어 원링크를 사용하면 어트리뷰션, 리디렉션, 딥링킹 기능을 가진 캠페인 링크를 만들어 온드(owned) 미디어 사용자를 앱 사용자로 전환하고, 디바이스, 운영 체제, 채널, 플랫폼에 관계없이 원활한 사용자 여정을 통해 기존 유저 참여를 유도할 수 있습니다. 원링크를 사용하여 개인화되고 상황에 맞는 사용자 여정을 만들어 사용자를 귀사의 앱으로 유도하여 최대 전환율과 수익을 달성하세요. 사용자 맞춤형 경험은 다음과 같은 것들이 있습니다:</Anchor>

* **소셜-투-앱**: 소셜미디어에서 유저를 참여시키고, 소셜미디어 피드에서 앱으로 발송하세요.
* **앱 - 앱**: 다른 앱에서 사용자를 귀사의 앱으로 유도하세요.
* 웹에서 앱으로: 스마트 배너와 스마트 스크립트를 사용하여 모바일 웹사이트 방문자를 새로운 모바일 앱 사용자로 전환하세요.
* **QR-투-앱**: 오프라인 고객 경험 중 주요 지점에서 QR 코드를 스캔하여 앱 인스톨을 유도합니다. 또한 데스크톱 사이트, TV 및 CTV 광고에 QR 코드를 삽입하여 유저를 귀사의 앱으로 안내할 수 있습니다.
* **이메일-투-앱**: 이메일 서비스 제공업체(ESPs)를 사용하여 이메일을 통해 유저를 (유저를 앱에) 참여시키고 받을 편지함에서 앱으로 발송하세요.
* **텍스트-투-앱**: SMS 문자메시지 및 메시징 캠페인을 위한 링크를 생성하여 문자 메시지를 통해 유저를 (유저를 앱에) 참여시키세요.
* **리퍼럴-투-앱**: 앱 초대 링크를 생성하여 유저와 인플루언서가 다른 사람을 귀사의 앱으로 초대하거나 특정 인앱 콘텐츠(예: 문서)를 공유할 수 있습니다.
* **사용자 지정**: 다양한 옵션으로 커스텀 경험을 만들어 최대한의 사용자 정의를 구현하세요. 사용자가 데스크톱, 모바일, 온라인, 오프라인, 온드(owned) 미디어, 유료 미디어 어디에서든 시작해도 원링크를 사용하면 쉽게 올바른 장소로 안내할 수 있습니다.

## 원링크 온보딩

**원링크 사용을 시작하려면 다음 단계를 따르세요:**

<span id="h_01J5WC8Z4J352AHSDTRCEP2W9H"></span>**전제 조건**

* 귀사의 앱이 최소 하나 이상 추가된 앱스플라이어 <Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">계정</Anchor>이 있어야 합니다.
* 원링크를 설정하려면 앱스플라이어 어드민 유저이거나 원링크 템플릿을 추가\/편집할 수 있는 <Anchor target="_blank" href="/marketers/ko/docs/user-management">권한</Anchor>이 있어야 합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/integrate-the-appsflyer-sdk">앱스플라이어</Anchor> SDK 는 인스톨, 인앱 이벤트, 딥링킹의 어트리뷰션을 위해 귀사의 모바일 앱에 설치되어야 합니다.
  * 앱에 SDK가 아직 설치되지 않았더라도 어트리뷰션 없이 작동하는 리디렉션 링크를 만들 수 있습니다.

| 작업 | 목적 | 필요한 조치 | 관련된 사람 |
| --- | --- | --- | --- |
| 1. 원링크 템플릿 만들기 | OneLink 템플릿은 생성할 링크에 대한 리디렉션 논리의 필수 기반입니다. | <ul><li>마케터\/제품 관리자: 앱스플라이어에서 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">원링크 템플릿</Anchor>을 설정하세요.</li><li>안드로이드 개발자: 기존 사용자를 위한 앱 열기 방법을 구성합니다(안드로이드 앱 링크 및 URI 체계).</li><li>iOS 개발자: 기존 사용자를 위한 앱 열기 방법을 구성합니다(iOS 유니버설 링크 및 URI 체계).</li></ul><Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">개발자 지침</Anchor> | 마케터 및 개발자 |
| 2. 원링크 링크 생성 | 새로 만든 템플릿에서 캠페인에 사용할 원링크 링크를 만드세요. | <ul><li>마케터\/제품 관리자: 앱스플라이어에서 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#캠페인을-위한-원링크-링크-생성하기">원링크 링크</Anchor>를 설정하고, 고객 경험을 선택하고, 어트리뷰션 및 딥링킹 파라미터를 추가하세요.</li><li>안드로이드 및 iOS 개발자: <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">딥링킹</Anchor>을 설정하세요(딥링킹이 필요한 경우).</li></ul> | 마케터 및 개발자 |
| 3. 도메인 리디렉션 허용 목록 설정 | 보안을 위해 앱스플라이어에서 생성한 링크는 허용 목록에 있는 도메인의 웹 URL로만 사용자를 리디렉션합니다. | 사용자를 리디렉션할 모든 도메인을 <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-domain-redirect-allowlist">도메인 리디렉션 허용 목록</Anchor>에 업데이트하세요. | 마케터 |
| 4. 새로 만든 링크 시험 | 링크가 성공적으로 리디렉션되는지 시험하세요.<ul><li>앱이 설치되지 않은 신규 사용자</li><li>앱이 설치된 기존 사용자</li></ul> | 새로 만든 링크를 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">시험</Anchor>할 수 있습니다. | 마케터 |
| 5. 캠페인에서 링크를 활용하고 결과를 측정하세요 |  | <ol><li>새로운 링크를 캠페인에 추가하고 오디언스에게 제공하세요.</li><li>앱스플라이어 개요 대시보드에서 캠페인 결과를 확인하세요(캠페인별로 필터링).</li></ol>축하합니다! 이제 원링크 온보딩이 완료되었습니다. | 마케터, 데이터 분석가 |
| **선택적 기능** |  | 이제 모든 설정이 완료되었으므로 추가 원링크 기능을 탐색하고 알아보세요:<ul><li>웹에서 앱으로: 웹 사용자를 앱 사용자로 전환하여 웹-앱 전환 경로를 측정하세요.</li><li><Anchor target="_blank" href="/marketers/ko/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">원링크 API</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/perform-onelink-bulk-actions-via-csv">대량 링크 생성</Anchor>: S여러 캠페인을 동시에 확장하고 실행하며, 수천 개의 원링크를 빠르고 쉽게 생성합니다.<br />*원링크 API는 Enterprise 구독이 필요합니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/export-onelink-urls">원링크 URL 내보내기: 앱스플라이어에서 생성한 귀사의 원링크 URL을 다운로드하세요.</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/measuring-push-notification-re-engagement-campaigns">푸시 알림 리인게이지먼트 캠페인 측정</Anchor>: 원링크와 푸시 알림을 활용해 모바일 사용자의 리인게이지먼트를 측정하세요.</li><li><Anchor target="_blank" href="/marketers/ko/docs/cross-promotion-attribution-for-marketers">크로스 프로모션 어트리뷰션</Anchor>: 기존 앱 사용자는 귀사의 다른 새로운 앱을 설치할 수 있는 훌륭한 대상입니다. SDK 방법을 활용해 크로스 프로모션 캠페인을 만들고 측정하는 방법을 학습합니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/understand-onelink-short-vs-long-urls">긴 URL</Anchor>: 귀사의 원링크 커스텀 링크에 파라미터를 추가하거나, 스프레드시트에서 간단한 수식을 적용하여 대량의 원링크 커스텀 링크를 생성합니다.</li></ul> | 마케터 및 개발자 |

원링크 시작에 도움이 필요하면 귀사의 담당자에게 문의하거나 [hello@appsflyer.com](mailto:hello@appsflyer.com)으로 이메일을 보내주세요.

## 특징 및 제약 사항

| 특징 | 비고 |
| --- | --- |
| iPad Safari에서의 소유 미디어 귀속 | 사용자가 iPad에서 Safari 브라우저를 사용하여 소유 미디어 링크를 클릭할 때, 브라우저는 iPad 장치 모델 대신 **Macintosh와 유사한 사용자 에이전트**를 보고할 수 있습니다. 그 결과, AppsFlyer는 클릭이 Mac 장치에서 발생한 것으로 식별하는 반면, 앱 설치는 iPad에서 발생한 것으로 식별됩니다. 확률적 귀속은 클릭과 설치 간의 장치 특성을 일치시키는 데 의존하기 때문에, 이 불일치는 귀속을 방지하고 귀속되지 않은 설치 또는 지연된 딥 링크 실패를 초래할 수 있습니다. 이 제한은 Safari를 사용하는 iPad 장치의 소유 미디어 트래픽에만 적용됩니다. |

<div data-zendesk-anchors="overview=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%A0%95%EB%B3%B4 h_01J2G7RMHSPPXCWJ60W9HZASXX=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%A0%95%EB%B3%B4 h_01HKHGX9JJQQCKF9SDZRSCM1XJ=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%A0%95%EB%B3%B4 xyz-onboarding=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%98%A8%EB%B3%B4%EB%94%A9 h_01J2RJFH0B4R815CWDQNEB2C1P=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%98%A8%EB%B3%B4%EB%94%A9 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01KFAG3N0X0W0RCJXK00KX038E=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
