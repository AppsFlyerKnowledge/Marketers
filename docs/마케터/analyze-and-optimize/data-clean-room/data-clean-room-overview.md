---
title: 데이터 클린룸 개요
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-03-08T14:47:36Z'
  edited_at: '2026-10-14T10:33:51Z'
  id: 4626852381713
  locale: ko
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ko/articles/4626852381713
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**![privacy_cloud_logo.png](https://files.readme.io/5862beb63a4b22f68fc230f89c3faa260a15ab40e1defa70c59604d5a81e759d-5583061038225.png)**

> **한눈에 보기:** 사용자 수준 데이터를 앱스플라이어의 사용자 수준 어트리뷰션 데이터와 매칭하여 집계된 리포트를 생성하고, 결합된 데이터의 가치를 활용하는 인사이트를 확보하세요.

<div id="introduction" />

## 소개

모바일 마케팅 생태계는 그 역사를 통틀어 사용자 수준 데이터를 활용하여 인사이트를 얻고 광고 캠페인을 최적화해 왔습니다.

1. 미디어소스는 사용자 수준 데이터를 어트리뷰션 측정 제공업체(예: 앱스플라이어)에 제공하고, 제공업체는 이를 사용하여 어트리뷰션을 제공한 다음 광고주에게 전달합니다.
2. 광고주는 이 사용자 수준 데이터를 자체 사용자 수준 데이터(예: BI 또는 CRM 시스템)와 일치시킨 다음, 필요에 따라 분석하고 그룹화하여 캠페인을 최적화하는 데 필요한 종합적인 인사이트를 얻습니다.

사용자 개인정보 보호 시대가 도래하며 미디어소스의 사용자 수준 데이터에 대한 접근이 크게 제한되고 있습니다.

1. 미디어소스는 어트리뷰션 측정 제공업체(예: 앱스플라이어)에 사용자 수준 데이터를 제공하고, 이 제공업체는 이를 사용하여 어트리뷰션을 제공하지만, **이제 이 사용자 수준 데이터를 광고주에게 전달할 수 없게 차단됩니다.**
2. 이로 인해 광고주는 과거처럼 사용자 수준의 어트리뷰션 데이터를 자체 사용자 수준의 데이터와 매칭할 수 없게 되어, 필요한 인사이트를 얻을 수 없게 됩니다.

바로 이러한 '데이터 사각지대'를 앱스플라이어 데이터 클린룸(DCR)이 바로잡기 위해 개입합니다.

<div id="how-does-it-work" />

### 어떻게 작동되나요?

광고주가 사용자 수준의 어트리뷰션 데이터를 광고주에게 전달하여 ***광고주***가 사용자 수준의 데이터와 매칭할 수 있도록 하는 대신, 사용자 수준의 어트리뷰션 데이터를 광고주의 사용자 수준 데이터와 ***매칭하는 작업을 DCR이 수행***하여, 이 책임을 앱스플라이어에게 전가합니다. 그런 다음 DCR은 이 데이터를 분석하고 그룹화한 후 집계된 형태로 광고주에게 전달하여, 광고주가 **사용자 개인정보 보호를 유지**하면서 필요한 종합적인 인사이트를 얻을 수 있도록 합니다.

<div id="how-does-the-dcr-obtain-data" />

### DCR은 데이터를 어떻게 수집하나요?

DCR은 현재 두 가지 유형의 데이터를 사용합니다.

* **사용자 지정 소스 데이터:** DCR에서 사용하기 위해 클라우드 스토리지에 업로드된 사용자 수준 데이터입니다. 이 데이터는 광고주의 내부 시스템(예: BI 또는 CRM 시스템)에서 생성됩니다.
* **어트리뷰션 데이터:** 어트리뷰션을 위해 미디어소스가 앱스플라이어에 제공한 사용자 수준 데이터입니다.

<div id="what-does-the-dcr-do-with-the-data" />

### DCR은 데이터로 어떤 작업을 수행하나요?

DCR은 표준 데이터베이스 원칙에 따라 작동합니다. 즉, 서로 다른 테이블(또는 **'소스'**)의 데이터를 단일 데이터 집합으로 일치시킵니다. 그런 다음, 이 단일 데이터 집합을 사용하여 결합된 데이터를 사용하는 **리포트**를 만듭니다.

* 서로 다른 소스의 데이터를 일치시키고 단일 집합으로 결합하려면 각 소스는 고유한 앱 사용자를 식별하는 필드 **(‘식별자’)** 하나 이상을 다른 소스와 공통으로 공유해야 합니다.
* 식별자를 사용하여 사용자 수준 데이터를 사용자 수준 어트리뷰션 데이터와 일치시킴으로써, DCR은 결합된 사용자 수준 데이터 세트를 생성합니다.
* 그런 다음 DCR은 사용자 개인정보 보호를 유지하면서 인사이트를 제공하기 위해 이 데이터를 처리하여 사용자가 정의한 특성 **('구분')** 에 따라 **그룹화된 집계 리포트**를 생성합니다.

<div id="dcr-terminology" />

## DCR 관련 용어

다음은 자주 사용되는 DCR 용어입니다.

* **커넥터:** DCR 데이터가 저장된 (광고주 소유의) AWS 또는 GCS 버킷입니다. 커넥터에는 DCR로 유입되는 소스 데이터의 폴더 및/또는 리포트가 유출되는 대상 폴더가 포함될 수 있습니다. DCR로 들어오고 나가는 데이터에는 단일 커넥터 또는 여러 개의 커넥터를 사용할 수 있습니다.
* **소스:**
  * DCR로 들어오는 퍼스트 파티 데이터 파일(앱스플라이어 어트리뷰션 데이터와의 매칭 및 보강용)입니다. 새 버전의 소스 파일을 6시간마다 업로드하여 처리할 수 있습니다. 앱스플라이어 DCR 플랫폼에서 소스를 설정할 때, 소스의 **구조**와 **위치**를 정의합니다.
    * **소스 구조:** 소스의 데이터 필드 목록과 리포트에서 사용되는 방식(식별자, 차원 또는 메트릭)에 대해 각각에 할당하는 카테고리입니다.
    * **소스 위치:** 업데이트할 때마다 앱스플라이어가 소스 파일을 가져오는 클라우드 서비스 폴더입니다. 이 폴더는 버킷(‘커넥터’) 내에 있습니다.
  * **어트리뷰션 데이터:** 앱스플라이어 계정의 사용자 수준 어트리뷰션 데이터(DCR에서 광고주 데이터의 매칭 및 보강에 사용)입니다.
* **리포트:** 처리 후 DCR에서 나오는 데이터 파일입니다. 관련 소스 파일의 새 버전이 업로드될 때마다 리포트가 생성됩니다. 앱스플라이어 DCR 플랫폼에서 리포트를 설정할 때, 리포트의 **구조**와 **대상**을 정의합니다.
  * **리포트 구조:** 리포트 작성에 사용할 광고주 소스 및 어트리뷰션 데이터, 이를 결합할 식별자, 포함할 지표 및 리포트를 그룹화할 차원을 지정합니다.
  * **보고 대상:** 앱스플라이어가 리포트를 처리할 때마다 전송하는 클라우드 서비스 폴더입니다. 이 폴더는 버킷(‘커넥터’) 내에 있습니다.

<div id="working-with-the-dcr-setup-workflow" />

## DCR로 작업하기(워크플로 설정)

앱스플라이어 데이터 클린룸(DCR)은 업로드할 데이터 유형, 수신하는 리포트, 처리 타이밍 또는 빈도를 매우 유연하게 선택할 수 있습니다. 따라서 비교적 중요한 계획 및 설정 프로세스가 필요하며, 조직 내 여러 사람의 협업이 필요할 수 있습니다.

다음 단계에 따라 조직의 요구 사항을 충족하도록 DCR을 설정하세요.

1. DCR에서 받고 싶은 리포트를 생각해 보세요. 이러한 리포트는 앱스플라이어 어트리뷰션 데이터로 광고주 소스를 보강한 결과물입니다. 리포트를 생성하기 위해 DCR에 업로드해야 하는 당사자 데이터 소스를 결정합니다.
2. 소스 및 리포트를 지원하기 위한 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-setting-up-cloud-services">기본 클라우드 스토리지 구조</Anchor>를 만듭니다.
3. 데이터를 가져오고 소스 데이터 파일을 생성할 쿼리를 정의하며, 소스 데이터 파일의 프로토타입을 생성합니다.
4. 데이터를 가져오고 소스 하위 폴더를 만들고, 소스 및 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-sources#_success-files">\_SUCCESS 파일</Anchor>을 정기적으로 업로드하는 자동화를 개발합니다.
5. 앱스플라이어 DCR 플랫폼에서 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-sources">소스</Anchor>를 설정합니다.
6. 앱스플라이어 DCR 플랫폼에서 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-reports">리포트</Anchor>를 설정합니다.
7. DCR이 리포트를 클라우드 스토리지로 전달한 후 리포트를 수집하는 자동화를 개발합니다.

<div data-zendesk-anchors="introduction=%EC%86%8C%EA%B0%9C h_01HE7SDH5PWCW6YG00GC12W4BS=%EC%86%8C%EA%B0%9C how-does-it-work=%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%EB%90%98%EB%82%98%EC%9A%94 h_01HE7SDH5PW64CHNJVJJ30V5ZY=%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%EB%90%98%EB%82%98%EC%9A%94 how-does-the-dcr-obtain-data=dcr%EC%9D%80-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%88%98%EC%A7%91%ED%95%98%EB%82%98%EC%9A%94 h_01HE7SDH5P82HCEN52ZBPMQV16=dcr%EC%9D%80-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%88%98%EC%A7%91%ED%95%98%EB%82%98%EC%9A%94 what-does-the-dcr-do-with-the-data=dcr%EC%9D%80-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A1%9C-%EC%96%B4%EB%96%A4-%EC%9E%91%EC%97%85%EC%9D%84-%EC%88%98%ED%96%89%ED%95%98%EB%82%98%EC%9A%94 h_01HE7SDH5PWDQ61389TT7V83F8=dcr%EC%9D%80-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A1%9C-%EC%96%B4%EB%96%A4-%EC%9E%91%EC%97%85%EC%9D%84-%EC%88%98%ED%96%89%ED%95%98%EB%82%98%EC%9A%94 dcr-terminology=dcr-%EA%B4%80%EB%A0%A8-%EC%9A%A9%EC%96%B4 h_01HE7SDH5P3QSG874XASXNH1YS=dcr-%EA%B4%80%EB%A0%A8-%EC%9A%A9%EC%96%B4 working-with-the-dcr-setup-workflow=dcr%EB%A1%9C-%EC%9E%91%EC%97%85%ED%95%98%EA%B8%B0%EC%9B%8C%ED%81%AC%ED%94%8C%EB%A1%9C-%EC%84%A4%EC%A0%95 h_01HE7SDH5P0S9542P2CB22KKVT=dcr%EB%A1%9C-%EC%9E%91%EC%97%85%ED%95%98%EA%B8%B0%EC%9B%8C%ED%81%AC%ED%94%8C%EB%A1%9C-%EC%84%A4%EC%A0%95" />
