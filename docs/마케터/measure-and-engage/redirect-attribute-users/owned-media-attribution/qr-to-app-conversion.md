---
title: QR에서 앱으로 전환
metadata:
  keywords:
    - OneLink
    - Advertisers
    - owned media
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2020-11-04T09:49:23Z'
  edited_at: '2026-10-14T10:26:36Z'
  id: 360015119718
  locale: ko
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ko/articles/360015119718
---
> **한눈에 보기:** 한눈에 보기: OneLink로 생성된 QR 코드를 사용하여 데스크톱, TV, CTV 또는 오프라인 유저를 모바일 앱 유저로 전환하십시오.

![6005_QR_code_4.jpg](https://files.readme.io/6db45d7e82bc33ba8af8c6e7d096011d71b06766da9df348dccfa1b3e4aa380d-12368835107601.jpg)

## 모바일, 비모바일, 오프라인 트래픽을 모바일 앱 유저로 전환

원링크에서 생성된 QR 코드를 데스크톱, TV, CTV 또는 오프라인 광고(예: 매장 내 디스플레이, 브로슈어 및 포장)에 게시하면 다음과 같은 이점이 있습니다.

* 유저는 모바일 장치로 코드를 빠르고 쉽게 스캔하여 앱을 다운로드하고 설치할 수 있습니다.
* 유저는 앱 스토어로 이동하여 앱을 검색하는 데 필요한 시간과 노력을 절약하여 QR에서 앱으로의 설치 전환율을 크게 높입니다.
* 이 변환 방법은 SMS를 우회하므로 개인 정보가 보호되며 유저는 문자 메시지를 보낼 전화번호와 같은 개인 정보를 제공할 필요가 없습니다.
* 쉽게 설치를 어트리뷰션하고 광고의 효과를 측정할 수 있습니다.

QR 코드는 다음 중 하나로 생성할 수 있습니다.

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#qr-codes">OneLink Smart Script</Anchor> (웹-앱 데스크톱 흐름을 위해 특별히 설계됨)를 사용하여 동적으로

<div id="qr-to-app-conversion" />

<Accordion title="QR에서 앱으로 전환">

#### 수동 QR 코드 설정

**선행 조건:**

* 최소 1개 이상의 앱이 있는 앱스플라이어 계정이 필요합니다.
* 어트리뷰션의 경우: 각 모바일 앱에 <Anchor target="_blank" href="/marketers/ko/docs/integrate-the-appsflyer-sdk">앱스플라이어 SDK가 설치되어 있어야 합니다.</Anchor>
  * SDK가 아직 앱에 설치되지 않은 경우에도 작동하는 리디렉션 링크를 생성할 수 있지만 대시보드에서 딥링크, 디퍼드 딥링크 또는 설치 측정은 불가능합니다.

1. * 1. [추천] 새 링크를 만들고 사용자 지정 미디어소스를 설정합니다. 예: **desktop\_web**. 기존 링크의 QR 코드를 사용하면 작동합니다. 그러나 신고를 위해 미디어소스를 다른 링크와 공유하지 않는 것이 좋습니다. 대신 전용 미디어소스가 원본이 있는 별도의 링크를 사용합니다.
     2. **클릭 후**링크 생성, QR 코드가 표시됩니다.
     3. QR 코드를 클릭하여 SVG 또는 PNG 형식의 전체 해상도로 다운로드합니다.
2. 다른 이미지/콘텐츠를 추가하는 것과 동일한 방식으로 광고에 QR 코드를 추가합니다.
   * [모범 사례를](/docs/qr-to-app-conversion#best-practices) 참조하세요.
   * 개발자의 도움이 필요할 수 있습니다.

</Accordion>

<div id="customize-qr-code" />

<Accordion title="QR 코드 사용자 지정">

![OnelinkQRFinal__1_.gif](https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif)

원링크를 통해 생성된 QR 코드는 다음과 같이 사용자 지정할 수 있습니다.

* 로고를 QR 코드에 추가하기
* QR 코드의 색상 변경하기

**참고**:

* QR 코드 사용자 지정은 개별 링크 수준이 아닌 템플릿 수준에서 이루어집니다. 따라서 사용자 지정은 편집된 템플릿을 기반으로 하는 모든 QR 코드에 영향을 미칩니다.
* 스마트 스크립트를 통해 생성된 QR 코드는 사용자 지정할 수 없습니다.

**QR 코드를 사용자 지정하는 방법**:

1. 앱스플라이어 대시보드에서 **원링크 관리** > **경험 및 딥링킹**으로 이동합니다.
2. 그리고 QR 코드 편집기가 열립니다.
3. 로고가 호스팅되는 URL을 입력합니다. 예: https://yourbrand.com/logo.png.  

   로고 요구사항:

   * PNG 또는 JPG 형식
   * 투명한 배경의 정사각형 또는 원형
   * 최소 크기 400 x 400 픽셀
   * 인쇄를 위해 최대 이미지 해상도 사용
4. QR 코드 색상을 설정합니다.
5. **저장**을 클릭합니다.

</Accordion>

<div id="measure-qrtoapp-conversions" />

<Accordion title="QR에서 앱으로의 전환 측정">

노출수(데스크톱 페이지뷰의 경우), 클릭수(QR 코드 스캔의 경우) 및 앱 설치를 비교하여 다양한 광고/미디어소스에서 QR 코드의 성능과 배치를 측정할 수 있습니다.

**QR에서 앱으로의 전환을 측정하는 방법은 다음과 같습니다**.

1. 앱스플라이어에서 개요 대시보드 또는 기타 앱스플라이어 분석 도구를 확인하고 QR 코드 미디어소스(예: **desktop\_web**)를 사용하여 총 **클릭** 및 **설치를** 기록합니다.
2. 웹 분석 소프트웨어를 사용하여 총 데스크톱 페이지 보기(노출수)를 기록합니다.
3. 성능 측정:
   * <Anchor target="_blank" href="/marketers/ko/docs/about-conversion-rates#마케팅-퍼널-단계-및-전환율-1">광고 클릭률</Anchor>
   * <Anchor target="_blank" href="/marketers/ko/docs/about-conversion-rates#마케팅-퍼널-단계-및-전환율-1">클릭-인스톨 전환율</Anchor>

</Accordion>

<div id="best-practices" />

<Accordion title="모범 활용 사례">

다음은 QR에서 앱으로의 전환을 극대화하기 위한 팁입니다.

* 데스크톱의 경우 수동 QR 코드 설정을 사용하는 경우 웹사이트에 별도의 페이지를 만들어 QR 코드를 배치합니다.
  * 페이지의 URL 슬러그(예: /app, /download-app 또는 **/mobile-app**)를 선택합니다.
  * 데스크톱/큰 화면 너비에 대해서만 페이지를 볼 수 있도록 합니다.
* 모든 광고:
  * 광고의 QR 코드를 크고 고해상도로 만들어 쉽게 스캔할 수 있도록 합니다.
  * 눈에 잘 띄는 위치에 있는 **앱 스토어**에서 다운로드 및 **Google Play에서 다운로드** 배지를 시각적 트리거(링크가 아님)로 추가합니다.
  * QR 코드를 스캔하는 방법에 대한 지침을 추가하는 것이 좋습니다.
* 이미 원링크를 사용하고 계신가요? 이메일 등에 사용되는 *다른* 사용자 지정 원링크에서 QR 코드가 포함된 페이지의 URL인 값을 사용하여 **af\_web\_dp** 매개변수를 추가합니다. 이렇게 하면 데스크톱 유저가 앱 스토어 대신 웹 페이지로 연결되는 링크를 클릭하게 됩니다.  

  [![](https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg)](https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg)

</Accordion>

<div data-zendesk-anchors="converting-mobile-nonmobile-and-offline-traffic-into-mobile-app-users=%EB%AA%A8%EB%B0%94%EC%9D%BC-%EB%B9%84%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%98%A4%ED%94%84%EB%9D%BC%EC%9D%B8-%ED%8A%B8%EB%9E%98%ED%94%BD%EC%9D%84-%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%95%B1-%EC%9C%A0%EC%A0%80%EB%A1%9C-%EC%A0%84%ED%99%98 h_01HKWVMKP3QT59EXPHQEPHW8K9=%EB%AA%A8%EB%B0%94%EC%9D%BC-%EB%B9%84%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%98%A4%ED%94%84%EB%9D%BC%EC%9D%B8-%ED%8A%B8%EB%9E%98%ED%94%BD%EC%9D%84-%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%95%B1-%EC%9C%A0%EC%A0%80%EB%A1%9C-%EC%A0%84%ED%99%98 h_01HKWWQXVC11E8M3NV3A03SWYD=qr-to-app-conversion manual-qr-code-setup=%EC%88%98%EB%8F%99-qr-%EC%BD%94%EB%93%9C-%EC%84%A4%EC%A0%95 h_01HKWWQXVCB96WDMBSE9WH9ZC5=%EC%88%98%EB%8F%99-qr-%EC%BD%94%EB%93%9C-%EC%84%A4%EC%A0%95 h_01HKWVMKP3R5C5FPH010ZJZAHS=customize-qr-code h_01HKWVMKP3XTF6NNPNM8J00NWD=measure-qrtoapp-conversions h_01HKWVMKP3P6FNRPP1X7ZTNH10=best-practices" />
