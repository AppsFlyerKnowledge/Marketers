---
title: 자체 도메인으로 원링크 브랜딩하기
metadata:
  keywords:
    - Marketers
    - cname
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-08-26T09:00:09Z'
  edited_at: '2026-10-14T10:35:25Z'
  id: 360002329137
  locale: ko
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ko/articles/360002329137
---
> **한눈에 보기:** 원링크 링크를 사용하는 광고주는 자체 도메인으로 링크를 브랜딩할 수 있어, 브랜드 원링크로 캠페인 성과를 높이고 브랜드 정체성을 강화할 수 있습니다.

![Branded_1__3_.jpg](https://files.readme.io/20d0a59aa3e896960c9a0faaacad51a58e314073368452e07a7507e0770ca817-30192959736465.png)

<div id="branded-domains" />

## 브랜드 도메인

* 브랜드 도메인은 브랜드와 도메인으로 어트리뷰션 링크를 브랜딩하는 데 사용됩니다. 위의 그림에 설명된 것을 토대로 예를 들어보겠습니다.
  * 원링크: abcdef.onelink.me
  * 브랜드 abcdef.com
  * 서브 도메인: app
  * 브랜드 도메인을 구현하고 전체 도메인을 사용하면, 어트리뷰션 링크는 click.abcdef.com 형식으로 생성됩니다.
* 브랜드 도메인을 통해 다음과 같은 이유로 캠페인 성과를 향상시킬 수 있습니다:
  * 신뢰 형성: 브랜드를 적극 활용하고, 일관된 아이덴티티를 유지할 수 있으며, 사용자 여정에서의 불필요한 마찰을 제거해 클릭률(CTR)을 향상시킬 수 있습니다.
  * 브랜드를 사용하여 딥링킹을 허용합니다.
  * 구현이 간단하며 원링크와 동일하게 동작합니다.
  * 브랜드 인지도 향상: 일반적인 링크 대신, 귀하의 브랜드가 캠페인에 표시됩니다.
  * 보낸 사람 이메일과 일치하지 않는 링크 때문에 스팸으로 지정되는 일이 없습니다.
  * <Anchor target="_blank" href="/marketers/ko/docs/account-management-plans-payments-and-billing">브랜드 도메인은 앱스플라이어 유료 구독 플랜에 포함됩니다.</Anchor>

<div id="principles-of-implementation" />

### 구현 원칙

브랜드 도메인은 DNS (Domain Name System)에 정의된 전체 도메인을 원링크 서브 도메인(앱스플라이어 CNAME 대상)과 연결함으로써 구현됩니다. 이 작업은 DNS의 표준 설정을 통해 이루어지며, 앱스플라이어 내에서 브랜드 도메인을 설정해야 합니다. 또한, 브랜드 도메인을 지원하려면 앱 내에 일부 간단한 수정이 필요합니다.

보통 IT 팀이나 DNS 호스팅 제공자 및 앱 개발자로 구성된 DNS 관리자의 도움이 필요합니다.

하나의 원링크 서브도메인에는 여러 개의 전체 도메인을 연결할 수 있습니다. 즉, 여러 브랜드가 동일한 원링크 서브 도메인을 공유하여 사용할 수 있습니다.

<div id="setting-up-branded-domains" />

### 브랜드 도메인 설정

아래 작업 목록을 완료하여 브랜드 도메인을 설정합니다.

|  | 담당자 | 작업 | 비고 |
| --- | --- | --- | --- |
| 1 | DNS 관리자와 협업하는 마케터 | [앱스플라이어에서 브랜드 링크 설정하기](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) | 일반적으로 IT 팀 또는 DNS 호스팅 제공업체의 구성원인 DNS 관리자는 전체 도메인(일명 호스트)을 정의하고 절차에 설명된 대로 CNAME 레코드를 설정해야 합니다. |
| 2 | 개발자 | [앱에서 브랜드 도메인 설정](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app) | 앱 코드에 약간의 변경 사항을 적용합니다. |
| 3 | 마케터 | [브랜드 도메인 사용 및 테스트](/docs/brand-onelink-with-your-domain#using-and-testing-branded-domains) |  |
| 필요 시 | 마케터 | [브랜드 도메인 편집 및 삭제](/docs/brand-onelink-with-your-domain#editing-and-deleting-branded-domains) |  |

<div id="procedures" />

### 절차

<div id="set-up-a-branded-domain-in-appsflyer" />

<Accordion title="앱스플라이어에서 브랜드 도메인 설정">

브랜드 도메인 설정은 DNS에 등록된 전체 도메인을 앱스플라이어의 원링크 서브 도메인과 연결하는 과정으로, 아래와 같이 구성됩니다.

**앱스플라이어 서버로 연결된 브랜드 도메인**

[![](https://files.readme.io/43bcdbe50ec58af434f404f0216f90ad345b7b1e034cb7d7c80e3c3c4307c1d2-30192946333713.png)](https://files.readme.io/43bcdbe50ec58af434f404f0216f90ad345b7b1e034cb7d7c80e3c3c4307c1d2-30192946333713.png)

**시작하기 전에**

* 전체 도메인 이름을 선택하세요. 예: app.abcdef.com  
  여기서 abcdef.com은 귀하의 브랜드입니다. 서브 도메인, 예를 들어 app을 사용자 정의할 수도 있습니다.
* DNS 관리자가 전체 도메인(호스트)를 생성하도록 요청하세요.
* DNS 관리자에게 전체 도메인(브랜드 도메인)이 지정된 URL(앱스플라이어 호스트)  
  과 연결되도록 CNAME 레코드 설정을 요청하세요.  
  이는 위의 앱스플라이어 서버와 연결되는 브랜드 도메인 그림(상단)에서도 확인할 수 있습니다.

**전체 도메인과 원링크 서브 도메인을 매핑하는 방법**

1. **앱스플라이어에서 참여 > 브랜드 도메인을 클릭합니다.**
2. **+ 새 브랜드 도메인**을 클릭합니다.
3. DNS에 설정된 대로 **브랜드 도메인**에 전체 도메인을 입력하세요. 예시: **click.abcdef.com 주의:** 도메인 뒤에 마침표를 넣지 마세요.
4. 표시되는 목록에서 원링크 서브 도메인을 선택하십시오. 목록이 표시되지 않는 경우,  
   기본 서브 도메인을 제공하는 원링크 템플릿을 생성해야 합니다.  
   .
5. **다음**을 클릭합니다.
6. CNAME 레코드 설정:
   * 귀하의 도메인이 앱스플라이어 CNAME 대상에 올바르게 지정되어 있는 경우,  
     "앱스플라이어 CNAME이 발견되었습니다"가 표시됩니다.
   * CNAME을 찾을 수 없는 경우 앱스플라이어 CNAME 대상을 복사하여 DNS 관리자에게 보내고, 전체 도메인이 CNAME 대상과 연결되었는지 확인을 요청하십시오. DNS 관리자는 전체 도메인을 앱스플라이어 CNAME 대상으로 매핑해야 합니다. 그렇지 않으면 브랜드 도메인이 생성되더라도 작동하지 않습니다.

     <div id="note" />

     > 📘 **참고**
     >
     > CNAME 레코드는 브랜드 도메인 생성일로부터 확인 대화 상자에 지정된 날짜까지의 7일 이내에 매핑되어야 합니다.   
     > 지정된 날짜까지 CNAME 레코드가 매핑되지 않으면, 반드시  
     > [7일 기간을 갱신해야 합니다](#cname-레코드-매핑을-위한-7일-기간-갱신하기).

7. **완료**를 클릭합니다. 이제 브랜드 도메인이 있는 원링크 템플릿을 기반으로 새 링크를 만들 수 있습니다.

   <div id="note-1" />

   > 📘 **참고**
   >
   > * 브랜드 도메인 없이 원링크 템플릿을 기반으로 이미 링크를 만든 경우에도 계속 작동합니다.
   > * 새 브랜드 도메인이 작동되기까지 최대 24시간이 걸릴 수 있습니다.


<div id="renew-the-7-day-period-for-mapping-the-cname-record" />

#### CNAME 레코드 매핑을 위한 7일 기간 갱신하기

새로운 브랜드 도메인은 전체 도메인의 CNAME 레코드가 브랜드 도메인 생성일로부터 7일 이내에 앱스플라이어에 매핑되지 않으면 작동하지 않습니다.

<div id="note-2" />

> 📘 **참고**
>
> 7일 기간이 만료된 후에 레코드가 매핑되었다면, 새로운 브랜드 도메인이 작동하기 위해서는 여전히 7일 기간을 갱신해야 합니다.

**7일 기간을 갱신하는 방법:**

1. 앱스플라이어에서 사이드 메뉴에서 **인게이지(Engage)** > **브랜드 도메인(Branded Domains)** 을 선택합니다.
2. 앱스플라이어에 아직 매핑되지 않은 브랜드 도메인으로 이동하십시오. 해당 도메인은 경고 아이콘(![alert.png](https://files.readme.io/7df53739ca5c629ec0bda789563f59717da9699986222705228f57e0d947c8de-30192946335761.png))으로 표시됩니다.
3. 7일 기간을 갱신하려면 새로 고침 아이콘(<Image alt="refresh.png" src="https://files.readme.io/052b47c423612c1b0549f37ed6394373d37f28331e09f4c709601a7e5473bf2b-30192959741585.png" width="18px" />)을 클릭하세요.

<div id="note-3" />

> 📘 **참고**
>
> 7일 기간을 갱신하지 않기로 했다면, 삭제 아이콘(<Image alt="delete-subdomain.png" src="https://files.readme.io/0029cc63db331d998182d46a63f9da9856de9b2351abd5b2d87fb2b47ae853c2-30192959748241.png" width="16px" />)을 클릭하여 브랜드 도메인을 삭제할 수 있습니다. 아직 앱스플라이어에 매핑되지 않은 브랜드 도메인만 삭제할 수 있습니다.

<div id="custom-ssl-certificate-optional" />

#### 사용자 지정 SSL 인증서 (선택 사항)

AppsFlyer에서 관리하는 SSL은 대부분의 고객에게 권장되는 기본 옵션이며 AppsFlyer가 자동으로 인증서 발급 및 갱신을 처리하므로 추가 조치가 필요하지 않습니다. 특정 보안 또는 정보보호법 준수 요구 사항이 있는 경우 AppsFlyer에서 관리하는 SSL 대신 자체 SSL 인증 기관 (커스텀 SSL 인증서) 을 사용하도록 선택할 수 있습니다. 이 옵션을 선택하면 인증서 발급, 업로드, 유지 관리 및 갱신을 책임집니다. 인증서가 만료되고 기한 내에 갱신되지 않으면 서비스가 중단될 수 있습니다.

**커스텀 SSL 인증서를 사용하려면:**

1. [브랜드 도메인을 생성합니다](/docs/brand-onelink-with-your-domain#브랜드-도메인-설정).
2. 앱스플라이어의 참여 **> 브랜드** **도메인에서** 관련 도메인에 마우스를 올리고 “사용자 지정 SSL 인증서” 아이콘을 선택합니다.   
   <Image alt="SSL certificate icon Newest minimal.png" src="https://files.readme.io/8b22a41fd755a3f36e8eaf4a869b107661894d81504bbfb44e1fc728b9b06751-45231876708497.png" width="1044px" />
3. 인증서 세부 정보 양식을 작성합니다.   
   <Image alt="CSR을 생성하기 위한 양식 작성 file.png" src="https://files.readme.io/4327a4da0cbcc6243c9bbdbec21fe4f91d7fe701ccbffca99e629a5eadd248e8-45231876709649.png" width="66.18%" />
4. **CSR 다운로드를** 클릭하여 방금 작성한 양식의 사본을 다운로드합니다.  
   CSR 파일 다운로드
5. 방금 다운로드한 CSR 파일을 선택한 SSL 인증 기관에 제공합니다.
6. 새 SSL 인증서를 받으면 앱스플라이어에 다시 업로드하세요.

<Image alt="새 SSL 인증서를 AF.png 에 업로드" src="https://files.readme.io/b22525d9f653c3897f39f02a7beded3ad5c42d74a5487458f2ed720a20351e03-45231892701969.png" width="811px" />

<div id="note-4" />

> 📘 **참고**
>
> SSL 인증서가 만료됩니다. 현재 인증서가 만료되기 전에 인증서를 갱신하고 앱스플라이어에 업로드하는 것은 사용자의 책임입니다.

</Accordion>

<div id="set-up-branded-domains-in-the-app" />

<Accordion title="앱에서 브랜드 도메인 설정">

* 다음 SDK 버전을 사용하십시오.
  * 안드로이드 V4.10.1 이상
  * iOS V4.10.1 이상
  * iOS 및 안드로이드의 경우, 사용자 초대 리퍼럴(친구 초대)를 이용하려면 SDK 버전 V5.2.0 이상이 필요합니다.

**브랜드 도메인 SDK 구현 고려 사항**

* 브랜드 도메인을 사용하여 딥링킹을 수행하면 앱스플라이어 SDK는 인스톨 및 딥링킹을 위한 전환 데이터를 가져올 수 없습니다.
* 이를 해결하기 위해 개발자는 각각 안드로이드 및 iOS용 `setOneLinkCustomDomain`과 `oneLinkCustomDomains` SDK API를 사용합니다.
* 이 API는 브랜드 도메인을 쿼리하고, 해당 도메인이 매핑된 원링크 도메인을 가져온 후, 원링크를 완성합니다.

<Tabs>
<Tab title="안드로이드">

매니페스트의 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">intent-filter</Anchor>에서 android:host를 설정하여 브랜드 도메인이 포함되도록 업데이트해야 합니다.

<Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">Android global application class</Anchor>의 SDK를 초기화하기 전에 이 API를 사용해야 합니다.

**예시**

```java
public class AFApplication extends Application {

    @Override
    public void onCreate() {
    super.onCreate();

      // Set branded link domain. Don't include https:// as part of the domain. 
      AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com");
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionListener, this);
      AppsFlyerLib.getInstance().start(this, AF_DEV_KEY);

    }
}
```

여러 개의 브랜드 도메인이 있는 경우, 모든 도메인을 API에 전달해야 항상 전환 데이터를 받고 앱으로 딥링크할 수 있습니다.

**예시**

```java
AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com", 
                                                        "click.greatapp.com", 
                                                        "deals.greatapp.com");
```

</Tab>

<Tab title="iOS">

<Tabs>
<Tab title="Objective C">

didFinishLaunchingWithOptions 메서드 내에서, AppDelegate.m에 이 API를 사용합니다.

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    /** APPSFLYER INIT **/
    [AppsFlyerLib shared].appsFlyerDevKey = @"SED_DEV_KEY";
    [AppsFlyerLib shared].appleAppID = @"123456789";
    [AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com"];
    //...
    //...
  }
```

여러 개의 브랜드 도메인이 있는 경우, 모든 도메인을 API에 전달해야 항상 전환 데이터를 받고 앱으로 딥링크할 수 있습니다.

**예시**

```objectivec
[AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com", @"click.greatapp.com"];
```

</Tab>

<Tab title="Swift">

didFinishLaunchingWithOptions 메서드 내에서, AppDelegate.swift에 이 API를 사용해야 합니다.

```swift
   func application(_ application: UIApplication, didFinishLaunchingWithOptions 
        launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
          AppsFlyerLib.shared().appsFlyerDevKey = "6CQi4Be6Zs9oNLsCusPbUL"
          AppsFlyerLib.shared().appleAppID = "340954504"
          AppsFlyerLib.shared().oneLinkCustomDomains = ["example.com"]
          //...
          //...
   }
```

브랜드 도메인이 여러 개 있는 경우 이를 문자열 배열(an array of strings)로 API에 전달할 수 있습니다. 이렇게 하면 어떤 브랜드 링크가 사용되더라도 항상 전환 데이터를 받을 수 있고 앱으로 딥링크할 수 있습니다.

**예시**

```objectivec
AppsFlyerLib.shared().oneLinkCustomDomains = ["promotion.greatapp.com", "click.greatapp.com"]
```

</Tab>
</Tabs>

</Tab>
</Tabs>

</Accordion>

<div id="using-and-testing-branded-domains" />

<Accordion title="브랜드 도메인 사용 및 테스트">

**선행 조건**:

사용 및 테스트 전에, [브랜드 도메인 워크플로우](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app)의 단계를 모두 완료해야 합니다.

**브랜드 도메인을 생성하고 테스트하는 방법:**

1. 브랜드 도메인에 매핑된 원링크 템플릿을 사용하여 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#캠페인을-위한-원링크-링크-생성하기">원링크 링크를 생성</Anchor>하십시오.
2. 사용자정의 어트리뷰션 링크를 문서 편집기에 복사합니다.
3. 사용자정의 어트리뷰션 링크는 원링크 하위 도메인, 원링크 ID 및 사용자정의 링크 ID로 구성됩니다. 원링크 서브 도메인을 브랜드 도메인의 전체 도메인으로 교체합니다. 예시:

| 커스텀 어트리뷰션 링크 | 브랜드 도메인 |
| --- | --- |
| **abcdef.onelink.me**/A1bc/dc1234ef | **click.abcdef.com**/A1bc/dc1234ef |

4. 브랜드 링크를 사용하여 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">인스톨 및 딥링킹을 테스트</Anchor>합니다.
5. 테스트에 로데이터 리포트를 사용하는 경우, Original URL 필드는 브랜드 링크로 채워집니다.

</Accordion>

<div id="editing-verifying-and-deleting-branded-domains" />

<Accordion title="브랜드 도메인 편집, 검증 및 삭제">

<div id="edit-a-branded-domain-mapping" />

#### **브랜드 도메인 매핑을 편집하는 방법**

기존 전체 도메인의 매핑을 다른 원링크 서브 도메인으로 변경할 수 있습니다. CNAME을 설정하지 않아도 됩니다.

1. 앱스플라이어에서 사이드 메뉴에서 **인게이지(Engage)** > **브랜드 도메인(Branded Domains)** 을 선택합니다.
2. 편집하려는 브랜드 도메인으로 이동합니다.
3. 편집 아이콘을 클릭하세요. (<Image alt="edit-subdomain.png" src="https://files.readme.io/ffe3da7d1c065a806a44c607bcf1231e06bf7e7478ca50187e57cb5ab876ae72-30192959751185.png" width="17px" />)
4. 새 원링크 서브 도메인을 선택하세요.
5. **다음을 클릭합니다.** CNAME을 설정하지 않아도 됩니다.
6. **완료**를 클릭합니다.

<div id="important" />

> ❗️ **경고**
>
> 활성 캠페인에 대한 브랜드 도메인을 수정하면, 링크 기능이 변경되거나 비활성화될 수 있습니다.

<div id="verify-a-branded-domain-mapping" />

#### **브랜드 도메인 매핑 확인**

브랜드 도메인에 매핑된 원링크 서브 도메인을 변경한 후, 브랜드 도메인이 올바르게 매핑되었는지 확인하십시오:

1. 앱스플라이어에서 사이드 메뉴에서 **인게이지(Engage)** > **브랜드 도메인(Branded Domains)** 을 선택합니다.
2. 확인하려는 브랜드 도메인으로 이동합니다.
3. 확인 아이콘을 클릭하세요.(<Image alt="verify-2.png" src="https://files.readme.io/4ac94a535e9101b3e727351f67df8917c0870d6ede8ec963de8c5528893b8e2b-30192946342929.png" width="17px" />)

<div id="note-5" />

> 📘 **참고**
>
> CNAME 레코드가 아직 매핑되지 않아 인증에 실패한 경우, 인증 실패 대화 상자에 표시된 날짜까지 최대 7일의 기간 내에 매핑을 완료할 수 있습니다.
> 지정된 날짜까지 CNAME 레코드가 매핑되지 않으면, 반드시 7일 기간을 갱신해야 합니다.

<div id="domain-cname-record-no-longer-pointing-to-appsflyer" />

#### **도메인 CNAME 레코드가 더 이상 앱스플라이어와 연결되지 않음**

CNAME 레코드가 앱스플라이어와 연결되지 않도록 설정을 변경하면 앱스플라이어에서 브랜드 도메인이 삭제됩니다.

<div id="delete-a-branded-domain-mapping" />

#### **브랜드 도메인 매핑 삭제**

브랜드 도메인을 삭제하려면 앱스플라이어 CSM 또는 hello@appsflyer.com에 문의하십시오.

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## 문제 해결, 특성 및 제한 사항

<div id="troubleshooting" />

<Accordion title="문제 해결">

| 증상 | 원인/솔루션 |
| --- | --- |
| 브랜드 도메인을 원링크 템플릿으로 매핑할 수 없습니다. | <ul><li>**잘못된 도메인 이름:** 브랜드 도메인을 원링크 템플릿에 매핑할 때 앱스플라이어는 브랜드 링크에 유효한 도메인 이름이 있는지 확인합니다. 유효한 도메인 이름은 click.abdef.com 형식이어야 합니다.</li><li>**브랜드 도메인이 이미 매핑되어 있음**: 전체 도메인은 한 번만 매핑될 수 있습니다.</li></ul> |
| 브랜드 도메인이 앱으로 딥링킹을 하지 않습니다. | <ul><li>[브랜드 도메인이 작동하는지 확인합니다.](#브랜드-도메인-매핑-확인)</li><li>**CNAME 확인**: 브랜드 도메인에서 앱스플라이어로 CNAME 레코드가 연결되도록 설정해야 합니다.</li><li>**원링크 템플릿에 대한 딥링킹 설정 확인**: 원링크 딥링킹 설정에 문제가 있을 수 있습니다. 원링크와의 딥링킹이 설정돼 있는지 확인합니다.</li><li>**원링크 매핑 변경됨**: 브랜드 도메인을 편집하고 다른 원링크에 매핑할 수 있습니다. 새로 매핑된 원링크에 기존과 다른 딥링킹 설정이 있거나 딥링킹 설정이 없는 경우, 딥링크가 정상적으로 작동하지 않을 수 있습니다.</li></ul> |
| 브랜드 도메인에서 측정된 인스톨이 없음 | <ul><li>**원링크 템플릿 설정 확인**: 브랜드 도메인에 매핑된 원링크 서브 도메인이 올바른 앱들과 연결되어 있는지 반드시 확인하세요.</li><li>**원링크 서브도메인 변경됨:** 브랜드 도메인을 원링크 템플릿에 매핑하고 원링크 서브 도메인을 변경할 경우, 어트리뷰션에 영향을 줄 수 있습니다.</li><li>**구현 확인:** 앱에 setOneLinkCustomDomain API가 구현되어 있는지 확인하십시오.</li></ul> |
| 브랜드 도메인에 기록된 리인게이지먼트 없음 | 다음 항목이 활성화되고 구성되어 있는지 확인합니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/onelink-guide#원링크-설정하기">원링크를 사용한 딥링킹 설정</Anchor>.</li><li>앱은 전용 [SDK API setOneLinkCustomDomain](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer)을 활용합니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#retargeting-settings">앱 설정에서 리타게팅이 활성화됩니다</Anchor>.</li></ul> |
| 브랜드 도메인 설정 중에 **도메인이 존재하지 않음** 메시지가 표시됨 | <ol><li>DNS 관리자에게 문의하여 조사를 요청하십시오.</li><li>DNS 관리자가 도메인이 등록되었는지 확인할 때까지 대기합니다.</li><li>**재확인**을 클릭하세요.</li></ol> |
| 브랜드 도메인 설정 중에 **앱스플라이어 CNAME을 찾을 수 없음** 메시지가 표시됨 | <ol><li>DNS 관리자에게 전체 도메인(브랜드 도메인)이 지정된 URL(앱스플라이어 호스트)과 연결될 수 있게 CNAME 레코드를 설정하도록 요청하십시오. 이는 해당 문서의 최상단에 있는 그림에 나타나 있습니다.</li><li>DNS 관리자가 CNAME이 활성화되었음을 확인할 때까지 대기합니다.</li></ol> |
| 브랜드 도메인 페이지를 로드할 때 **“차단되었습니다(you have been blocked)”** 메시지가 표시되는 경우 | 브랜드 도메인에는 템플릿이나 파라미터를 포함하지 않습니다. 브랜드 도메인을 사용할 때는 브랜드 도메인 URL의 끝에 템플릿 또는 파라미터를 추가해야 합니다.<br /><br />예를 들어, click.abcdef.com이 귀하의 브랜드 도메인일 때, **click.abcdef.com**만 사용하는 경우 **차단되었습니다(you have been blocked)** 라는 메시지가 표시됩니다.<br /><br />파라미터 또는 템플릿을 끝에 추가해야 합니다. 예시: click.abcdef.com **/A1bc/dc1234ef** |
| 브랜드 도메인 페이지를 로드할 때 발생하는 **err\_cert\_authority\_invalid** 오류 | 이 오류는 인증 기관이 인식되지 않아, 브랜드 도메인에 유효한 HTTPS 인증서가 없음을 나타냅니다. 앱스플라이어는 Let's Encrypt로 브랜드 도메인을 인증하기 때문에 도메인의 CAA(Certification Authority Authorization) DNS 레코드에 따라 Let's Encrypt가 유효한 인증 기관(CA)으로 인식되지 않기 때문에 오류가 발생할 수 있습니다.<br /><br />**솔루션**<br />다음 작업을 수행해 주십시오:<ol><li>도메인이 <Anchor target="_blank" href="https://www.entrust.com/resources/certificate-solutions/tools/caa-lookup">이와</Anchor> 같은 서비스를 사용하여 Let's Encrypt를 CA로 인식하는지 확인합니다.</li><li>시스템 관리자에게 Let's Encrypt를 인증된 CA로 포함하도록 도메인 CAA 레코드를 업데이트하도록 요청합니다.</li></ol> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 예 ✓ /아니요 **x** | 비고 |
| --- | --- | --- |
| 계정 유저 액세스 | ✓ |  |
| 애드 네트워크 액세스 | **x** |  |
| 에이전시 액세스 | **x** | 에이전시는 브랜드 도메인(또는 원링크 링크)을 생성할 수 없습니다. |
| 에이전시 투명성 | **x** |  |
| 앱별 통화 | 해당 없음 |  |
| 앱별 시간대 | 해당 없음 |  |
| 브랜드 도메인 사용 가능 여부 | 해당 없음 | 브랜드 도메인은 적격한 유료 플랜에서만 사용할 수 있습니다. 구독 플랜이 만료되거나 취소되면 브랜드 도메인에 대한 액세스가 제거되고 브랜드 도메인을 사용하는 기존 링크는 작업하지 않습니다. |
| 문자 제한 | 해당 없음 | 브랜드 도메인을 입력할 때 마침표(".")를 마지막 문자로 사용할 수 없습니다. |
| 데이터 최신성 | 해당 없음 |  |
| 과거 데이터 | ✓ |  |
| HTTP | **x** | HTTP 프로토콜은 브랜드 링크에서 지원되지 않습니다. HTTPS를 사용해야 합니다. |
| 논오가닉 데이터 | ✓ |  |
| 오가닉 데이터 | ✓ |  |
| 발급 제한 | ✓ | 브랜드 도메인 SSL/HTTP 인증서는 앱스플라이어에 의해 <Anchor target="_blank" href="https://letsencrypt.org/">Let's Encrypt</Anchor>에 따라 처리되며, 새 인증서는 하나의 도메인마다 매주 50개로 제한됩니다. |
| 사이즈 제한 | 해당 없음 |  |
| SSL/HTTP 인증서 갱신 | ✓ | 귀하의 브랜드 도메인 SSL/HTTP 인증서는 AppsFlyer에 의해 관리되며, 별도의 조치 없이 자동으로 갱신됩니다. |

</Accordion>

<div data-zendesk-anchors="branded-domains=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%8F%84%EB%A9%94%EC%9D%B8 h_01HFM51V4PE53FQAED68V8Q834=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%8F%84%EB%A9%94%EC%9D%B8 principles-of-implementation=%EA%B5%AC%ED%98%84-%EC%9B%90%EC%B9%99 h_01HFM51V4PPJXMCSV5ZVDPT49M=%EA%B5%AC%ED%98%84-%EC%9B%90%EC%B9%99 setting-up-branded-domains=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%84%A4%EC%A0%95 h_01HFM51V4PH58ZA4ZXHP5J6K2W=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%84%A4%EC%A0%95 procedures=%EC%A0%88%EC%B0%A8 h_01HFM51V4PWWX7TBCHFMPR3QVB=%EC%A0%88%EC%B0%A8 h_01HQ5CWGQNRBXQ6QQDADV7XCQP=set-up-a-branded-domain-in-appsflyer h_01HQ5CWGQN7ED03CBQE3XMJQC6=%EC%B0%B8%EA%B3%A0 h_01HQ5DHKPW0RBEDZ3JVZRV37JW=%EC%B0%B8%EA%B3%A0-1 renew-the-day=cname-%EB%A0%88%EC%BD%94%EB%93%9C-%EB%A7%A4%ED%95%91%EC%9D%84-%EC%9C%84%ED%95%9C-7%EC%9D%BC-%EA%B8%B0%EA%B0%84-%EA%B0%B1%EC%8B%A0%ED%95%98%EA%B8%B0 h_01HQ5CWGQNQJJ1CXDKTGZ8N9ZE=cname-%EB%A0%88%EC%BD%94%EB%93%9C-%EB%A7%A4%ED%95%91%EC%9D%84-%EC%9C%84%ED%95%9C-7%EC%9D%BC-%EA%B8%B0%EA%B0%84-%EA%B0%B1%EC%8B%A0%ED%95%98%EA%B8%B0 h_01HQ5CWGQNEPDY6J30B6VY0FCP=%EC%B0%B8%EA%B3%A0-2 h_01HQ5CWGQNSRNKQHARJCB3C5EA=%EC%B0%B8%EA%B3%A0-3 custom-ssl-certificate=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-ssl-%EC%9D%B8%EC%A6%9D%EC%84%9C-%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD h_01KM0E8VHARA2JRAR2H37QM91Y=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-ssl-%EC%9D%B8%EC%A6%9D%EC%84%9C-%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD h_01KM0FTWTX09651KY524RH9JSJ=%EC%B0%B8%EA%B3%A0-4 h_01HFM51V4PP0NQHVHTKB86250R=set-up-branded-domains-in-the-app h_01HFM51V4PN0FPEDNAF0Q1QS8P=using-and-testing-branded-domains h_01HQ5CWGQPZ6MEFA6MDTHYHCSA=editing-verifying-and-deleting-branded-domains edit-a-branded-domain-mapping=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%A7%A4%ED%95%91%EC%9D%84-%ED%8E%B8%EC%A7%91%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01HQ5FJZD6QMNFA45Z2C7CA3ST=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%A7%A4%ED%95%91%EC%9D%84-%ED%8E%B8%EC%A7%91%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01HQ5G6ZQ481TGXA0P6FNB4NN7=%EA%B2%BD%EA%B3%A0 verify-a-branded-domain-mapping=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%A7%A4%ED%95%91-%ED%99%95%EC%9D%B8 h_01HQ5FK5XJNZ1EABJA66RMYBCN=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%A7%A4%ED%95%91-%ED%99%95%EC%9D%B8 h_01HQ5CWGQP7F54G518AKV2PV1G=%EC%B0%B8%EA%B3%A0-5 domain-cname-record-no-longer-pointing-to-appsflyer=%EB%8F%84%EB%A9%94%EC%9D%B8-cname-%EB%A0%88%EC%BD%94%EB%93%9C%EA%B0%80-%EB%8D%94-%EC%9D%B4%EC%83%81-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%99%80-%EC%97%B0%EA%B2%B0%EB%90%98%EC%A7%80-%EC%95%8A%EC%9D%8C h_01JSHFECXS00M6BXH8168ZWJE5=%EB%8F%84%EB%A9%94%EC%9D%B8-cname-%EB%A0%88%EC%BD%94%EB%93%9C%EA%B0%80-%EB%8D%94-%EC%9D%B4%EC%83%81-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%99%80-%EC%97%B0%EA%B2%B0%EB%90%98%EC%A7%80-%EC%95%8A%EC%9D%8C delete-a-branded-domain-mapping=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%A7%A4%ED%95%91-%EC%82%AD%EC%A0%9C h_01JSHF5RMXXFJTXC246KKAQBSS=%EB%B8%8C%EB%9E%9C%EB%93%9C-%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%A7%A4%ED%95%91-%EC%82%AD%EC%A0%9C troubleshooting-traits-and-limitations=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HFM51V4PH4YM13DVXENRWF2E=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HFM51V4PJNHZTD97X75WPN98=troubleshooting h_01HFM51V4QQ2TZQMJ2ATNDG91F=traits-and-limitations" />
