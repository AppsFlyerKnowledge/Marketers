---
title: 도메인 리디렉션 허용 목록 설정
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2024-05-15T11:31:00Z'
  edited_at: '2026-10-14T10:30:38Z'
  id: 25068636064529
  locale: ko
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ko/articles/25068636064529
---
> **한눈에 보기:** 도메인 리디렉션 허용 목록을 설정하여, 유저를 검증되고 신뢰할 수 있는 도메인으로 안내합니다. 이로써 데이터를 보호하고 브랜드 신뢰도를 확보하세요.

<div id="about-the-redirect-allowlist" />

## <Image alt="메인 리디렉션 허용 목록 이미지.png" src="https://files.readme.io/a13b1c4641f4b265ef93ba9b65c57b0a7891336d6f6c21e94dd2ff5d83b948d6-30258741325713.png" width="1340px" />리디렉션 허용 목록에 대하여

리디렉션 허용 목록을 사용하여 링크 리디렉션이 허용되는 특정 루트 도메인 및 서브 도메인 목록을 정의하여 무단 리디렉션, 피싱 공격 및 프로드로부터 링크를 보호합니다. 허용 목록이 활성화되면 앱스플라이어를 통해 생성하는 링크는 도메인이 허용 목록에 있는 웹 URL로만 유저를 리디렉션합니다. 그렇지 않은 경우, 유저가 앱 스토어로 이동합니다. 리디렉션 허용 목록은 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">파트너 연동</Anchor>을 통한 단일 플랫폼 어트리뷰션 링크와 CTV, PC 및 콘솔 플랫폼을 위한 <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">다이렉트 어트리뷰션 링크</Anchor>에 적용됩니다. 리디렉션 허용 목록(및 사용자 정의 웹 리디렉션)은 Growth, Enterprise 플랜 구독 회원에게 제공됩니다.

<div id="set-up-your-redirect-allowlist" />

## 리디렉션 허용 목록 설정

허용 목록은 수동으로 또는 CSV 파일을 통해 설정할 수 있습니다. 설정하기 전에 보안팀과 함께 신뢰할 수 있는 도메인 목록을 확인하세요.

<div id="manual-setup" />

<Accordion title="수동 설정">

**수동으로 설정하려면:**

1. 상단 메뉴에서 계정 메뉴(이메일 주소 드롭다운) > **보안 센터(Security Center)** 를 엽니다.

![from account click security center Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. **리디렉션 허용 목록(Redirect Allowlist)** 섹션에서 **리디렉션 허용 목록 관리**를 클릭합니다.

<Image alt="Manage redirect allowlist with arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="549px" />  

**리디렉션 허용 목록(Redirect Allowlist)** 페이지가 열립니다.

3. **수동** 탭 아래 **도메인 이름** 필드에 루트 도메인이나 서브 도메인을 입력한 다음, **목록에 도메인 추가**를 클릭합니다.

<Image alt="Manually add domains.jpg" src="https://files.readme.io/95b37db2064ddba8c787d2dd5ac5ab2aa7698605f5c6eb3b4a59dd6324dee355-25103405228689.jpg" width="403px" />

* 문자, 숫자, 하이픈 및 마침표만 사용합니다.
* 도메인은 문자 또는 숫자로 시작하고 끝나야 하며, 최대 253자까지 입력할 수 있습니다.
* https:// 와 같은 프리픽스를 추가하지 마세요.

허용 목록 [특징 및 제약 사항](/docs/set-up-your-domain-redirect-allowlist#특징-및-제약-사항)도 참조하세요.

추가된 도메인이 오른쪽 목록에 표시됩니다.

4. **목록 저장**을 클릭합니다.

저장 후 약 1시간 이내에 허용 목록이 활성화되어 클릭에 적용됩니다.

</Accordion>

<div id="setup-via-csv-file" />

<Accordion title="CSV 파일을 통한 설정">

**CSV 파일 업로드를 통해 설정하려면:**

1. 상단 메뉴에서 계정 메뉴(이메일 주소 드롭다운) > **보안 센터(Security Center)** 를 엽니다.  

![from account click security center Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. **리디렉션 허용 목록(Redirect Allowlist)** 섹션에서 **리디렉션 허용 목록 관리**를 클릭합니다.  
<Image alt="Manage redirect allowlist with arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="530px" />  

**리디렉션 허용 목록(Redirect Allowlist)** 페이지가 열립니다.

3. **CSV 파일** 탭을 클릭한 다음, **CSV 파일 지침**을 클릭하여 도메인 목록이 포함된 파일을 만듭니다.  
![CSV file upload.jpg](https://files.readme.io/2be73080048545f79e102e6f48df0db956e6739f156153c172c4fef5a2ea339f-25381979219345.jpg)

4. CSV 파일을 업로드 필드에 업로드합니다.

* 파일이 업로드되면, 해당 파일이 분석되고 값의 유효성이 검증됩니다.
* 유효한 값이 자동으로 추가되어 오른쪽 목록에 표시됩니다.
* 유효하지 않은 값은 추가되지 않습니다. 잘못된 값에 대한 정보는 **업로드 상태** 섹션에 표시되므로, 값을 검토 및 수정하고 다시 업로드하는 조치를 취할 수 있습니다. 자세한 내용은 허용 목록 [특징 및 제약 사항](/docs/set-up-your-domain-redirect-allowlist#특징-및-제약-사항)을 참조하세요.

5. **목록 저장**을 클릭합니다.

저장 후 약 1시간 이내에 리디렉트 허용 목록이 활성화되어 클릭에 적용됩니다.

</Accordion>

<div id="edit-the-redirect-allowlist" />

<Accordion title="리디렉션 허용 목록 수정">

언제든지 허용 목록에서 도메인을 추가하거나 삭제할 수 있습니다.

**허용 목록에서 도메인을 삭제하는 방법은 다음과 같습니다.**

1. 오른쪽 목록에서 삭제하려는 도메인을 마우스로 가리키면 삭제 아이콘이 나타납니다.
2. 삭제 아이콘을 클릭합니다.
3. **목록 저장**을 클릭하여 변경 사항을 저장합니다.

**참고:** 저장이 완료되면, 업데이트된 리디렉션 허용 목록은 약 1시간 내에 클릭에 적용됩니다.

</Accordion>

<div id="traits-and-limitations" />

## 특징 및 제약 사항

| 특징 | 비고 |
| --- | --- |
| 설정 | <ul><li>리디렉션 허용 목록은 'Admin' 및 'Security' 역할이 액세스하고 관리할 수 있습니다.</li><li>리디렉션 허용 목록은 계정 레벨에 있으며 계정의 모든 앱과 모든 앱스플라이어 링크에 적용됩니다.</li><li>리디렉션 허용 목록(및 사용자 정의 웹 리디렉션)은 Growth, Enterprise 플랜 구독 회원에게만 제공됩니다. 여러 계정에 연결된 팀 멤버는 결제 수단이 등록되어 있지 않은 계정이 한개라도 있을 경우, 모든 계정들에 대해 리디렉션 허용 목록을 사용할 수 없습니다.</li><li>앱스플라이어 링크 생성 관리를 담당하는 동료 및 이해관계자에게 리디렉션 허용 목록 적용 및 허용된 리디렉션 도메인에 대해 사전에 알리세요.</li></ul> |
| 적용 가능 범위 | <ul><li>허용 목록은 **AppsFlyer를 통해 생성된 모든 링크**에 영향을 미치며, 이는 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">OneLink</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">파트너 연동</Anchor>을 통한 단일 플랫폼 어트리뷰션 링크 또는 CTV, PC 및 콘솔 플랫폼을 위한 <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">어트리뷰션 링크</Anchor>를 포함하며, 링크 생성 시점에 관계없이 적용됩니다.</li><li>여기 명시된 링크 리디렉션 설정에서 값으로 설정된 모든 URL의 도메인을 허용 목록에 포함하십시오. 여기에는 사용자 지정 웹사이트/랜딩 페이지, Google Play/App Store, 또는 다른 앱 스토어 웹사이트가 포함됩니다. 허용 목록은 다음에 대한 리디렉션을 지원하고 보호합니다.<ul><li>링크 파라미터:<ul><li>`af_r`</li><li>`af_web_dp`</li><li>`af_ios_url`</li><li>`af_android_url`</li></ul></li><li>iOS, Android 및 데스크톱을 위한 원링크 템플릿 리디렉션 설정</li><li>웹 URL을 `af_dp` 값으로 사용하는 경우. 하지만 웹 URL은 `af_dp` 값으로 권장되는 값이 아닙니다. 이 파라미터는 앱을 열기 위한 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_dp">URI 스킴</Anchor> 값을 채우는 데 사용됩니다.</li></ul></li></ul> |
| 도메인 | <ul><li>허용 목록에는 도메인이 하나 이상 포함되어야 합니다.</li><li>루트 도메인 또는 서브 도메인만 허용되며 특정 경로는 허용되지 않습니다. ‘https://’ 또는 ‘http://’ 프로토콜을 값에 포함하지 마세요.</li><li>루트 도메인을 추가하면, 루트 도메인 내의 모든 서브 도메인에 적용됩니다.<br />예를 들어, 루트 도메인 “website.com”을 추가하면 “abc.website.com” 및 “xyz.website.com”도 적용됩니다.</li><li>리디렉션은 공개적으로 접근 가능한 도메인에 대해서만 지원됩니다.</li><li>링크 리디렉션의 예측 가능성을 강화하기 위해 앱스플라이어 도메인(예: onelink.me, app.appsflyer.com) 또는 자체 리디렉션 메커니즘이 있는 기타 도메인(예: bit.ly)을 포함하지 마십시오.</li><li>최대 100개의 도메인/서브 도메인을 허용 목록에 추가할 수 있습니다. 리디렉션 허용 목록으로 이동하면, 도메인 개수가 표시되며 이미 추가된 도메인 수를 확인할 수 있습니다.</li></ul> |
| 리디렉션 | 링크가 리디렉션되는 도메인이 허용되는지 확실하지 않은 경우:<br /><br />허용 목록을 검토하여 해당 도메인이 포함되어 있는지 확인하세요.<br /><br />또는<br /><br /><Anchor target="_blank" href="/marketers/ko/docs/discover-your-campaign-link-parameters-and-behavior">링크 검색(Link Discovery)</Anchor> 툴을 사용합니다. 링크를 입력하고 해당 도메인이 허용 목록에 없는 경우, (**리디렉션** 아래) **파라미터** 열에 경고가 표시됩니다. |

<div data-zendesk-anchors="overview=%EB%A6%AC%EB%94%94%EB%A0%89%EC%85%98-%ED%97%88%EC%9A%A9-%EB%AA%A9%EB%A1%9D%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HYTJSH4YMAJ3CV88KZ9JD9XR=%EB%A6%AC%EB%94%94%EB%A0%89%EC%85%98-%ED%97%88%EC%9A%A9-%EB%AA%A9%EB%A1%9D%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC set-up-your-redirect-allowlist=%EB%A6%AC%EB%94%94%EB%A0%89%EC%85%98-%ED%97%88%EC%9A%A9-%EB%AA%A9%EB%A1%9D-%EC%84%A4%EC%A0%95 h_01HY0BNRBEN91348744YME42SW=%EB%A6%AC%EB%94%94%EB%A0%89%EC%85%98-%ED%97%88%EC%9A%A9-%EB%AA%A9%EB%A1%9D-%EC%84%A4%EC%A0%95 h_01HY04JEK8J3664HE8J9783S61=manual-setup h_01HY04JEK8Y51EG3H6WFKHYYH4=setup-via-csv-file h_01HY04JEK840Q4DZ2SRMTB7HRE=edit-the-redirect-allowlist traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
