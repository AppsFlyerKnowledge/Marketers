---
title: 광고주를 위한 포스트백 문제 해결
metadata:
  keywords:
    - Postback
    - Partner
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-04-04T07:09:26Z'
  edited_at: '2026-10-14T10:36:22Z'
  id: 14272573202833
  locale: ko
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ko/articles/14272573202833
---
> **한눈에 보기:** 요약: 파트너가 예상한 포스트백을 받지 못하는 주요 원인과 해결 방법을 찾아보게 됩니다. 아래의 각 항목을 살펴보고 원인이 될 수 있는지 확인하십시오.

<div id="check-the-integration-toggles" />

## 연동 토글 확인

다양한 토글을 통해 연동의 서로 다른 부분을 제어합니다. 토글의 상태가 포스트백을 받지 못하는 이유로 될 수 있습니다.

<div id="the-activate-partner-toggle-was-turned-off" />

<Accordion title="파트너 활성화가 꺼져 있습니다.">

파트너 활성화

![integration_turned_off.png](https://files.readme.io/d43b4f465749e343d9523e90e87e43b77a85cdd920f0c0770a94bcb7a585d920-14979273403793.png)

**연동 활성화 방법:**

1. 앱스플라이어의 사이드 메뉴에서**콜라보레이트(Collaborate )> 활성 연동(Active Integrations)을 선택합니다**.
2. 파트너의 연동 관리 아이콘을 클릭합니다.
3. 파트너 토글 활성화

파트너 활성화

* <span id="1703758710.321359"></span>에서 이메일 주소 dropdown)

</Accordion>

<div id="1703760110.503549" />

<div id="the-inapp-event-postbacks-toggle-was-turned-off" />

<Accordion title="인앱이벤트 포스트백이 꺼져 있습니다.">

리치 인앱이벤트에서 이는 포스트백이 전송되지 않았음을 의미합니다.

**인앱이벤트 포스트백을 켜려면:**

1. 앱스플라이어의 사이드 메뉴에서**콜라보레이트(Collaborate )> 활성 연동(Active Integrations)을 선택합니다**.
2. 파트너의 연동 관리 아이콘을 클릭합니다.
3. **연동** 탭까지 내려가세요.   

   ![integration-in_app_event_postbacks_toggle.png](https://files.readme.io/20dadaa71b8b54c4512e74a925e66cec9da5e8138bb28a545c5452eef2d38304-14627453566737.png)

</Accordion>

<div id="check-the-event-configuration" />

## 이벤트 설정 확인

이벤트는 특정 포스트백이 전송되지 않도록 설정할 수 있습니다.

<div id="the-event-wasnt-configured" />

<Accordion title="이벤트가 설정되지 않음">

설정된 인앱이벤트 목록에 이벤트가 포함되어 있는지 확인하십시오. 정의되지 않은 경우 포스트백이 전송되지 않습니다.

[![list_of_in_app_events.png](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)

1. 앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. 파트너의 연동 관리 아이콘을 클릭합니다.
3. **연동** 탭에서 **인앱이벤트 포스트백**까지 아래로 스크롤하여 이벤트 이름이 나타나는지 확인하십시오.

</Accordion>

<div id="the-event-was-configured-incorrectly" />

<Accordion title="이벤트가 잘못 설정됨">

<Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#이벤트-매핑">이벤트 매핑</Anchor>이 올바른지 확인하십시오. 앱스플라이어 이벤트 **(앱스플라이어가 모바일 앱 또는 S2S를 통해 수신한 이벤트 이름)가 매핑된 파트너 이름(파트너가 사용하는 정확한 이벤트 이름)과 일치하는지 확인하십시오.**

[![in_app_event_postback_mapping_2.png](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)

</Accordion>

<div id="the-event-was-configured-correctly-but-with-a-condition" />

<Accordion title="이벤트가 조건부적으로 올바르게 설정됨">

이벤트에 대한 조건이 정의된 경우 해당 조건에 따라 포스트백이 전송됩니다. 포스트백 전송을 제한하는 조건이 있는지 확인하십시오.

[altin\_app\_event\_condition\_\_1\_.pngalt](https://support.appsflyer.com/hc/article_attachments/51858070994833)

</Accordion>

<div id="the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner" />

<Accordion title="이벤트는 어트리뷰트된 파트너에게만 포스트백을 보내도록 설정됨">

인앱이벤트 설정이 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#포스트백-발송-옵션">**이 파트너에만** 또는 **오가닉을 포함한 모든 미디어 소스**</Anchor>에 포스트백을 보내도록 설정되어 있는지 확인하십시오. 이 파트너엑만으로설정된 경우 어트리뷰트된 파트너만 포스트백을 받을 수 있습니다.

[![in_app_event_sending_options.png](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)

</Accordion>

<div id="the-event-occurred-outside-of-the-configuration-window" />

<Accordion title="이벤트가 설정 기간 외에 발생함">

포스트백은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">포스트백 기간</Anchor> 설정에 따라 전송됩니다. 이 기간 이후의 이벤트에 대한 포스트백은 파트너에게 전송되지 않지만 이벤트는 여전히 앱스플라이어에 기록됩니다.

![in_app_event_postback_window.png](https://files.readme.io/21cae7825d557c1ee89c890ec64c922cb36e31be882850a26bfdc4e5595773f0-14661845664401.png)

<Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns">SRN</Anchor>의 경우 <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention#파트너-데이터-리텐션-기간">파트너 데이터 보존 기간</Anchor> 동안 인앱이벤트 포스트백이 전송된다는 것에 주목하십시오.

</Accordion>

<div id="the-attribution-link-was-configured-not-to-send-postbacks-for-installs" />

<Accordion title="어트리뷰션 링크는 인스톨에 대한 포스트백을 보내지 않도록 설정됩니다.">

어트리뷰션 링크에 `af_installpostback=false` 파라미터가 포함되면 인스톨은 기록되지만 포스트백은 파트너에게 전송되지 않습니다.

**어트리뷰션 링크를 보려면:**

1. 앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. 어트리뷰션 링크 탭으로 이동하고 아래로 스크롤하여 **어트리뷰션 링크** 를 확인합니다.

</Accordion>

<div id="privacy-restrictions" />

## 개인 정보 보호 제한

다음과 같은 경우, 앱스플라이어는 개인 정보 보호 제한으로 인해 포스트백을 전송하지 않습니다.

<div id="the-partner-didnt-set-up-advanced-privacy" />

<Accordion title="파트너가 프라이버시 강화 모드를 지원하지 않거나 설정하지 않음">

<Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch">프라이버시 강화 모드</Anchor>가 켜져 있지만 파트너가 프라이버시 강화 모드를 구성하지 않았거나 프라이버시 강화 모드를 지원하지 않는 경우 프라이<Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks#포스트백을-보내기-위한-템플릿의-종류">버시 강화 모드 집약형 포스트백</Anchor>을 받지 못합니다.

![partner_not_supporting_ap_postbacks.png](https://files.readme.io/1d8784e8994eba5c403ac706673490b91b7b34ed4d5dbea8c3fe58f227d382c5-15140294126353.png)

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms" />

<Accordion title="타사 플랫폼에 대한 매체사 제한">

<Anchor target="_blank" href="/marketers/ko/docs/discrepancies-between-appsflyer-and-third-party-platforms#타사-플랫폼에-대한-포스트백-제한">일부 매체 소스</Anchor>는 제3자와 데이터 공유를 제한합니다. 앱스플라이어는 이러한 매체사를 통해 획득한 사용자 수준 데이터를 타사 플랫폼 또는 서비스와 공유할 수 없습니다. 따라서 이러한 매체사의 모든 인스톨은 오가닉으로 전송됩니다. 메타 광고는 타사 플랫폼과 데이터를 공유하지 않는다는 것을 주목하십시오.

</Accordion>

<div id="the-sdk-was-set-not-to-share-information-with-the-partner" />

<Accordion title="SDK가 파트너와 정보를 공유하지 않도록 설정되었습니다.">

파트너가 정보를 수신하지 못하도록 SDK에 공유 필터가 구현되었습니다. 이 필터는 사용자의 명시적인 옵트아웃 요청에 의해 또는 앱 수명 주기 중 다른 시점에 활성화될 수 있습니다.

자세한 내용은 다음을 참조하세요.

</Accordion>

<div id="miscellaneous" />

## 기타

<div id="the-postback-was-sent-but-doesnt-show-on-the-partners-platform" />

<Accordion title="포스트백이 전송되었지만 파트너의 플랫폼에 표시되지 않음">

경우에 따라 앱스플라이어가 파트너에게 포스트백을 보내지만 파트너 측에서는 이를 표시하지 않을 수 있습니다. 이런 경우 파트너에게 문의하십시오.

**앱스플라이어에서 포스트백이 전송되었는지 확인하려면:**

1. **앱스플라이어의 사이드 메뉴에서** **리포트** > 로데이터 내보내기를 선택합니다.
2. **포스트백**(인스톨, 인앱이벤트, 리타게팅 전환, 인앱이벤트 리타게팅)에서 관련 리포트를 확인하십시오.

[![postback_reports.JPG](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)

</Accordion>

<div id="the-event-didnt-occur" />

<Accordion title="이벤트가 발생하지 않았거나 앱스플라이어로 전송되지 않음">

발생한 모든 이벤트는 <Anchor target="_blank" href="/marketers/ko/docs/activity-dashboard">**액티비티** 대시보드</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview?query=raw%20data%20reports">로데이터 리포트</Anchor>에서 찾아볼 수 있습니다. 거기에 표시되지 않은 이벤트는 발생하지 않았거나 앱스플라이어로 전송되지 않았음을 의미합니다.

이벤트가 SDK에 정의되지 않았을 수 있습니다. 이 경우 플랫폼에서 볼 수 없습니다.

이벤트가 발생했다고 생각되면 아래에서 활동 대시보드에 나타나는지 보는 방법을 확인하거나 로데이터 리포트를 만들어 찾아보십시오.

**활동 대시보드를 보는 방법:**

* **앱스플라이어의 사이드 메뉴에서분석 > 활동을 선택하고** 파트너 및 날짜 범위를 선택합니다.

**로데이터 리포트를 만드는 방법들려면:**

1. **앱스플라이어의 사이드 메뉴에서** **리포트** > 로데이터 내보내기를 선택합니다.
2. 리포트 만들기를 클릭합니다.
3. 관련 리포트를 선택합니다.
4. 날짜 범위와 필요한 필드를 선택하고 만들기를 클릭합니다 .
5. 리포트를 다운로드하여 이벤트를 찾아보십시오.

</Accordion>

<div id="differences-in-time-zones" />

<Accordion title="시간대의 차이">

앱스플라이어 플랫폼과 파트너 플랫폼 간의 시간대 차이로 인해 포스트백 수신에 불일치가 있을 수 있습니다. 앱스플라이어 대시보드 및 리포트는 선택한 시간대에 따라 표시됩니다.

**앱스플라이어에서 앱 시간대를 보려면:**

1. **앱스플라이어의 사이드 메뉴에서** **설정** > 앱 설정을 선택합니다.
2. **현지화**에서 앱 시간대를 봅니다.

</Accordion>

<div id="srns-missing-advertising-ids-idfagaid" />

<Accordion title="광고 ID가 누락된 SRN(IDFA/GAID)">

<Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid">앱스플라이어가 인스톨, 앱 열기 또는 인앱이벤트에 대한 포스트백을 보내지 않는SRN</Anchor>의 특정한 사례가 여러 가지 있습니다.

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms::40092c14" />

<Accordion title="타사 플랫폼에 대한 매체사 제한">

<Anchor target="_blank" href="/marketers/ko/docs/discrepancies-between-appsflyer-and-third-party-platforms#타사-플랫폼에-대한-포스트백-제한">일부 매체 소스</Anchor>는 제3자와 데이터 공유를 제한합니다. 앱스플라이어는 이러한 매체사를 통해 획득한 사용자 수준 데이터를 타사 플랫폼 또는 서비스와 공유할 수 없습니다. 따라서 이러한 매체사의 모든 인스톨은 오가닉으로 전송됩니다. 메타 광고는 타사 플랫폼과 데이터를 공유하지 않는다는 것을 주목하십시오.

</Accordion>

<div id="advanced-privacy-postbacks" />

<Accordion title="Advanced privacy 포스트백.">

포스트백은 <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks#포스트백을-보내기-위한-템플릿의-종류">고급 개인정보 보호 템플릿</Anchor>에 따라 전송됩니다.

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> <Anchor target="_blank" href="/partners/ko/docs/postback-troubleshooting-for-ad-networks">애드 네트워크에 대한 포스트백 트러블슈팅문제 해결</Anchor>

<div data-zendesk-anchors="activation-toggles=%EC%97%B0%EB%8F%99-%ED%86%A0%EA%B8%80-%ED%99%95%EC%9D%B8 h_01H9FT385FY1QJC6M2YVMZF2NC=%EC%97%B0%EB%8F%99-%ED%86%A0%EA%B8%80-%ED%99%95%EC%9D%B8 h_01H9FT385FJ0W62NB6FBB6ASKP=the-activate-partner-toggle-was-turned-off h_01H9FT385FKK7VQ293HH9RANBP=the-inapp-event-postbacks-toggle-was-turned-off event-configuration-issues=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95-%ED%99%95%EC%9D%B8 h_01H9FT385FW71JV2KKZ22TP6TN=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95-%ED%99%95%EC%9D%B8 h_01H9FT385FHFX4PNRQVRXX8A5X=the-event-wasnt-configured h_01H9FT385FE4GCP9D5XCNZ1FAR=the-event-was-configured-incorrectly h_01H9FT385FTT97PJ9NN09K0X9F=the-event-was-configured-correctly-but-with-a-condition h_01H9FT385FDEC21CAZ7V9BBT7M=the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner h_01H9FT385G8HSVJWWGKSRKT381=the-event-occurred-outside-of-the-configuration-window h_01H9FT385GDDV1D6X69JQWPN02=the-attribution-link-was-configured-not-to-send-postbacks-for-installs privacy-restrictions=%EA%B0%9C%EC%9D%B8-%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8-%EC%A0%9C%ED%95%9C h_01H9FT385G84E2A1J64VWG8H4Z=%EA%B0%9C%EC%9D%B8-%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8-%EC%A0%9C%ED%95%9C h_01H9FT385G3ECF0PXCE6S2GD5A=the-partner-didnt-set-up-advanced-privacy h_01H9FT385G9YMX9BAEYY0XQR4C=media-source-restrictions-on-thirdparty-platforms h_01HG0YAHWJ565C7BAXAXT75ACB=the-sdk-was-set-not-to-share-information-with-the-partner miscellaneous=%EA%B8%B0%ED%83%80 h_01H9FT385GSWRPKEHKJ4HXCX01=%EA%B8%B0%ED%83%80 h_01H9FT385GTSH1K93WNCARY2BA=the-postback-was-sent-but-doesnt-show-on-the-partners-platform h_01H9FT385G5HK6N2JEE8C6S245=the-event-didnt-occur h_01H9FT385GPVT9WAC6ZTPK6D10=differences-in-time-zones h_01H9FT385G8RXJD25KAQJ28TF6=srns-missing-advertising-ids-idfagaid h_01H9FT385GAYCY615W7M88XJT3=media-source-restrictions-on-thirdparty-platforms::40092c14 h_01JK86ZFXJGPVYJCAAVAY6F4YD=advanced-privacy-postbacks h_01HE7R6G699RG30ZSSQF02AK5Y=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
