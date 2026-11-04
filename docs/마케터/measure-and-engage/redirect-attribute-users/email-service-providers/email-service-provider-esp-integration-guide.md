---
title: 이메일 서비스 제공업체(ESP) 연동 가이드
metadata:
  keywords:
    - Email
    - Advertisers
    - Developers
    - Premium
    - Email service providers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-12-31T10:43:24Z'
  edited_at: '2026-10-14T10:29:25Z'
  id: 360004556077
  locale: ko
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ko/articles/360004556077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 원링크 브랜드 링크와 딥링킹을 사용하여 ESP가 연동된 이메일 캠페인을 만들고, 매끄러운 사용자 경험을 제공하여 전환율을 높입니다.

<div id="about-esp-integration" />

## ESP 연동 소개

이메일 마케팅은 고객 및 잠재 고객과 소통할 수 있는 쉽고 강력하며 효과적인 마케팅 방법입니다. 이미 많은 마케터들이 이메일 서비스 제공업체(ESP)를 통해 대규모의 이메일 캠페인을 실행하고 있습니다. 완벽한 유저 여정을 돕는 쉽고 간단한 프로세스여야 하지만, 그렇지 않은 경우가 많습니다.

**무엇이 문제일까요?**

일반적으로 ESP가 분석을 처리하는 방식에 문제가 있는데, 이 방식은 딥링크를 차단시키고 부정적인 모바일 유저 경험을 가져다주는 경향이 있습니다. 딥링킹은 유저가 앱 내 특정 위치로 바로 랜딩하도록 해주는 동작 기능이기 때문에 전환에 있어 매우 중요한 역할을 하는 기능입니다. ESP가 전송하는 이메일 캠페인에서 매끄러운 딥링킹을 제공하는 것은 쉽지 않습니다. ESP가 측정 목적으로 딥링크를 '래핑'하면 iOS 유니버셜 링크 및 안드로이드 앱 링크에 요구되는 앱-도메인 연결이 끊어지기 때문입니다. 다음과 같이 원치 않는 결과를 가져옵니다.

* 유저가 앱으로 딥링킹되지 않고 모바일 웹사이트로 라우팅 됨
* URI 스킴 딥링킹 사용으로 보안성과 유저 경험 질 저하

<Image alt="53242 KB.png" src="https://files.readme.io/53db119f60e3fe2dfaf58b8a87e14595eeb9dde375bf87f7617f36a463ee0ced-30227717940753.png" width="688px" />

**해결책은 무엇일까요?**

이러한 문제를 방지하고 모바일 유저에게 최상의 경험을 제공하려면 아래 섹션에서 해당 ESP를 클릭하고 연동 가이드라인을 확인하세요. 앱스플라이어 연동 솔루션은 ESP 서버와 도메인 이름 사이 중개자 역할을 하며 일부 ESP를 지원합니다. 프록시로 작동하여 딥링킹을 가능하게 하는 연결 파일(AASA/애셋 링크)을 제공합니다.

<div id="other-esps" />

<div id="supported-esps" />

## 지원되는 ESP

모바일 앱 유저에게 ESP 이메일 캠페인을 발송하면 어트리뷰션과 딥링킹 문제가 발생할 수 있습니다. 이러한 문제를 방지하기 위해, 아래 섹션에서 해당 ESP를 클릭하여 자세한 가이드라인을 확인하세요.

| 지원되는 ESP 목록 | 앱스플라이어 베타 통합 지원 유무 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="acoustic logo.svg" src="https://files.readme.io/b3dac2e0a4f326da76584ed95ee2cd61683edff054c67110c56b95a361444acb-38086051586577.svg" width="211px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB blueshift.png" src="https://files.readme.io/038b29f54fdb4e20775d7c1af0e6543a78351abdfad8b8d7d029a1fdd5b5de7b-32377991388945.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB braze.png" src="https://files.readme.io/41e9614c7a35cd18f1d17d5958d6a7243e53a1af0a3e56935342b90103d7be20-32378022189969.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB CleverTap.png" src="https://files.readme.io/f3190c5c82b380e93d70bbccccf279f78decf6a223bcab3ca62958356202e1a1-32378022192657.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB customer.io.png" src="https://files.readme.io/e893909294e6397226b10dbad55f06644cf7a9e6db0a3020280495a9d17fc53c-32378022194833.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/emaillabs-integration-with-appsflyer"><Image alt="53798 KB EmailLabs (1).png" src="https://files.readme.io/32d440b286d811ac5c0120527084e829cef389cf875b6af863e483e1cc119d36-51912551927697.png" width="343px" /></Anchor> | 아니요. 자사 고유의 리디렉션 방법을 사용합니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB emarsys.png" src="https://files.readme.io/449120ed88bb0540b758530ca5d8884e2e8210485859b17eb272d61e218566a1-32378022206737.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB expertsender.png" src="https://files.readme.io/25141c53c10b3f2eed600567b04849dda88f6b379bb71ae00bcc2e85fa0171e7-32377991413393.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Insider (1).svg" src="https://files.readme.io/544b4f408b64e99e037cfca238c578185db66d87d85f7d329e39d62b253ba618-36655909659153.svg" width="145px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/iterable-integration-with-appsflyer"><Image alt="53798 KB ITERABLE (1).png" src="https://files.readme.io/117d55213b184ac6aaed30984f9d9420aeb33d563a254dbe767007d069b87535-51912545062161.png" width="343px" /></Anchor> | 아니요. 자사 고유의 리디렉션 방법을 사용합니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB klaviyo.png" src="https://files.readme.io/69c38e0a4c025aa0eae473a10028fce0a59236855118f7a5b6fb3e82c0486fc3-51912545062929.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB MailExpress (2).png" src="https://files.readme.io/7a196f7d2825ea7dbb14a7deda4af907c5056957b63e93c53a7550bd8394a5c4-32377991435921.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB Mailgun.png" src="https://files.readme.io/4a19bb320d3abf176ca3bb2384f4de5a06d8e2f1925df2fc6e082372b711b19a-32377991438865.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB moengage.png" src="https://files.readme.io/d2316501fe1f428d4337a4924a59e93545b50171d173b3371bdd4dd180805509-32377991440913.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB ongage.png" src="https://files.readme.io/d3dd0839abd7ee6fbcf065a815d71a20885b0a09beabd37452c47d0396ee1d6e-32378022240273.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/oracle-responsys-integration-with-appsflyer"><Image alt="53798 KB ORACLE (1).png" src="https://files.readme.io/8f6b7a560dbddfaafc87c870aec7cdb077c5fb5b14e41531048161f780bf12b7-51912551934865.png" width="343px" /></Anchor> | 아니요. 자사 고유의 리디렉션 방법을 사용합니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB RD STATION.png" src="https://files.readme.io/91a24e7341c87484a4c06d077a1ee7fd7a04b3817b63ced27cec944421ca58aa-32378022248977.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB Reteno.png" src="https://files.readme.io/4e1d8fab29601c1d3c2015a7253258a9c152cd987ee6c5f0125c6f6e79a370a1-32377991454609.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB SAILTHRU.png" src="https://files.readme.io/61b721936f4f9cc64ee9551a213865eca2bea188599311f79d92d945204a713b-32378022253841.png" width="343px" /></Anchor> | 예 |
| <Image alt="salesforce.png" src="https://files.readme.io/c9d40ec29e6aa035a1a7446310dce7b64f04d9512d05ceed11a413b34d9e0b60-51912551935633.png" width="147px" /> | 아니요. 자사 고유의 리디렉션 방법을 사용합니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB sendgrid.png" src="https://files.readme.io/f4c3217e956db7e922a6150597d596c2c4848e5aa0a43b2347824aacbeb2caa3-32378022256785.png" width="343px" /></Anchor> | 예 |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB SPARKPOST.png" src="https://files.readme.io/bec55e3c96bb80b736777e110d05df9009e015ef2c1cdd8b3d8088880264f593-32377991460369.png" width="343px" /></Anchor> | 예 |

<div data-zendesk-anchors="overview=esp-%EC%97%B0%EB%8F%99-%EC%86%8C%EA%B0%9C h_01J3JHJCCASM6E5QYJB5VHQ8HK=esp-%EC%97%B0%EB%8F%99-%EC%86%8C%EA%B0%9C supported-email-service-providers=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-esp h_01H92VH355BQ13SP72VNJEKW1E=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-esp" />
