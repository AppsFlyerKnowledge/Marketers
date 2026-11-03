---
title: 원링크 스마트 스크립트 개요
metadata:
  keywords:
    - OneLink
    - Adwords
    - Advertisers
    - referral
    - referal
    - landing
    - redirect
    - gclid
    - facebook
    - landing page
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2018-12-12T16:32:47Z'
  edited_at: '2026-10-14T10:32:14Z'
  id: 360000677217
  locale: ko
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ko/articles/360000677217
---
> **한눈에 보기:** 원링크 스마트 스크립트를 사용하여 모든 소스에서 온 모바일 웹 사이트 방문자를 모바일 앱 사용자로 전환하고 어트리뷰트합니다.

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

## 원링크 스마트 스크립트 소개

사용자는 앱 스토어 페이지에 도달하기 전 또는 광고 캠페인에 참여한 후에 모바일 웹 사이트에 도착합니다. 그러나 다음과 같이 작동하는 두 번의 클릭이 있습니다.

* 웹 페이지로 연결하기
* 웹 페이지에서 앱 스토어에서 연결하기

이 시나리오에서는 어트리뷰션과 딥링킹이 문제가 됩니다. 결국 앱을 다운로드한 사용자에 의한 인스톨은 잘못 어트리뷰트되거나 오가닉으로 어트리뷰트될 수 있습니다. 이 문제는 첫 번째 클릭이 애드 네트워크, Google 클릭 또는 온드 미디어소스에서 발생하는 경우에도 발생할 수 있습니다.

원링크 스마트 스크립트는 다음과 같은 점에서 이러한 문제를 해결합니다.

* 웹 페이지로 연결되는 입력 URL을 사용하여, 앱 스토어로 연결되는 고유한 출력 원링크 롱 URL을 동적으로 생성합니다.
* 애드 네트워크, SRN, Google 클릭 및 온드 미디어를 포함한 모든 미디어소스에 대한 정확한 웹-투-앱 어트리뷰션을 제공합니다.
* 딥링킹에 사용할 수 있습니다.
* 웹 페이지 또는 랜딩 페이지에서 원활하게 실행됩니다.
* 스마트 배너를 사용할 필요가 없습니다.    
  **참고**: 스마트 배너는 다양한 업계에서 효과적인 전환 도구로 사용할 수 있으며, 개발자 없이도 설정할 수 있습니다. 단, 사용자 여정에 배너라는 단계가 추가됩니다.
* 마케터가 Google Tag Manager에서 설정할 수 있습니다.

원링크 스마트 스크립트에는 두 가지 버전이 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors">**원링크 스마트 스크립트 V2 (추천)**</Anchor>: 처음으로 원링크 스마트 스크립트를 설정하는 경우, 해당 버전의 사용을 권장드립니다. 앱스플라이어 UI에서 구성할 수 있으며, 개발자 작업 부분이 더 쉬워지고 Google Tag Manager를 사용하여 설정할 수도 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/legacy-onelink-smart-script-v1-setup">**원링크 스마트 스크립트 V1(레거시)**</Anchor>: 이미 원링크 스마트 스크립트를 설정한 경우, 이 버전에 대한 문서를 참고하여 스크립트를 유지관리하고 편집하십시오. **참고**: 반드시 필요하지는 않지만, V2로 마이그레이션하는 것을 권장합니다. 

> 📘 **참고사항**
>
> 원링크 스마트 스크립트가 적합한 솔루션인지 잘 모르시겠나요? 원링크 스마트 스크립트를 다른 앱스플라이어 웹-투-앱 솔루션과 <Anchor target="_blank" href="/marketers/ko/docs/convert-your-mobile-web-visitors-to-app-users">비교해 보십시오</Anchor>.

### 예시

이 섹션의 예에서는 원링크 스마트 스크립트를 사용하여 정확한 어트리뷰션을 생성하는 방법 혹은 딥링킹 기능을 제공하는 출력 원링크 URL을 생성하는 방법을 보여줍니다. 특정 미디어소스가 있는 캠페인 유형에 대한 사용 사례에 대해서는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#활용-사례">사용 사례</Anchor>를 참조하십시오.

<div id="attribution" />

<Accordion title="어트리뷰션">

마크는 호텔 프랜차이즈의 마케팅 담당자입니다. 엠마는 플로리다 올랜도에 있는 호캉스를 광고하는 이메일을 받습니다. 이메일의 링크는 다음과 같습니다:  https://hotel.me/pid=email&c=orlando

링크는 사용자를 호텔의 모바일 웹사이트로 리디렉션합니다. 거기에서 사용자들은 호텔의 모바일 앱을 다운로드하라는 버튼을 보게 됩니다. 원클릭 스마트 스크립트는 이메일의 원래 링크와 동일한 **pid** 및 **c** 파라미터를 포함하는 URL을 자동으로 생성합니다. 링크는 다음과 같습니다: https://hotel.onelink.me/Ac4G?pid=email&c=orlando

사용자가 모바일 사이트의 버튼을 클릭하여 앱을 다운로드하면 앱 인스톨은 마크의 올랜도 이메일 캠페인에 어트리뷰트됩니다.

</Accordion>

<div id="deep-linking" />

<Accordion title="딥링킹">

엠마는 플로리다 올랜도에 있는 호캉스에 대한 광고 이메일을 받습니다.

이메일 링크는 다음과 같은 형태입니다. https://hotel.me?type=email&campaign=Florida&city=orlando

링크를 클릭하면 호텔의 모바일 웹 사이트로 리디렉션됩니다. 리디렉션된 웹사이트에서 호텔의 모바일 앱을 다운로드하도록 초대하는 버튼을 볼 수 있습니다. 원클릭 스마트 스크립트는 이메일의 원래 링크와 동일한 **pid** 및 **c** 파라미터를 포함하는 URL을 자동으로 생성합니다. 링크는 다음과 같은 형태입니다. https://hotel.onelink.me/Ac4G?pid=email&c=Florida&deep_link_value=orlando

**엠마가 모바일 사이트의 버튼을 클릭하면 앱 스토어로 리디렉션됩니다. 그리고 앱을 다운로드하여 실행하면, 앱의 올랜도 호캉스 페이지와 딥링킹됩니다.**

> 📘 **참고사항**
>
> 딥링킹은 앱 개발사가 구현한 앱 설정에 따른 것입니다. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#캠페인을-위한-원링크-링크-생성하기">더 알아보기</Anchor>.

</Accordion>

<div data-zendesk-anchors="about-onelink-smart-script=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%86%8C%EA%B0%9C h_01HE7RW9G26CNME9TP350GFGS4=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%86%8C%EA%B0%9C h_01HE7RW9G2BV2NFJ0YZ9QKAA2V=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD examples=%EC%98%88%EC%8B%9C h_01HE7RW9G2WBZ1A0RS66CJ7BNH=%EC%98%88%EC%8B%9C h_01HE7RW9G24Y604NTZFGKJJXSS=attribution h_01HE7RW9G2ZDDWE1M1B2G175ZF=deep-linking h_01HE7RW9G3W5GKQ2CD2BZW8YAW=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-1" />
