---
title: 2FA 로그인 구현 및 사용
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
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
  created_at: '2020-06-22T10:25:26Z'
  edited_at: '2026-10-14T10:37:08Z'
  id: 360010178037
  locale: ko
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ko/articles/360010178037
---
> **한눈에 보기:** **요약:** 2단계 인증(2FA)을 사용하여 로그인 프로세스에 보호 계층을 추가하고 보안을 강화합니다. 계정 사용자의 로그인 자격 증명은 Google Authenticator 또는 SMS 인증으로 보강됩니다.

<div id="highlights" />

## 주요 기능

* 2FA는 관리자가 활성화할 수 있는 선택적 기능입니다.
* 인증 방식은 **Google Authenticator** 및 **SMS 인증**이 있습니다.
* 활성화/비활성화는 모든 계정 사용자에게 적용됩니다.
* 활성화된 시점에는 계정 사용자의 로그인이 허용되고 다음 로그인 시에 2FA를 설정하도록 메시지가 표시됩니다.

<div id="-admin-managing-2fa" />

## ![admin.png](https://files.readme.io/d54680123b25ab7929285cebd778e0e74bd0d032df994b04d1bca106381c3dc6-360014518718.png) Admin: 2FA 관리

관리자만이 사용자의 2FA 설정을 활성화, 재설정 또는 비활성화시킬 수 있습니다.

<div id="activate" />

<Accordion title="활성화">

관리자가 **Google Authenticator** 및 **SMS 인증**을 활성화할 경우, 계정 사용자는 둘 중에 인증 방법을 선택할 수 있습니다.

<div id="note" />

> 📘 **참고**
>
> SMS 인증은 SMS 전송 성공률에 영향을 받으며, 이는 이동통신사와 국가별로 차이가 있을 수 있습니다. 따라서 SMS 전송 실패로 발생할 수 있는 로그인 잠금을 피하기 위해 SMS 인증과 Google Authenticator를 모두 활성화하는 것을 권장합니다.

**2FA 활성화 방법:**

1. 상단 메뉴에서 계정 메뉴(이메일 주소 드롭다운 메뉴) > 보안 센터(Security Center)를 클릭합니다.
2. **향상된 로그인 보안** 섹션에서 **로그인 방법 설정**을 클릭하여 **로그인 보안** 페이지에 액세스하세요.
3. **2단계 인증(2FA)** 섹션에서 **Google Authenticator** 및/또는 **SMS 인증** 토글을 활성화하세요.

</Accordion>

<div id="reset" />

<Accordion title="재설정">

2FA를 사용하고 있는 계정의 경우, 사용자의 2FA를 재설정해야 하는 경우가 있을 수 있습니다. 재설정 후 **Google Authenticator**가 디폴트 2FA 로그인 화면으로 설정됩니다.

**사용자의 2FA를 재설정하는 방법:**

1. 메뉴에서 이메일 주소 드롭다운 메뉴를 클릭합니다.
2. **사용자 관리**를 선택합니다.
3. **사용자** 탭에서 사용자 행의 맨 오른쪽에 있는 <Image alt="" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />메뉴 옵션altactions\_icon.png을 클릭합니다.
4. 메뉴에서 **2FA 재설정**을 선택합니다.

**참고:** 관리자는 본인 또는 <Anchor target="_blank" href="/marketers/ko/docs/user-management#관리자">계정 소유자</Anchor> 이외의 다른 관리자의 2FA를 재설정할 수 있습니다. 계정 소유자의 2FA를 재설정하려면 앱스플라이어 지원팀에 문의하십시오.

</Accordion>

<div id="deactivate" />

<Accordion title="비활성화">

2FA가 비활성화되면 계정 사용자는 사용자 이름과 비밀번호를 사용하여 로그인할 수 있습니다.

**2FA 비활성화 방법:**

1. 상단 메뉴에서 계정 메뉴(이메일 주소 드롭다운 메뉴) > 보안 센터(Security Center)를 클릭합니다.
2. **향상된 로그인 보안** 섹션에서 **로그인 방법 설정**을 클릭하여 **로그인 보안** 페이지에 액세스하세요.
3. **2단계 인증(2FA)** 섹션에서 **Google Authenticator** 및/또는 **SMS 인증** 토글을 비활성화하세요.
4. 비활성화를 확인합니다.

</Accordion>

<div id="account-users-using-google-or-microsoft-authenticator" />

## 계정 사용자: Google Authenticator 사용하기

Google Authenticator 화면이 디폴트로 표시되지만, 지난 로그인 시에 사용된 인증 방법이 다음 로그인 시에도 나타납니다.

**Google Authenticator**을 사용하지 않도록 선택하면 설정 및 로그인 화면에 **SMS** 2FA로 넘어가는 링크가 나타납니다.

<div id="firsttime-setup" />

<Accordion title="최초 설정">

2FA를 최초로 사용하기 전에 모든 계정 사용자는 **Google Authenticator** 및 **QR 코드** 앱을 다운로드해야 합니다. 해당 앱은 **Google Play**(안드로이드) 또는 **앱 스토어**(iOS)에서 다운로드할 수 있습니다.

**신규 계정 사용자**

1. 이메일 지시사항에 따라 비밀번호를 설정하세요.
2. **앱스플라이어**에 로그인하면 2FA 설정 페이지로 리디렉트됩니다.
3. 2FA 설정
   * **Google Authenticator** 및 **QR 코드** 앱을 다운로드합니다.
   * QR 코드를 스캔합니다.
   * **Google Authenticator**에서 생성된 인증 코드를 입력합니다.
   * **인증**을 클릭하면 **마이 앱(My apps)** 페이지로 리디렉트됩니다.

**기존 계정 사용자**

1. **앱스플라이어**(사용자 이름 및 비밀번호)에 로그인하시면 2FA 설정 페이지로 리디렉트됩니다.
2. 2FA 설정
   * **Google Authenticator** 및 **QR 코드** 앱을 다운로드합니다.
   * QR 코드를 스캔합니다.
   * **Google Authenticator**에서 생성된 인증 코드를 입력합니다.
   * **인증**을 클릭하면 **마이 앱(My apps)** 페이지로 리디렉트됩니다.

</Accordion>

<div id="ongoing-use" />

<Accordion title="사용을 지속하는 경우">

**계속해서 사용하려면 다음 단계를 차례로 실행하세요**

1. **앱스플라이어**(사용자 이름 및 비밀번호)에 로그인하시면 2FA 로그인 페이지로 리디렉트됩니다.
2. **Google Authenticator**앱을 실행하여 인증 코드를 확인합니다.
3. 2FA 페이지에 코드를 입력합니다.
4. **인증**을 클릭하면 **마이 앱(My apps)** 페이지로 리디렉트됩니다.

</Accordion>

<div id="account-users-using-sms-verification" />

## 계정 사용자: SMS 인증 방법 사용

**SMS 인증**을 사용하지 않도록 선택하면 설정 및 로그인 화면에 **Google Authenticator** 2FA로 넘어가는 링크가 나타납니다.

<div id="firsttime-sms-setup" />

<Accordion title="최초 SMS 인증 설정">

**Google Authenticator**는 디폴트로 설정된 2FA 방법입니다. **SMS 인증** 방법을 사용하려면 **SMS 인증** 링크를 클릭하세요.

**신규 계정 사용자**

1. 이메일 지시사항에 따라 비밀번호를 설정하세요.
2. **앱스플라이어**에 로그인하면 2FA 설정 페이지로 리디렉트됩니다.
3. 2FA 설정 방법:
   * 전화번호를 입력하고(숫자만 가능)**코드 전송**을 클릭하세요.
   * SMS 인증 코드를 입력하고 >**인증**을 클릭하세요.

**기존 계정 사용자**

1. **앱스플라이어**(사용자 이름 및 비밀번호)에 로그인하시면 2FA 설정 페이지로 리디렉트됩니다.
2. 2FA 설정 방법:
   * 전화번호를 입력하고(숫자만 가능)**코드 전송**을 클릭하세요.
   * SMS 인증 코드를 입력하고 **인증**을 클릭하세요.

</Accordion>

<div id="ongoing-sms-use" />

<Accordion title="SMS 인증을 계속해서 사용하는 경우">

**계속해서 사용하려면 다음 단계를 차례로 실행하세요.**

1. **앱스플라이어**(사용자 이름 및 비밀번호)에 로그인하시면 2FA 로그인 페이지로 리디렉트됩니다.
2. 지난 로그인 시 **SMS 인증** 방법을 사용한 경우, SMS 인증 페이지가 나타납니다. 아닌 경우,**Google Authenticator** 2FA 페이지 맨 하단에 있는 링크를 클릭하세요.
3. 전화번호를 자동으로 불러옵니다. **코드 보내기**를 클릭하세요.
4. SMS으로 전송된 인증 코드를 입력합니다.
5. **인증**을 클릭합니다.

</Accordion>

<div data-zendesk-anchors="highlights=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5 h_01HEHRKE8PY64KWVSSFR6T4F1Z=%EC%A3%BC%EC%9A%94-%EA%B8%B0%EB%8A%A5 admin-managing-2fa=-admin-2fa-%EA%B4%80%EB%A6%AC h_01HEHRKE8PZA3H9SXPRD1FZ50S=-admin-2fa-%EA%B4%80%EB%A6%AC h_01HEHRKE8PV0ZADPXHNBBDMKAF=activate 01JCDTA1W486FEFRPT2VYJ2PVX=%EC%B0%B8%EA%B3%A0 h_01HEHRKE8P9N2W871ZEB1D3MYN=reset h_01HEHRKE8PEDWCNKMG1N4CFDMN=deactivate account-users-using-google-authenticator=%EA%B3%84%EC%A0%95-%EC%82%AC%EC%9A%A9%EC%9E%90-google-authenticator-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0 h_01HEHRKE8P1A2BARBDVMJPH1WY=%EA%B3%84%EC%A0%95-%EC%82%AC%EC%9A%A9%EC%9E%90-google-authenticator-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0 h_01HEHRKE8QQTX3Y9ZY1HZ6GBAG=firsttime-setup h_01HEHRKE8QHWHCMNB5M7S5YVYJ=ongoing-use account-users-using-sms-verification=%EA%B3%84%EC%A0%95-%EC%82%AC%EC%9A%A9%EC%9E%90-sms-%EC%9D%B8%EC%A6%9D-%EB%B0%A9%EB%B2%95-%EC%82%AC%EC%9A%A9 h_01HEHRKE8QZ245ZYBZ4FF814KN=%EA%B3%84%EC%A0%95-%EC%82%AC%EC%9A%A9%EC%9E%90-sms-%EC%9D%B8%EC%A6%9D-%EB%B0%A9%EB%B2%95-%EC%82%AC%EC%9A%A9 h_01HEHRKE8Q30QHGZ5QYMV4MR27=firsttime-sms-setup h_01HEHRKE8Q0229YE5QP5EJFSD8=ongoing-sms-use" />
