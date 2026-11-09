---
title: SKAN 포스트백 사본을 iOS 15+에서 앱스플라이어로 직접 전송
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-08T12:09:25Z'
  edited_at: '2026-10-14T10:35:33Z'
  id: 4402320969617
  locale: ko
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ko/articles/4402320969617
---
> **한눈에 보기:** iOS 15부터 귀사의 앱을 구성하여 애드 네트워크뿐만 아니라 앱스플라이어에도 포스트백 사본을 발송하세요. 이를 통해 앱스플라이어가 전환 값(CV)을 검증하고 포스트백의 무결성을 확인할 수 있습니다. 앱스플라이어 Push API를 구성하여 선택한 추가 엔드포인트로 포스트백 사본을 전달합니다.

<div id="why-send-postback-copies-to-appsflyer" />

## 앱스플라이어로 포스트백 사본을 보내는 이유는?

* 모든 포스트백을 한곳에서 받아보세요: 포스트백에는 광고주에게 중요한 정보가 포함됩니다.—특히 유저의 품질을 측정하는 데 사용되는 CV가 포함됩니다. 포스트백의 CV는 암호화되지 않았으며 포스트백 서명에 포함되어 있지 않습니다. 그 결과, 애드 네트워크에서 보고한 CV는 검증될 수 없고 조작의 위험이 있습니다. 앱스플라이어는 Push API를 사용하여 귀사가 정의한 엔드포인트로 포스트백 사본을 전달합니다.
* 재다운로드 지표를 확인하세요. 일부 애드 네트워크는 앱스플라이어와 재다운로드 데이터를 공유하지 않습니다. 포스트백 사본은 전체 그림을 완성하는 데 도움이 됩니다.
* 퍼블리셔 앱 데이터 보기
* 터치형 인게이지먼트 보기

**참고!** 앱스플라이어는 여전히 애드 네트워크 포스트백을 받아야 합니다. 왜냐하면 그 안에는 추가 데이터(예: 캠페인 이름)가 포함되어 있기 때문입니다.

<div id="configure-your-app-to-send-postback-copies-to-appsflyer" />

## 귀사의 앱을 구성하여 앱스플라이어로 포스트백 사본을 발송하세요.

Apple 문서에 따르면 단일 SKAN 포스트백 엔드포인트를 설정할 수 있습니다.

**앱스플라이어 엔드포인트를 등록하려면:**

1. 귀사의 iOS 개발자에게 다음 앱 버전에서 SKAN 포스트백 엔드포인트로 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#sending-skan-postback-copies-to-appsflyer">앱스플라이어</Anchor>를 추가하도록 요청하세요.
2. iOS 앱을 제출하세요.
3. 새 버전이 게시되면 앱스플라이어로 포스트백이 발송됩니다.(TestFlight가 아님)
4. 수신된 포스트백은 <Anchor target="_blank" href="/marketers/ko/docs/skan-raw-data-reports">포스트백 복사 리포트</Anchor>에서 확인할 수 있습니다.

<div id="important" />

> 🚧 **중요!**
>
> SKAN 트래픽이 없는 앱은 설정을 완료한 후에도 다음 메시지를 볼 수 있습니다: '귀사의 앱은 iOS 포스트백 사본(iOS 15 이상)을 앱스플라이어로 보내도록 설정되지 않았습니다. 이는 귀사의 SKAN 측정 무결성을 보장하는 데 필요합니다.

<div id="common-misconceptions" />

## 흔한 오해

<div id="dont-believe-everything-you-hear" />

> 📘 **듣는 모든 것을 믿지 마세요!**
>
> 이 진술들은 사실인가 거짓인가요?
>
> <Image align="center" alt="참 또는 거짓.png" src="https://files.readme.io/77212d5a12ce2af35b0a4c87ca9e58213b4f9fd88c775007793e7abb5aaa3f04-35682597298577.png" />
>
> * 광고주는 이제 포스트백을 받기 위해 애드 네트워크에 의존하지 않습니다.
>   * **거짓. 광고주는 여전히 중요한 데이터를 디코딩하기 위해 애드 네트워크에 의존합니다. 예를 들어, SKAN 캠페인 ID를 캠페인 이름에 매핑할 수 있는 것은 애드 네트워크뿐입니다.**
> * 추가 엔드포인트를 설정하자마자 모든 포스트백 사본이 해당 엔드포인트로 전송됩니다.
>   * **거짓. 추가 엔드포인트 기능은 iOS 15 이상을 운영하는 디바이스에서만 사용할 수 있습니다. 이전 버전을 운영하는 디바이스에서는 포스트백 사본이 발송되지 않습니다.**

<div id="traits-and-limitations" />

## 특성 및 제한 사항

앱이 앱스플라이어에 포스트백 사본을 발송하도록 구성된 후, 대시보드에 표시되기까지 몇 일이 소요될 수 있습니다.

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_an_advertised_app?changes=latest_minor#see-also">Apple 개발자</Anchor>

<div data-zendesk-anchors="why-send-postback-copies-to-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A1%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%82%AC%EB%B3%B8%EC%9D%84-%EB%B3%B4%EB%82%B4%EB%8A%94-%EC%9D%B4%EC%9C%A0%EB%8A%94 h_01HE7SV29Y7DNSKAAR91MJX986=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A1%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%82%AC%EB%B3%B8%EC%9D%84-%EB%B3%B4%EB%82%B4%EB%8A%94-%EC%9D%B4%EC%9C%A0%EB%8A%94 configure-your-app-to-send-postback-copies-to-appsflyer=%EA%B7%80%EC%82%AC%EC%9D%98-%EC%95%B1%EC%9D%84-%EA%B5%AC%EC%84%B1%ED%95%98%EC%97%AC-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A1%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%82%AC%EB%B3%B8%EC%9D%84-%EB%B0%9C%EC%86%A1%ED%95%98%EC%84%B8%EC%9A%94 h_01HE7SV29YDFA5Z0X4WS87YK0Y=%EA%B7%80%EC%82%AC%EC%9D%98-%EC%95%B1%EC%9D%84-%EA%B5%AC%EC%84%B1%ED%95%98%EC%97%AC-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A1%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%82%AC%EB%B3%B8%EC%9D%84-%EB%B0%9C%EC%86%A1%ED%95%98%EC%84%B8%EC%9A%94 h_01HH9WCVH4C37ZGMRZRB7EQT6B=%EC%A4%91%EC%9A%94 common-misconceptions=%ED%9D%94%ED%95%9C-%EC%98%A4%ED%95%B4 h_01HE7SV29YC855TGCXTCT4KHRN=%ED%9D%94%ED%95%9C-%EC%98%A4%ED%95%B4 h_01HE7SV29YMMTPH6EKYF3GQYEN=%EB%93%A3%EB%8A%94-%EB%AA%A8%EB%93%A0-%EA%B2%83%EC%9D%84-%EB%AF%BF%EC%A7%80-%EB%A7%88%EC%84%B8%EC%9A%94 traits-and-limitations=%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HHH74CC5X0T5M1F86XWMNH9V=%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HE7SX466CMCC03K99H68ZRBN=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
