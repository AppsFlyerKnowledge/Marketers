---
title: IdP(ID 제공업체)를 통해 SSO 인증 설정
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - login security
    - SSO
    - SSO verification
    - SSO certificate
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-11-02T10:50:55Z'
  edited_at: '2026-10-14T10:38:32Z'
  id: 360015017198
  locale: ko
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ko/articles/360015017198
---
> **한눈에 보기:** 앱스플라이어를 ID 제공업체(IdP)와 통합하면 앱스플라이어 계정 유저가 SSO(Single Sign-On)를 사용하여 앱스플라이어에 로그인할 수 있습니다. SSO 인증을 AppsFlyer와 IdP 플랫폼에서 설정하는 방법을 배우십시오.

<div id="note" />

<div id="considerations" />

## 고려 사항

* **전제 조건:** 유저는 동일한 이메일을 사용하여 두 시스템(앱스플라이어 및 IdP)에 모두 설정되어야 합니다.
* SSO 구성 설정은 관리자만 관리하고 제거할 수 있습니다.
* **SSO 강제 적용**이 설정되면 모든 사용자는 SSO를 통해 로그인해야 하며, 개별 사용자는 제외할 수 없습니다.
* SSO를 사용할 때 2FA는 지원되지 않습니다.
* 사용자 이름과 비밀번호로 SSO를 동시에 활성화하는 것은 권장되지 않습니다.

<div id="access-the-sso-configuration-page" />

## SSO 구성 페이지에 액세스하십시오.

1. **상단 막대에서 계정 메뉴(관리자 이메일 주소 드롭다운)** > 보안 센터를 엽니다.
2. **향상된 로그인 보안** 아래에서 **로그인 방법 구성**을 선택합니다.
3. **로그인 보안** 페이지에서 **SSO 구성**를 클릭하십시오.

<div id="set-up-sso" />

## SSO를 설정하십시오.

SSO 구성은 아래 단계에 자세히 설명된 대로 IdP 플랫폼과 AppsFlyer 모두에서 수행됩니다. 구성 상태는 SSO가 설정된 경우 **활성**이거나, 구성되지 않았거나 구성 설정이 제거된 경우 **구성되지 않음**일 수 있습니다.

<div id="note-1" />

> 📘 **참고**
>
> * 이 가이드에는 아래 IdP에 대한 자세한 절차가 포함되어 있습니다. 모든 다른 IdP에 대한 일반 설정 개요가 설명되어 있습니다.
>   * JumpCloud
>   * Okta
>   * OneLogin
>   * Ping Identity

<div id="step-1-set-up-the-idp-platform" />

<Accordion title="1단계: IdP 플랫폼을 설정하십시오.">

다음 IdP에서 SSO 인증을 구성하는 자세한 절차를 참조하십시오:

* <Anchor target="_blank" href="/marketers/ko/docs/configure-appsflyer-sso-in-jumpcloud">JumpCloud</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/configure-appsflyer-sso-in-okta">Okta</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/configure-appsflyer-sso-in-onelogin">OneLogin</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/configure-appsflyer-sso-in-ping-identity">Ping Identity</Anchor>

<div id="setup-overview-for-other-idp-platforms" />

#### 다른 IdP 플랫폼에 대한 설정 개요

다른 IdP 플랫폼을 구성하는 과정은 아래에 설명되어 있습니다:

* SAML 2.0 프로토콜을 사용하여 IdP 플랫폼에서 AppsFlyer 앱을 생성하고, IdP 플랫폼 내에서 [AppsFlyer 인증서](#the-authentication-certificate)를 통합하십시오.
* 새로 생성된 AppsFlyer 앱에 사용자를 할당하십시오.
* AppsFlyer에서 사용할 IdP 인증서 또는 메타데이터를 가져오십시오( [2단계에서 언급된 대로: AppsFlyer 설정 --> 5. IdP 메타데이터 제공](#step-5-provide-idp-metadata)

<div id="note-2" />

> 📘 **참고**
>
> * **중요!** 유저를 IdP에 할당할 때 앱스플라이어와 동일한 유저 이메일을 사용하여 두 플랫폼의 각 유저가 동일한 이메일을 갖도록 하세요.
> * <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">앱스플라이어 메타데이터</Anchor>에는 다음이 포함됩니다.
>   * 암호화 및 서명 인증서
>   * 엔터티 ID
>   * 콜백 URL

<div id="step-2-set-up-appsflyer" />

<Accordion title="2단계: 앱스플라이어 설정하기">

다음 흐름은 IdP 플랫폼에서 SSO 인증을 설정한 후 앱스플라이어에서 SSO 인증을 설정하는 단계를 안내합니다.

SSO 구성 설정 페이지에 [접근하는 방법](#sso-구성-페이지에-액세스하십시오)을 확인하세요.

<div id="step-1-select-authentication-starting-point" />

<Accordion title="1. 인증 시작 지점">

1. 사용자가 앱스플라이어에 들어오는 경로를 선택하세요. 이것은 인증 프로세스도 정의합니다.
   * [ID 제공업체(IdP)](#id-제공업체idp)
   * [서비스 제공업체(앱스플라이어)](#서비스-제공업체앱스플라이어)
2. **다음**을 클릭합니다.

<div id="identity-provider-idp" />

#### ID 제공업체(IdP)

IdP 인증 플러그인 또는 웹페이지를 통해 로그인하는 사용자는 인증 후 앱스플라이어 웹페이지로 이동됩니다.

<div id="note-3" />

> 📘 **참고**
>
> 이 옵션을 선택한 사용자는 IdP와 서비스 제공업체(앱스플라이어) 둘 다를 통해 로그인할 수 있습니다.

<div id="service-provider-appsflyer" />

#### 서비스 제공업체(앱스플라이어)

유저는 <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-callback">앱스플라이어 SSO 로그인 페이지</Anchor>에서 **SSO로 로그인**을 클릭하고 이메일 주소를 입력하여 앱스플라이어에 들어갈 수도 있습니다. 그들은 인증을 위해 IdP로 안내되고 앱스플라이어 홈페이지로 리디렉션됩니다.

[<Image alt="AppsFlyer_login_page.png" src="https://files.readme.io/fb80e44cf0cad29349ec85f75f65de73041b1787b278ae9d96449783580faeaa-17233244722577.png" width="257px" />](https://files.readme.io/fb80e44cf0cad29349ec85f75f65de73041b1787b278ae9d96449783580faeaa-17233244722577.png)

<div id="note-4" />

> 📘 **참고**
>
> 이 옵션을 선택하면 사용자는 서비스 제공자(앱스플라이어)를 통해서만 로그인할 수 있으며 IdP에서 직접 로그인할 수 없습니다.

<div id="step-2-set-login-method" />

<Accordion title="2. 로그인 방법 설정">

1. 사용자가 앱스플라이어에 로그인할 수 있는 방법을 선택하세요:
   * **SSO 강제 적용** [추천]: 이 방법을 사용하면 보다 안전한 로그인이 가능합니다.
   * SSO 방식 또는 사용자 이름 및 비밀번호 입력 방식 사용자는 SSO를 통해 로그인하거나 사용자 이름과 비밀번호를 사용하여 로그인하도록 선택할 수 있습니다.
2. **다음**을 클릭합니다.

</Accordion>

<div id="step-3-select-certificate-type" />

<Accordion title="3. 인증서 유형 선택">

앱스플라이어는 데이터를 암호화하고 SSO 요청에 서명하기 위해 두 가지 유형의 공개 암호화 키 인증서를 제공합니다:

* **앱스플라이어 서명 인증서:** 앱스플라이어 메타데이터 URL에서 생성된 앱스플라이어 인증서입니다<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">.</Anchor>
* **CA 서명 인증서:** Amazon이 서명한 앱스플라이어 인증서.

**이 단계를 수행하려면:**

* 인증서 유형을 선택하고 **다음**을 클릭하세요.

<div id="6-activate-sso" />

<div id="5-add-exception-users" />

<div id="activation-results" />

<div id="note-7" />

<div id="delete-an-exception-user" />

<div id="add-login-methods-for-multiple-users" />

<div id="note-6" />

<div id="note-5" />

> 📘 **참고**
>
> 인증서는 양측이 상호 인증서 구현 프로세스를 완료한 후에만 활성화됩니다: 앱스플라이어는 IdP SAML 구성을 통합하고 IdP는 최신 앱스플라이어 SSO 메타데이터를 통합합니다. 다음 단계에서 수행됩니다.

</Accordion>

<div id="step-4-obtain-service-provider-appsflyer-metadata" />

<Accordion title="4. 서비스 제공업체(앱스플라이어) 메타데이터 가져오기">

1. 최신 앱스플라이어 SSO 메타데이터를 복사하여 IdP SAML 구성에 구현하세요.
   * **앱스플라이어 서명 인증서를 선택한 경우:** 아래의 필드 중 하나를 복사하세요.
     * **Metadata URL:** 전체 메타데이터 URL을 지원하는 IdP의 경우 URL을 복사하여 IdP에 구현하세요.
     * 메타데이터 구성 요소 전체 메타데이터 URL을 지원하지 않는 IdP의 경우 각 구성 요소를 복사하여 IdP의 해당 섹션에 구현하세요: **엔터티 ID**, **암호화 키** (다운로드 가능), 및 **위치 URL**.
     * XML 파일 AppsFlyer SSO 메타데이터를 XML 파일로 다운로드할 수 있는 옵션이 있습니다.
   * **CA 서명 인증서를 선택한 경우:** **메타데이터 구성 요소**를 복사합니다.
2. **다음**을 클릭합니다.

</Accordion>

<div id="step-5-provide-idp-metadata" />

<Accordion title="5. IdP 메타데이터 제공">

아래 옵션을 사용하여 IdP SSO 메타데이터를 제공한 후 메타데이터 형식을 검증하십시오. **참고**: IdP 인증서 데이터는 메타 문자가 없는 단일 행 형식이어야 합니다.

1. IdP 메타데이터를 제공하기 위한 선호하는 방법을 선택하십시오:
   * **URL:** IdP 메타데이터 URL 입력
   * XML 파일 IdP 메타데이터 XML 파일을 업로드하십시오.
2. **유효성 검증**을 클릭하세요. 페이지 상단에 검증 상태를 나타내는 확인 메시지가 나타납니다.
3. **활성화**를 클릭하십시오. 페이지 상단에 SSO 인증 활성화 상태를 나타내는 확인 메시지가 나타납니다.

</Accordion>

</Accordion>

<div id="step-3-test-the-sso-configuration" />

<Accordion title="3단계: SSO 구성을 테스트하십시오.">

IdP와 앱스플라이어의 두 플랫폼에서 모두 SSO 구성을 완료한 후 유저가 [URL 콜백 방법](#single-signon-url-configuration) (IdP 또는 서비스 제공업체(앱스플라이어) 중 **하나**를 사용하여 앱스플라이어에 로그인할 수 있는지 확인하세요(둘 다는 아님).

<div id="test-authentication-via-your-idp" />

#### IdP를 통한 인증 테스트

IdP를 통해 로그인하도록 인증을 구성한 경우, 유저가 IdP 플러그인이나 웹페이지에서 앱스플라이어에 들어갈 수 있는지 확인하세요.

1. 앱스플라이어와 IdP에 로그인되어 있는 경우 둘 모두에서 로그아웃합니다.
2. 시크릿 모드로 웹페이지를 엽니다.
3. IdP 웹페이지로 이동합니다. IdP에 로그인되어 있지 않으므로 인증 과정을 거치게 됩니다. 해당 유저로 로그인하세요.
4. 앱스플라이어를 검색하고 선택합니다. 앱스플라이어 홈페이지로 이동됩니다. 이는 프로세스가 성공했음을 나타냅니다.

<div id="test-authentication-via-your-service-provider-appsflyer" />

#### 서비스 제공업체(앱스플라이어)를 통한 인증 테스트

서비스 제공업체(앱스플라이어)를 통해 로그인하도록 인증 흐름을 구성한 경우, 유저가 이메일을 사용하여 앱스플라이어에 들어갈 수 있는지 확인하세요.

<Image alt="log_in_to_af_by_email2.png" src="https://files.readme.io/ae22ff9ba0216f54bee4cea82ed7d35cea656a68e30c0a0e4f549b1855ec7cfd-17233244746257.png" width="245px" />

1. 앱스플라이어와 IdP에 로그인되어 있는 경우 둘 모두에서 로그아웃합니다.
2. 시크릿 모드로 웹페이지를 엽니다.
3. <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">앱스플라이어 로그인 페이지</Anchor>로 이동하여 **SSO로 로그인**을 클릭합니다.
4. 해당 이메일을 입력하고 **계속**을 클릭합니다. 이제 인증을 위해 IdP로 이동됩니다.
5. IdP 인증 후에는 로그인한 유저로 앱스플라이어로 다시 리디렉션됩니다. 이는 프로세스가 성공했음을 나타냅니다.

</Accordion>

</Accordion>

</Accordion>

<div id="edit-exception-users-1" />

<div id="note-8" />

<div id="important" />

<div id="manage-sso-configuration" />

## SSO 구성을 관리하십시오.

SSO 구성을 설정한 후에는 구성을 편집하거나 제거할 수 있습니다.

SSO 구성 페이지에 [접근하는 방법](#sso-구성-페이지에-액세스하십시오)을 확인하십시오.

<div id="zd-edit-sso" />

<div id="edit-exception-users" />

<div id="edit-sso" />

<Accordion title="SSO 편집">

이 페이지에서 다음 옵션 중 하나를 편집할 수 있습니다:

* 인증 시작 지점
* 로그인 방법
* 인증서 유형
* 서비스 제공자 (AppsFlyer 메타데이터) - 세부정보를 얻을 수 있습니다.
* 신원 제공자 메타데이터

> 🚧 **중요!**
>
> 인증서 유형이나 인증 시작 지점을 변경할 때 AppsFlyer 메타데이터가 변경됩니다. 가장 최근의 서비스 제공자 (AppsFlyer) SSO 메타데이터를 복사하고 변경 사항을 저장한 직후에 IdP SAML 구성에 즉시 구현하는 것이 중요합니다.

**SSO 구성 편집하기:**

1. 오른쪽 **편집** <Image alt="edit-icon.jpg" src="https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg" width="24px" /> 아이콘을 클릭하여 **SAML 단일 로그인(SSO)** 섹션에서 선택합니다.
2. 섹션 중 하나로 이동하여 선호하는 옵션을 선택합니다.
3. **변경 사항 저장**을 클릭합니다. 변경 상태를 나타내는 확인 메시지가 나타납니다.

</Accordion>

<div id="remove-sso-configuration" />

<Accordion title="SSO 구성 삭제">

**SSO 구성 삭제하기:**

1. 오른쪽 **삭제** 쓰레기통 아이콘을 클릭하여 **SAML 단일 로그인(SSO)** 섹션에서 선택합니다.
2. 섹션 중 하나로 이동하여 선호하는 옵션을 선택합니다.
3. **변경 사항 저장**을 클릭합니다. 변경 상태를 나타내는 확인 메시지가 나타납니다.

> 📘 **참고**
>
> SSO 구성을 제거할 때, AppsFlyer에 저장된 IdP SSO 메타데이터가 삭제됩니다.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 이름 | 설명 |
| --- | --- |
| 이메일 주소의 기호 | SSO는 이메일 주소에 + 기호가 포함된 이메일 주소를 지원하지 않습니다.<br /><br />예: my+customer@demo.com<br /><br />이것이 있으면 로그인 실패가 발생합니다. |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> <Anchor target="_blank" href="/marketers/ko/docs/sso-authentication-overview-and-faq">SSO 인증에 대해 배우고 FAQ에 대한 답변을 찾으세요</Anchor>

<div data-zendesk-anchors="considerations=%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD h_01J7KK52TX8WGA3EK110R9M0GY=%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD access-the-sso-configuration-page=sso-%EA%B5%AC%EC%84%B1-%ED%8E%98%EC%9D%B4%EC%A7%80%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01J7X4Y5Y50EFAPVP6JY8WAMKN=sso-%EA%B5%AC%EC%84%B1-%ED%8E%98%EC%9D%B4%EC%A7%80%EC%97%90-%EC%95%A1%EC%84%B8%EC%8A%A4%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 setting-up-sso-authentication=sso%EB%A5%BC-%EC%84%A4%EC%A0%95%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01HCHG901V25TSRGRT9244384D=sso%EB%A5%BC-%EC%84%A4%EC%A0%95%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01J530X1930CMCF7XJM1XKPC74=%EC%B0%B8%EA%B3%A0 01J530ZP34SQKHM5324DNFA25Y=step-1-set-up-the-idp-platform configuration-overview-for-other-idp-platforms=%EB%8B%A4%EB%A5%B8-idp-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90-%EB%8C%80%ED%95%9C-%EC%84%A4%EC%A0%95-%EA%B0%9C%EC%9A%94 h_01HCHG901VPG0ZJ20XJBFPY7CD=%EB%8B%A4%EB%A5%B8-idp-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90-%EB%8C%80%ED%95%9C-%EC%84%A4%EC%A0%95-%EA%B0%9C%EC%9A%94 h_01HCHG901VH2XZS9Q0KM9D26WX=%EC%B0%B8%EA%B3%A0-1 h_01J5303SNTEVQNA4KZEMS2VG04=step-2-set-up-appsflyer h_01J4PGJ2T73313B1X6ECQ17S7Q=step-1-select-authentication-starting-point identity-provider-idp=id-%EC%A0%9C%EA%B3%B5%EC%97%85%EC%B2%B4idp h_01J4PHJ8FECGSAGQJGWREX3PKK=id-%EC%A0%9C%EA%B3%B5%EC%97%85%EC%B2%B4idp h_01J4PHSVS55G2M00S00KG06BB7=%EC%B0%B8%EA%B3%A0-2 service-provider-appsflyer=%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%A0%9C%EA%B3%B5%EC%97%85%EC%B2%B4%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4 h_01J4PHTR1E9JV3SM0A7N4X3WJY=%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%A0%9C%EA%B3%B5%EC%97%85%EC%B2%B4%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4 h_01J4PJEQTBJ9P2SZBKGPF2696S=%EC%B0%B8%EA%B3%A0-3 h_01J4PGJ2T7BQKNS08R22WFPM50=step-2-set-login-method h_01J4PGJ2T76F7YTK42VBW8J1P6=step-3-select-certificate-type h_01J8CEE2BZN0THJ7DNSGRCGJNQ=%EC%B0%B8%EA%B3%A0-4 h_01J4PGJ2T76PKE0V7NS7YXC4T5=step-4-obtain-service-provider-appsflyer-metadata h_01J4PGJ2T7SM8EGYZCW6D7AQN8=step-5-provide-idp-metadata h_01J5303SNTYMDMP2DW4GQCGEHK=step-3-test-the-sso-configuration testing-authentication-via-the-idp=idp%EB%A5%BC-%ED%86%B5%ED%95%9C-%EC%9D%B8%EC%A6%9D-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HCHG901WXSQ2VPCH2NKE63SE=idp%EB%A5%BC-%ED%86%B5%ED%95%9C-%EC%9D%B8%EC%A6%9D-%ED%85%8C%EC%8A%A4%ED%8A%B8 testing-authentication-via-appsflyer=%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%A0%9C%EA%B3%B5%EC%97%85%EC%B2%B4%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A5%BC-%ED%86%B5%ED%95%9C-%EC%9D%B8%EC%A6%9D-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HCHG901W6DJ3GN6E7WFR6RNK=%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%A0%9C%EA%B3%B5%EC%97%85%EC%B2%B4%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A5%BC-%ED%86%B5%ED%95%9C-%EC%9D%B8%EC%A6%9D-%ED%85%8C%EC%8A%A4%ED%8A%B8 manage-sso-configuration=sso-%EA%B5%AC%EC%84%B1%EC%9D%84-%EA%B4%80%EB%A6%AC%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01J7WKPGTNPF10N4XMJG9ZDN87=sso-%EA%B5%AC%EC%84%B1%EC%9D%84-%EA%B4%80%EB%A6%AC%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01J7X4P6B18HXJB99JYTVSC75N=edit-sso h_01J7WT7362KNX2K9KGW48R2N1P=%EC%A4%91%EC%9A%94 h_01J7X4P6B1THTVR1M966JS4P99=remove-sso-configuration h_01J7X4D9F2BDH1SPBJPNV929X0=%EC%B0%B8%EA%B3%A0-5 h_01K44S4WP3N8HG872PQX1CCES8=traits-and-limitations h_01HDPF69BTMRYR6E6VNMFR4JY4=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
