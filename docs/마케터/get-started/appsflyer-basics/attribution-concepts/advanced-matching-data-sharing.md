---
title: 고급 매칭 데이터 공유
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-06-18T14:23:54Z'
  edited_at: '2026-10-14T10:27:35Z'
  id: 47876839961489
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/47876839961489
---
> **한눈에 보기:** 고급 매칭 데이터 공유를 통해 이메일 및 전화번호와 같은 해시 처리된 사용자 식별자를 앱스플라이어 에서 선택한 광고 네트워크로 전달할 수 있으므로 파트너는 기기 ID 없이도 이벤트를 광고 참여와 연결할 수 있습니다.

<div id="about-advanced-matching-data-sharing" />

## 고급 매칭 데이터 공유에 대하여

기기 식별자를 사용할 수 있는 경우가 줄어들면서 광고 네트워크는 광고 참여를 연결하기 위해 자사 데이터에 점점 더 의존하고 있습니다. 고급 매칭 데이터 공유는 해시 처리된 식별자를 개인정보 보호 규정을 준수하는 형식으로 지원되는 파트너에게 전달함으로써 이러한 격차를 해소합니다.

이 기능은 선택 사항이며 파트너별로 구성할 수 있습니다. 지원되는 네트워크 에서 앱스플라이어 활성화되면 설치, 재참여 및 인앱 이벤트 대한 이벤트 데이터와 함께 해시된 식별자를 전달합니다.

> 🚧 **중요!**
>
> 모든 식별자는 앱스플라이어 도달하기 전에 SHA-256으로 해싱되어야 합니다. 이는 SDK 통한 기기 내 해싱 또는 S2S API 통한 서버 측 해싱 모두에 해당합니다. 평문 데이터는 절대 수신, 저장 또는 전송되지 않으며, 유효성 검사에 실패한 가치 은 수집 단계에서 모두 폐기됩니다.

<div id="supported-partners" />

### 지원되는 파트너:

고급 매칭 데이터 공유의 범위는 파트너별로 다릅니다. 스냅챗 과 틱톡은 설치, 재참여 및 인앱 이벤트 지원 반면, 구글 과 Meta 인앱 이벤트 매칭으로 제한됩니다. 이 기능은 현재 다음 네트워크에서 사용할 수 있습니다.

| 파트너 | 연동 유형 | 지원되는 이벤트 |
| --- | --- | --- |
| Google (googleads\_int) | OCI | 인앱 이벤트 |
| Meta (facebook\_int, Metaweb\_int) | SRN + CAPI | 인앱 이벤트 |
| 오픈아이(openai\_int) | CAPI | 설치, 재참여, 인앱 이벤트 |
| 틱톡(tiktokglobal\_int, tiktokweb\_int) | SRN + CAPI | 설치, 재참여, 인앱 이벤트 |
| 스냅챗 (snapchat\_int, snapweb\_int) | SRN + CAPI | 설치, 재참여, 인앱 이벤트 |
| Pinterest (pinterest\_int) | CAPI | 설치, 재참여, 인앱 이벤트 |
| 레딧(reddit\_int) | CAPI | 설치, 재참여, 인앱 이벤트 |
| 로쿠(rokuads\_int) | SRN + CAPI | 인앱 이벤트 |

<div id="the-end-to-end-flow" />

## 전체 흐름

식별자가 검색된 순간부터 파트너에게 도달하는 순간까지의 과정은 다음과 같습니다.

1. 식별자(이메일 주소, 전화번호 또는 기타 지원되는 유형)는 앱 또는 백엔드 에서 검색됩니다.
2. 식별자는 SHA-256을 사용하여 정규화 및 해시됩니다. 이는 앱스플라이어 SDK 에서 자동으로 수행되거나 S2S API 통해 전송하기 전에 서버에서 수행됩니다.
3. 해시 처리된 식별자는 이벤트 (인스톨, 재설치, 리인게이지먼트 또는 인앱 이벤트 )와 함께 앱스플라이어 로 전송됩니다.
4. 파트너에 대해 고급 매칭 데이터 공유가 활성화된 경우 앱스플라이어 이벤트 페이로드와 함께 해시 값을 전달합니다.
5. 파트너는 해시값을 사용하여 이벤트 알려진 사용자와 일치시킴으로써 속성 파악 정확도와 일치 품질을 향상시킵니다.

> 📘 **참고**
>
> 해시 처리된 식별자는 고급 매칭 데이터 공유가 활성화된 파트너에게만 전달됩니다. 켜기/끄기 기능이 꺼져 있는 경우, 이벤트 에 식별자가 있더라도 해시된 데이터는 해당 파트너와 공유되지 않습니다.

<div id="how-hashed-user-identifiers-reach-appsflyer" />

## 해시 처리된 사용자 식별자가 앱스플라이어 에 도달하는 경로

해시된 식별자는 SDK 또는 서버 간(S2S) API 두 가지 방법을 통해 앱스플라이어 에 전달됩니다. 두 경우 모두 올바르게 해시된 값만 허용됩니다. 아래 탭에서 각 방법을 설명합니다.

<Tabs>
<Tab title="SDK">

SDK V7.0.1에서는 앱스플라이어 안드로이드 및 iOS SDK에 원시 식별자를 전달하는 방법을 도입했습니다. SDK 는 입력값을 앱스플라이어 로 보내기 전에 정규화 및 해싱 작업을 수행합니다.

SDK 다음 단계를 순서대로 수행합니다.

1. 각 파트너의 요구 사항에 따라 입력값을 정규화합니다.
2. 정규화된 가치 SHA-256을 사용하여 해싱합니다.
3. 앱스플라이어 에는 해시된 가치 전송합니다. 입력된 원본 데이터는 장치를 벗어나지 않습니다.

SDK 에서 유효하지 않은 값은 오류와 함께 거부되며 앱스플라이어 로 전송되지 않습니다.

> 📘 **참고**
>
> SDK 7.0.1부터 안드로이드 및 iOS 지원 제공됩니다.

구현 세부 정보는 안드로이드 SDK 연동 가이드 및 iOS SDK 연동 가이드를 참조하세요.

</Tab>

<Tab title="S2S APIs">

S2S 인앱 이벤트 API 통해 이벤트를 전송할 때, 식별자는 제출 전에 서버 측에서 정규화 및 해시 처리되어야 합니다. API 다음 필드를 허용합니다.

| 필드 | 설명 |
| --- | --- |
| `email_hashed` | 해시 처리된 이메일 주소 |
| `phone_number_hashed` | 전화번호를 해시 처리한 후 숫자 부분만 표시합니다. |
| `phone_number_e164_hashed` | E.164 형식으로 해시 처리된 전화번호 |
| `first_name_hashed` | 해시 처리된 이름 |
| `last_name_hashed` | 해시 처리된 성 |
| `fb_login_id` | Facebook 로그인 ID (해시 처리되지 않고 그대로 전달됨) |

> 🚧 **중요!**
>
> 이 표 모든 필드(단, 제외)`fb_login_id` )는 SHA-256 형식에 대해 유효성이 검증되었습니다. 일치하지 않는 값은 아무런 경고 없이 삭제되며 어떤 파트너에게도 전달되지 않습니다. 이벤트 의 다른 필드는 정상적으로 처리됩니다.

**전화번호 입력란이 두 개 있는 이유는 무엇인가요?** 네트워크는 앱스플라이어 전달하는 해시 값을 자체적으로 저장해둔 사용자 전화번호의 해시 값과 비교하여 이벤트를 일치시킵니다. 같은 숫자라도 다른 형식으로 정규화하면 다른 해시값이 생성되므로, 일치하는 결과를 얻으려면 양쪽 모두 동일한 형식으로 해싱해야 합니다. 네트워크마다 전화번호를 표준화하는 방식이 다르고 앱스플라이어 이미 해시된 값을 수신하므로, 지원되는 모든 파트너에게 전달하려면 두 가지 버전 모두를 보내야 합니다.

* `phone_number_hashed`Meta 와 스냅챗 입니다. 해싱 전 정규화 형식: `16501234567`
* `phone_number_e164_hashed`구글 과 틱톡의 경우. 해싱 전 정규화 형식: `+16501234567`

</Tab>
</Tabs>

<div id="normalize-and-hash-identifiers" />

## 식별자를 정규화하고 해시합니다.

아래 설명된 대로 원시 가치 정확하게 정규화한 다음 SHA-256을 사용하여 해싱하고 소문자 16진수 다이제스트를 전송합니다.

<div id="email-email_hashed" />

<Accordion title="이메일(email_hashed)">

1. 모든 공백을 제거하세요.
2. 소문자로 변환하세요.
3. SHA-256으로 해시합니다.

**예:**

`User@Example.COM` →`user@example.com` → SHA-256 해시

</Accordion>

<div id="phone-number-digits-only-phone_number_hashed" />

<Accordion title="전화번호 (숫자만 포함, 해시 처리됨)">

Meta 와 스냅챗 에서 사용하다 .

1. 국가 코드를 앞에 추가하세요.
2. 모든 기호, 문자 및 선행 0을 제거하십시오.
3. SHA-256으로 해시합니다.

**예:**

`+1 (650) 123-4567` →`16501234567` → SHA-256 해시

</Accordion>

<div id="phone-number-e164-phone_number_e164_hashed" />

<Accordion title="전화번호, E.164 (phone_number_e164_hashed)">

구글 과 틱톡에서 사용하다 .

1. 국가 코드를 앞에 추가하세요.
2. 모든 기호, 문자 및 선행 0을 제거하십시오.
3. 접두사 a를 붙이세요`+` 징후.
4. SHA-256으로 해시합니다.

**예:**

`+1 (650) 123-4567` →`+16501234567` → SHA-256 해시

</Accordion>

<div id="first-name-first_name_hashed-and-last-name-last_name_hashed" />

<Accordion title="이름(first_name_hashed)과 성(last_name_hashed)">

1. 모든 공백을 제거하세요.
2. 소문자로 변환하세요.
3. SHA-256으로 해시합니다.

</Accordion>

<div id="facebook-login-id-fb_login_id" />

<Accordion title="Facebook 로그인 ID (fb_login_id)">

Facebook 로그인 SDK 에서 제공하는 그대로의 Facebook 로그인 ID 전송하세요. 이 필드는 해시되지 않았습니다.

</Accordion>

<div id="turn-on-advanced-matching-data-sharing" />

## 고급 매칭 데이터 공유를 켜세요

고급 매칭 데이터 공유는 파트너 및 앱별로 제어되며, 각 네트워크 에 대해 명시적으로 활성화해야 합니다.

고급 매칭 데이터 공유를 활성화하려면:

1. 앱스플라이어의 사이드 메뉴에서 **협업** > 활성화된 연동을 선택합니다.
2. 파트너를 검색하여 선택합니다.
3. **고급 매칭 데이터 공유를** 활성화하세요.
4. **연동 저장**을 클릭하세요.

고급 매칭 데이터 공유 기능이 활성화되면 하나 이상의 지원되는 식별자 필드를 포함하는 모든 이벤트 에서 해당 필드가 파트너에게 전달됩니다.

> 📘 **참고**
>
> 고급 매칭 데이터 공유 기능을 끄면 해당 파트너와의 해시 데이터 공유가 즉시 중지됩니다. 포스트백 및 이벤트 데이터를 포함한 다른 연동 설정은 영향을 받지 않습니다.

<div id="privacy-and-data-handling" />

## 개인정보 및 데이터 처리

파트너에 대해 고급 매칭 데이터 공유가 활성화되면 앱스플라이어 해시 처리된 사용자 식별자를 이벤트 데이터와 함께 해당 네트워크 로 전달하기 시작합니다. 전원을 켜기 전에 다음 사항을 확인하십시오.

* 해당 개인정보 보호법(예: 일반 데이터 보호 규정(GDPR) 또는 캘리포니아 소비자 개인정보 보호법(CCPA))에 따라 파트너와 이 데이터를 공유할 수 있는 법적 근거가 있습니다.
* 개인정보 처리방침이 업데이트되었으며, 필요한 경우 사용자 동의를 얻었습니다.
* 귀사의 데이터 공유 방식은 파트너의 약관을 준수합니다.

> 🚧 **중요!**
>
> 앱스플라이어 개인 식별 정보(PII)를 평문으로 처리하거나 앱 내 하지 않습니다. 모든 식별자 필드는 데이터 수집 시 유효성 검사를 거칩니다. SHA-256 형식을 준수하지 않는 값은 삭제되며 어떤 파트너에게도 전달되지 않습니다.

## FAQ

<div id="is-advancedmatching-data-sharing-the-same-as-the-audiences-hashed-email-and-phone-feature" />

<Accordion title="고급 매칭 데이터 공유는 오디언스의 해시 처리된 이메일 및 전화번호 기능과 동일한 것인가요?">

아니요. 이것들은 별개의 메커니즘입니다. 잠재고객은 광고 타겟팅 위한 사용자 목록을 작성합니다. 고급 매칭 데이터 공유는 해시된 식별자를 개별 이벤트와 함께 전달하여 파트너 수준 에서 매칭률을 향상시킵니다. 앱스플라이어 새로운 데이터 검색 방식을 고급 매칭 데이터 공유와 잠재고객 기능 모두에 적용하여 두 가지 방식을 통합할 계획입니다.

</Accordion>

<div id="what-happens-if-i-send-an-invalid-hash-value" />

<Accordion title="유효하지 않은 해시 가치 보내면 어떻게 되나요?">

해당 필드는 데이터 수집 시 삭제되며 어떤 파트너에게도 전달되지 않습니다. 이벤트 의 다른 필드는 정상적으로 처리됩니다.

</Accordion>

<div id="do-i-need-to-send-all-supported-fields" />

<Accordion title="지원되는 모든 필드를 보내야 하나요?">

아니요. 구성된 파트너와 관련된 식별자만 포함하면 됩니다. 누락된 필드는 전달되지 않습니다.

</Accordion>

<div id="will-advancedmatching-data-sharing-improve-install-attribution" />

<Accordion title="고급 매칭 데이터 공유 기능이 인스톨 기여도 분석을 개선할 수 있을까요?">

스냅챗 과 틱톡에서는 가능합니다. 이 파트너들은 해시 처리된 이메일 과 전화번호를 기반으로 인스톨 및 리인게이지먼트 클레임을 지원 . 구글 과 Meta 의 경우, 현재 이 기능은 인앱 이벤트 에 대한 매칭률만 향상시킵니다.

</Accordion>

<div id="does-appsflyer-ever-receive-plaintext-user-identifiers" />

<Accordion title="앱스플라이어 평문 사용자 식별자를 수신하는 경우가 있습니까?">

아니요. SDK 를 사용할 경우, 앱스플라이어 로 데이터가 전송되기 전에 기기 내에서 해싱이 수행됩니다. S2S API 사용할 때, 해싱은 제출 전에 서버에서 수행됩니다. 앱스플라이어 해시된 값만 허용합니다.

</Accordion>

<div data-zendesk-anchors="about-advancedmatching-data-sharing=%EA%B3%A0%EA%B8%89-%EB%A7%A4%EC%B9%AD-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01KVFJHWK1TYAPPMZDYFAP0RX0=%EA%B3%A0%EA%B8%89-%EB%A7%A4%EC%B9%AD-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01KVFJHWK1T1PN0ENT84PM2E69=%EC%A4%91%EC%9A%94 supported-partners=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-%ED%8C%8C%ED%8A%B8%EB%84%88 h_01KVFJHWK1VTJZH53FKNE8NZ59=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-%ED%8C%8C%ED%8A%B8%EB%84%88 the-endtoend-flow=%EC%A0%84%EC%B2%B4-%ED%9D%90%EB%A6%84 h_01KVFJHWK1JQ7J838YNDTYDD4A=%EC%A0%84%EC%B2%B4-%ED%9D%90%EB%A6%84 h_01KVFJHWK1JNHRHP1NJ5YCXV70=%EC%B0%B8%EA%B3%A0 how-hashed-user-identifiers-reach-appsflyer=%ED%95%B4%EC%8B%9C-%EC%B2%98%EB%A6%AC%EB%90%9C-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%8B%9D%EB%B3%84%EC%9E%90%EA%B0%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%90-%EB%8F%84%EB%8B%AC%ED%95%98%EB%8A%94-%EA%B2%BD%EB%A1%9C h_01KVFJHWK197KW8YBQ1NBD9XT1=%ED%95%B4%EC%8B%9C-%EC%B2%98%EB%A6%AC%EB%90%9C-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%8B%9D%EB%B3%84%EC%9E%90%EA%B0%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%90-%EB%8F%84%EB%8B%AC%ED%95%98%EB%8A%94-%EA%B2%BD%EB%A1%9C h_01KVFJHWK1JVSGVKPS9C2M01ZP=%EC%B0%B8%EA%B3%A0-1 h_01KVFJHWK15MA0FG7AFB999JQR=%EC%A4%91%EC%9A%94-2 normalize-and-hash-identifiers=%EC%8B%9D%EB%B3%84%EC%9E%90%EB%A5%BC-%EC%A0%95%EA%B7%9C%ED%99%94%ED%95%98%EA%B3%A0-%ED%95%B4%EC%8B%9C%ED%95%A9%EB%8B%88%EB%8B%A4 h_01KVFJHWK16KQ1X1WFTTTFFND3=%EC%8B%9D%EB%B3%84%EC%9E%90%EB%A5%BC-%EC%A0%95%EA%B7%9C%ED%99%94%ED%95%98%EA%B3%A0-%ED%95%B4%EC%8B%9C%ED%95%A9%EB%8B%88%EB%8B%A4 h_01KVFJHWK2KRFS56PAZF23KXE2=email-email_hashed h_01KVFJHWK208WBE3NB5TER7RWM=phone-number-digits-only-phone_number_hashed h_01KVFJHWK2HBN91BS5D52FZJQ9=phone-number-e164-phone_number_e164_hashed h_01KVFJHWK26PAD582XDE14ZDBE=first-name-first_name_hashed-and-last-name-last_name_hashed h_01KVFJHWK2TC4FK1F260CZWGYE=facebook-login-id-fb_login_id turn-on-advancedmatching-data-sharing=%EA%B3%A0%EA%B8%89-%EB%A7%A4%EC%B9%AD-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0%EB%A5%BC-%EC%BC%9C%EC%84%B8%EC%9A%94 h_01KVFJHWK27C5FA358M526EJED=%EA%B3%A0%EA%B8%89-%EB%A7%A4%EC%B9%AD-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0%EB%A5%BC-%EC%BC%9C%EC%84%B8%EC%9A%94 h_01KVFJHWK2CQX93GDZ6G97E4Y0=%EC%B0%B8%EA%B3%A0-2 privacy-and-data-handling=%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B0%8F-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B2%98%EB%A6%AC h_01KVFJHWK2BN2T7BTXANAWAX4B=%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B0%8F-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B2%98%EB%A6%AC h_01KVFJHWK2GX1PGCWFGYADE1S3=%EC%A4%91%EC%9A%94-2 h_01KVFJHWK2XB5VF8V2KPG62QYV=faq h_01KVFJHWK2J7R7P123Z1877Y3H=is-advancedmatching-data-sharing-the-same-as-the-audiences-hashed-email-and-phone-feature h_01KVFJHWK2XS2WK3F3GDDYCZ92=what-happens-if-i-send-an-invalid-hash-value h_01KVFJHWK2XY4FBWMZH38GYD2V=do-i-need-to-send-all-supported-fields h_01KVFJHWK2HJS895AS5ANK94AX=will-advancedmatching-data-sharing-improve-install-attribution h_01KVFJHWK2R7BAMWZRC41PKAX4=does-appsflyer-ever-receive-plaintext-user-identifiers" />
