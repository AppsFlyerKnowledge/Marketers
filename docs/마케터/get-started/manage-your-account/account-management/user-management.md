---
title: 사용자 관리
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2021-10-17T11:54:49Z'
  edited_at: '2026-10-14T10:31:40Z'
  id: 4409128270481
  locale: ko
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/ko/articles/4409128270481
---
> **한눈에 보기:** 앱스플라이어 계정 사용자를 생성하고 관리하며, 사용자가 특정 기능, 앱, 데이터에 액세스할 수 있도록 권한을 할당합니다.

## 개요

앱스플라이어 계정은 여러 사용자가 동시에 사용할 수 있으며, 각 사용자마다 할당되는 권한이 다릅니다. 계정당 최대 사용자 수는 가입 요금제에 따라 달라집니다.

사용자의 권한은 다음 3가지 영역으로 구분됩니다.

* **역할**(플랫폼 기능에 액세스하고 동작을 수행할 수 있는 권한)
* 현재 및 미래의 앱에 대한 **앱 액세스**
* 미디어 소스 및 지역별 **데이터 액세스**
  * 중요! 특정 앱스플라이어 대시보드 및 기능은 데이터 액세스(미디어 소스 및 지역)가 제한된 사용자는 사용할 수 없습니다. 해당 대시보드 및 기능은 [여기에 나열되어 있습니다.](#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)

각 영역 내 권한은 독립적으로 할당됩니다. 즉, 사용자에 광범위한 권한을 가진 **역할**을 할당하되, **앱, 미디어 소스 및 지역 범주로 제한하여 특정 범위에서만 권한을 가지도록 설정할 수 있습니다.** 예외적으로 [관리자](#관리자)는 모든 권한을 가지며 앱, 미디어 소스 및 지역에 액세스할 수 있습니다.

관리자는 [여러 계정에 사용자를 추가](#multiple-accounts)하여 사용자가 계정 간 쉽게 전환할 수 있도록 합니다.

## 사용자 관리 페이지

**사용자 관리 페이지에 액세스하는 방법:**

* 상단 표시줄에서 계정 메뉴(이메일 주소 드롭다운)를 선택하고 >**사용자 관리**를 선택합니다.

[![user-management-page.jpg](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)

<div id="users-tab" />

<Accordion title="사용자 탭">

**사용자**탭에는 계정에 연동된 전체 사용자가 표시됩니다. 이곳에서 사용자를 추가, 관리 및 삭제할 수 있습니다.

사용자 탭 활용팁:

* **사용자** 열 제목을 클릭하여 표를 알파벳순으로 정렬합니다(오름차순/내림차순).
* 서치 박스에서 특정 사용자를 검색하면 결과가 화면에 나타납니다.
* **역할** 열 제목에서 필터 아이콘 <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" />을 클릭하여 역할(임시 역할 포함)별로 사용자를 정렬합니다.
  * 필터를 지우려면 필터 드롭다운 목록에서 **없음**을 선택합니다.
* **마지막 로그인** 열 제목을 클릭하여 앱스플라이어에 마지막으로 로그인한 날짜를 기준으로 사용자를 정렬합니다.
  * **팁:** 이 기능을 사용하여 비활성 사용자를 쉽게 식별 및 [삭제](#deleting-users)하고 무단 로그인으로부터 계정을 안전하게 보호하세요.
* 박스를 체크하여 여러 사용자를 동시에 선택하고 수정합니다.
* 관리자 전용: 페이지의 오른쪽 상단 모서리에 있는 다운로드 아이콘 <Image alt="download_icon.png" src="https://files.readme.io/fba5d56ceb7f6b3dc3191e5ec33c85ccbba0f7dc409ad0390de238c12b479b61-31780969029777.png" width="24px" />을 클릭하여 전체 사용자 테이블을 CSV 파일로 다운로드합니다.
  * 다운로드한 파일에는 **사용자** 탭에 있는 표와 동일한 열이 포함되어 있습니다.

</Accordion>

<div id="roles-tab" />

<Accordion title="역할 탭">

**역할** 탭에는 다음의 역할을 포함한 계정에 정의된 모든 역할이 목록으로 표시됩니다.

* [사전 정의된 역할](#사전-정의된-역할)
* 커스텀 생성된 역할
* 사용자에게 할당된 [임시 역할](#임시-역할)

역할 이름 옆에는 해당 역할에 현재 할당된 사용자 수가 표시됩니다.

왼쪽 패널에서 특정 역할을 클릭하면 해당 역할의 권한에 대한 세부 정보가 표시됩니다.

</Accordion>

아래 선택 가능한 작업을 살펴보고 사용자와 사용자 역할을 효과적으로 관리하세요.

## 사용자 관리하기

관리자는 새 사용자를 생성하고 여러 계정에 추가할 수 있으며, 앱과 데이터에 대한 액세스 권한 및 역할 등의 세부 정보를 수정하고, 사용자를 삭제할 수 있습니다. 이 작업 중 일부는 [전용 API를 사용하여 일괄 처리할 수 있습니다](#api를-통한-다수의-사용자-관리).

<div id="creating-users" />

<Accordion title="사용자 생성">

<Embed title="사용자 관리" typeOfEmbed="youtube" url="https://www.youtube.com/embed/wLCXP5dFrKg" providerUrl="https://www.youtube.com" />

사용자를 생성하거나 편집하는 페이지에는 여러 섹션이 포함되어 있습니다. 아래 나온 순서에 따라 사용자를 생성합니다. 변경 사항을 저장하려면 페이지의 오른쪽 하단에 있는 **저장**을 클릭하세요.

#### 사용자 정보

1. **사용자** 탭에서 **새 사용자**를 클릭합니다.
2. 사용자 이름을 입력합니다(필수):
   * 문자, 숫자, 공백, 마침표(.), 하이픈(-), 밑줄(\_), 작은따옴표(') 또는 큰따옴표(")를 포함할 수 있습니다.
   * 다른 특수 문자는 허용되지 않습니다.
3. 사용자의 이메일 주소를 입력합니다(필수).

   * 문자, 숫자, 아포스트로피('), 앰퍼샌드(&), 달러 기호($), 해시 기호(#), 하이픈(-), 밑줄(\_) 및 마침표(.)를 포함할 수 있습니다.
   * 연이은 두 개의 마침표(..) 및 기타 특수 문자는 허용되지 않습니다.
   * 유효한 이메일 도메인이어야 합니다.

   > 🚧 **중요!**
   >
   > 앱스플라이어 플랫폼에서는 사용자의 이메일 주소로 사용자를 식별합니다. 아래 유의사항을 참고하세요.
   >
   > * 사용자를 삭제하고 다시 생성하지 않는 한 변경이 불가능합니다.
   > * 수신 가능한 올바른 이메일 주소여야 합니다.
   > * 이메일은 다른 사용자와 중복될 수 없으며, 동일 사용자가 여러 계정을 사용하는 경우에만 동일 이메일 주소 사용이 허용됩니다. 이메일 주소가 이미 사용 중인 경우(현재 계정 또는 다른 계정에서) *이 사용자를 만들 수 없습니다*라는 메시지가 표시됩니다. 이 문제를 해결하려면 [아래의 문제 해결 단계](/docs/user-management#troubleshooting-can-t-create-this-user)를 수행하세요.

4. 사용자의 부서를 선택합니다(선택 사항).

#### 역할

사전 정의된 역할 또는 커스텀 생성한 역할 중 하나로 사용자의 역할(필수)을 선택합니다.

#### 앱 액세스

사용자가 접근할 수 있는 앱을 선택하세요:

* 기본 설정은 사용자가 계정의 현재 앱과 향후 설치되는 앱에 모두 액세스할 수 있도록 설정되어 있습니다. 이 설정을 변경하려면 박스를 체크하여 앱을 선택하거나 취소하세요.
* 현재 사용하는 앱에 모두 액세스할 수 있는 경우에만 이후 모든 앱에 대한 액세스 권한을 부여받을 수 있습니다.

#### 데이터 액세스

미디어 소스 및 지역에 대한 사용자 접근 수준을 설정하세요. 모든 데이터에 대한 접근을 허용할지 선별적으로 허용할지를 선택해 주세요.

> 📘 **참고**
>
> 미디어 소스 또는 지역에 대한 접근이 제한적인 사용자는 특정 [대시보드 및 기능](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)에 접근할 수 없습니다.

#### 미디어 소스

기본적으로 **모두(All)** 설정은 계정 내 모든 미디어 소스에 대한 접근을 허용합니다. 향후에 추가되는 미디어 소스에 대한 접근 또한 허용됩니다. 특정 미디어 소스를 선택하면, 이후 새로 추가되는 미디어 소스에 대한 접근 권한이 자동으로 부여되지 않습니다.

> 📘 **참고**
>
> * 미디어 소스에 대한 접근이 제한적인 사용자는 특정 [대시보드 및 기능](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)에 접근할 수 없습니다.
> * 관리자 및 보안 책임자는 모든 미디어 소스에 대해 제한 없이 접근할 수 있습니다. 이 설정은 변경할 수 없습니다.

**미디어 소스 유형:**

목록에 표시된 미디어 소스 유형은 두 가지입니다:

* **유료 미디어 소스:** 애드 네트워크, 셀프 리포팅 애드 네트워크(SRNs) 및 에이전시
* 커스텀 미디어 소스: 사전 정의된 미디어 소스. 온드 미디어 링크, Single Source 링크, OneLink 링크 및 광고주가 앱스플라이어 외부에서 생성한 링크가 포함될 수 있습니다.

**미디어 소스 목록 산출 기준:**

* 지난 24개월 내에 트래픽이 있는 미디어 소스를 가장 최근 트래픽 순으로 정렬하여 표시
* 목록 하단에 에이전시 별도로 분류
* 최대 10,000개의 미디어 소스 포함
  * 최대 5,000개의 애드 네트워크, SRN 및 커스텀 미디어 소스 포함
  * 최대 5,000개의 에이전시 포함
* 하루 한 번 업데이트 새로 추가된 미디어 소스는 트래픽이 시스템에 집계되고 하루가 지나야 목록에 나타납니다.
* 5년 넘게 트래픽이 없는 미디어 소스는 목록에서 제거됩니다.

**기본 설정을 변경하려면:**

1. **미디어 소스** 아래에서 **모두**를 클릭합니다.
2. 드롭다운 목록에서 액세스를 부여할 미디어 소스를 선택하여 사용자에게 권한을 부여합니다.

해당 설정이 저장되면, 사용자 대시보드는 선택한 미디어 소스의 데이터만 표시합니다.

#### 지역

사용자가 **모든** 지역 데이터에 액세스할 수 있는지, 특정 지역에 대해서만 액세스할 수 있는지 선택합니다. 기본 설정은 모든 지역에 액세스할 수 있도록 되어있습니다. 제한된 액세스는 사용자가 특정 [대시보드 및 기능](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)에 액세스할 수 없음을 의미합니다.

**기본 설정을 변경하려면:**

1. **지역** 아래에서 **모두**를 클릭합니다.
2. 드롭다운 목록에서 액세스를 부여할 지역을 선택하여 사용자에게 권한을 부여합니다.

#### 사용자 활성화

사용자가 생성되면 봉투 아이콘 ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png)과 함께 사용자 테이블에서 확인하실 수 있습니다. 이는 사용자 초대가 완료되었으며 계정이 활성화되기 이전임을 의미합니다. 사용자는 이메일의 링크를 사용하여 계정을 활성화해야 합니다. 활성화 링크는 48시간 동안 유효합니다. 사용자가 계정을 활성화하면 봉투가 사라집니다.

> 📘 **참고**
>
> 사용자가 초대받지 못했거나 링크가 만료된 경우 [초대장을 다시 전송](/docs/user-management#resending-a-user-invitation)할 수 있습니다.

</Accordion>

<div id="multiple-accounts" />

<Accordion title="여러 계정에 사용자 추가">

사용자를 여러 계정에 추가하고 계정마다 다른 역할을 할당할 수 있습니다. 이렇게 하면 사용자가 다시 자격 증명을 할 필요 없이 다른 계정에서 작업할 수 있습니다.

#### 여러 계정에 로그인

사용자는 다음의 로그인 방법으로 여러 계정에 로그인할 수 있습니다: 자격 증명(사용자 이름 및 비밀번호), <Anchor target="_blank" href="/marketers/ko/docs/implementing-and-using-2fa-login">2FA</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/set-up-sso-authentication-with-your-identity-provider-idp">SSO</Anchor>

#### 지원되는 계정 및 사용자

광고주 계정의 경우 하나의 사용자가 여러 계정에 추가될 수 있습니다. 적절한 권한을 가진 사용자는 자신이 관리하는 계정에 다른 사용자를 추가할 수 있습니다. 아래 제한 사항 참조

#### 여러 계정에 사용자 추가 시 제한 사항

* 이 기능은 광고주 계정에만 적용되며, 사용자 관리 권한이 있는 사용자만이 이용할 수 있습니다.
* 사용자는 하나의 계정에 대해서만 [계정 소유자](#계정-소유자) 역할을 맡을 수 있습니다. 다른 계정에서는 다른 역할을 맡을 수 있습니다.
* 아직 [계정을 활성화](#사용자-활성화)하지 않은 사용자는 다른 계정에 추가될 수 없습니다.

#### 여러 계정에 사용자 추가

**동일한 사용자를 여러 계정에 추가하는 방법:**

1. 사용자를 추가하려는 계정에 로그인합니다.
2. **메뉴 바에서** **이메일 주소 드롭다운** > 사용자 관리를 클릭합니다.
3. **사용자** 탭에서 **새 사용자**를 클릭합니다.
4. 필요한 세부 정보를 입력하고 해당 계정의 사용자 역할을 선택한 다음 **저장**을 클릭합니다.
5. 1&#126;4단계를 반복하여 다른 계정에 사용자를 추가합니다.

</Accordion>

<div id="editing-users" />

<Accordion title="사용자 편집">

사용자를 한 번에 한 명씩 또는 그룹 단위로 편집할 수 있습니다.

#### 개별 편집

**사용자를 개별로 편집하는 방법:**

1. **사용자** 탭에서 사용자 행의 맨 오른쪽에 있는 **조치** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> 버튼을 클릭합니다.
2. 메뉴에서 **편집**을 선택합니다.
3. 필요에 따라 사용자 설정을 편집하세요.
4. 이메일 주소 이외의 모든 설정은 편집 가능합니다(역할, 앱, 미디어 소스 및 지역 포함).
5. **저장**을 클릭합니다.

#### 다중 사용자 편집

다중 사용자 편집은 여러 사용자의 계정 권한을 한 번에 변경할 수 있는 효율적인 방법입니다. 이 기능을 **사용자** 탭의 검색 및 필터링 기능과 함께 사용하면 다수의 사용자를 쉽게 관리할 수 있습니다.

> 📘 **참고**
>
> 다중 사용자 편집 기능을 사용하여 사용자에 관리자 역할을 할당할 수 없습니다.

**다중 사용자를 편집하는 방법:**

1. **사용자** 탭에서 편집하고자 하는 사용자 혹은 다수의 사용자를 체크합니다.
   * 모든 사용자를 선택하려면 열 제목의 체크박스를 선택하세요.
   * 선택된 사용자 수는 검색창 오른쪽에 표시됩니다. [계정 소유자](#계정-소유자)를 선택할 수 없으며 선택된 사용자 수에 포함되지 않습니다.
2. 표 오른쪽 상단에 표시되는 버튼: **역할, 앱, 미디어 소스** 및 **지역**
   * 선택된 사용자 중 한 명 이상이 향후 앱에 대한 접근 권한을 가진 경우,**앱** 버튼은 비활성화됩니다. (아래의 [임시 역할 제한](/docs/user-management#임시-역할-제한사항)을 참조하십시오.)
3. 변경하려는 권한에 해당하는 버튼을 클릭하세요.
4. 대화 상자 또는 드롭다운 목록을 사용하여 내용을 변경할 수 있습니다.
   * 변경 내용은 선택된 모든 사용자에게 적용됩니다!
5. 편집된 사용자는 테이블에서 하이라이트 되어 표시되고, 변경 사항을 저장하면 그대로 반영되어 나타납니다. 다음 단계에서 변경 사항을 검토하고 확인 또는 취소할 수 있습니다.
6. 변경 사항을 검토합니다. **저장**을 눌러 확정하거나**취소**를 눌러 변경을 취소합니다.

> 📄 **예시**
>
> * 귀하의 계정에 30명의 사용자가 귀속되어 있습니다. 이들 중 10명이 **마케팅 – 제한됨** 역할에 할당되어 있습니다.
> * Alice, Bill, Charlie가 승진을 했습니다. 따라서 그들의 역할을**마케팅 – 제한** 에서 마케팅 역할로 변경하려고 합니다.
> * Alice는 Astounding 앱을 담당하게 될 것입니다. Bill은 Beautiful 앱을 담당하게 될 것입니다. Charlie는 Charming 앱을 담당하게 될 것입니다.
>
> **단계:**
>
> 1. 역할 필터 <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" />를 선택하면 **마케팅–제한** 역할의 사용자만 볼 수 있습니다.
> 2. Alice, Bill, Charlie의 역할을 **마케팅** 으로 변경합니다:
>    * Alice, Bill, Charlie를 체크합니다.
>    * **역할** 버튼을 클릭합니다.
>    * 드롭다운 목록에서 **마케팅**을 선택합니다.
>    * **저장**을 클릭하여 확정합니다.
>    * 변경 내용을 확정하면 **역할** 필터가 지워지고 표에 모든 사용자가 표시됩니다.
> 3. Alice, Bill, Charlie에게 적절한 앱 액세스 권한을 부여합니다.
>    * 검색 상자를 사용하여 Alice를 찾은 다음, 계정을 편집하여 Alice가 Astounding 앱에 액세스할 수 있도록 합니다.
>    * 이 단계를 반복하여 Bill과 Charlie가 각각 Beautiful 및 Charming 앱에 액세스할 수 있도록 합니다.

</Accordion>

<div id="deleting-users" />

<Accordion title="사용자 삭제하기:">

한 계정에서 여러 사용자를 한꺼번에 삭제할 수 있습니다.

> 📘 **참고**
>
> * 계정 소유자는 삭제할 수 없습니다
> * 삭제된 사용자는 복구할 수 없습니다.

<span id="to-delete-users"></span>**사용자 삭제하기:**

1. 사용자 탭에서 삭제할 사용자를 체크합니다. **검색 및 필터를 사용하여 사용자를 검색**할 수 있습니다.
2. 사용자를 선택한 후 표 오른쪽 상단에 표시되는 **삭제** 버튼을 클릭합니다.
3. 확인 창에 삭제할 사용자가 표시됩니다. **예, 삭제합니다**를 클릭하여 삭제를 확인합니다.

</Accordion>

### API를 통한 다수의 사용자 관리

일부 사용자 관리 작업은 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-management-overview">전용 API</Anchor>를 사용하여 일괄 처리할 수 있습니다:

* [여러 사용자 생성](https://dev.appsflyer.com/hc/reference/bulk-users-post)
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-delete">여러 사용자 삭제</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-get">여러 사용자의 접근 권한 세부정보 가져오기</Anchor>

API는 주요 사용자 관리 기능을 지원하며, 플랫폼과 동일한 방식으로 오류를 검증합니다.

## 역할 관리

앱스플라이어 계정의 각 사용자는 반드시 하나의 역할을 할당받아야 합니다. 역할에 따라 사용자의 액세스 범위와 수행 가능한 동작이 달라집니다. 역할별 권한은 **사용자 관리** 페이지의 [역할 탭](#roles-tab)에서 확인할 수 있습니다.

앱스플라이어 내의 역할은 [사전 정의된 역할](#사전-정의된-역할), [커스텀 역할](#커스텀-역할) 또는 [임시 역할](#임시-역할) (특수 상황에서)로 구분됩니다.

### 사전 정의된 역할

앱스플라이어에서 사전 정의된 역할은 다음과 같습니다:

* [관리자—특수한 역할](#관리자)
* 팀 매니저
* 마케팅 리드
* 마케팅
* 마케팅 – 제한됨
* 기여자
* 회계
* 보안
* 품질 보증

> 📘 **참고**
>
> 사전 정의된 역할의 경우, 각 역할의 기능 권한은 고정되어 있으며 임의로 조합하거나 변경할 수 없습니다. 다만, 사용자를 사전 정의된 다른 역할이나 커스텀 역할에 할당하여 사용자의 기능 권한을 변경할 수 있습니다([계정 소유자](#계정-소유자) 제외).

> 📄 **예시**
>
> Bill Bates에게 **팀 매니저** 역할을 할당했습니다. 해당 역할은 Bill이 **원링크 템플릿**을 관리할 수 있는 권한을 주지만 **마이 플랜** 및 **결제** 페이지에는 액세스할 수 없습니다.
>
> **질문:** Bill의 팀 매니저 역할을 유지하면서 마이 플랜과 결제 페이지에 액세스할 수 있는 권한도 부여할 수 있나요? 원링크 템플릿을 관리하는 Bill의 권한을 삭제할 수 있나요?
>
> **답변:** 아니요. Bill이 팀 매니저 역할에 할당되어 있는 동안에는 마이 플랜 및 결제 페이지에 액세스할 수 있는 권한을 줄 수 없습니다. 또한 Bill의 원링크 템플릿 관리 권한을 삭제할 수 없습니다. Bill을 사전 정의된 다른 역할에는 할당할 수 있으며, 그 경우, Bill에 부여되는 권한은 해당 역할의 정의에 따라 달라집니다. 또는, Bill에게 커스텀 역할을 할당하여 필요에 맞게 권한을 부여할 수 있습니다.

### 관리자

앱스플라이어 계정에는 **한 명 이상의 관리자**가 있을 수 있습니다. 관리자 역할은 다음의 고유한 특성을 가지고 있습니다:

#### 액세스

관리자는 **전 계정**에 다음을 포함하는 권한을 가집니다.

* 전체 기능 및 동작 수행 권한
* 기존 및 향후 추가되는 앱에 대한 권한
* 전체 미디어 소스 및 지역에 대한 권한

관리자 역할의 "전체 액세스" 특성은 변경하거나 제한할 수 없습니다.

#### 토큰 관리

관리자만이 <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">토큰 관리</Anchor>를 할 수 있습니다: API 및 서버-투-서버 토큰 생성, 이름 변경 및 제거할 수 있습니다.

#### 역할 복제

[커스텀 역할](#커스텀-역할-관리) 생성 시에 관리자 역할은 **복제할 수 없습니다**.

#### 앱스플라이어에 새로운 파트너 초대하기

관리자는 파트너 마켓플레이스를 통해 앱스플라이어와 연동되지 않은 파트너에게 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#앱스플라이어에-새로운-파트너-초대하기">초대 링크를 전송</Anchor>할 수 있습니다.

### 계정 소유자

계정이 개설될 때 생성된 사용자 (**‘계정 소유자’**)에게는 기본적으로 관리자 역할이 할당됩니다. 계정 소유자는 최초에 사용자를 추가로 생성할 수 있으며, 이후 관리 권한이 부여된 사용자는 동일한 작업을 수행할 수 있습니다.

계정 소유자는 일반 관리자(계정 소유자가 아닌)와 구별되며, 고유한 권한을 가집니다. 계정 소유자는 관리자와는 달리 삭제되거나 역할에서 제거될 수 없으며, 계정 소유자를 **[사용자 관리](/docs/user-management#사용자-관리-페이지)** 페이지에서 편집할 수 없습니다. 계정 소유자를 변경해야 하는 경우 **여기 나온 절차를** 따르십시오.

### 커스텀 역할

앱스플라이어의 사전 정의된 역할은 대부분의 상황에서 필요한 권한 조합으로 구성되어 있습니다. 따라서 대부분의 광고주들은 기존 정의된 역할을 별도로 커스텀 하여 구성할 필요를 못 느낍니다. 그럼에도 커스텀이 추가로 필요한 경우, 기존 정의된 역할을 템플릿으로 활용해 사용자 권한을 구성하면 좋습니다.

[커스텀 역할 관리](#커스텀-역할-관리)에 대해 더 알아보기.

### 임시 역할

구 버전의 사용자 관리 시스템(관리자와 팀 구성원 계정만 존재했던 버전)에 등록된 앱스플라이어 계정은, 기존 권한이 그대로 유지되어 새로운 시스템으로 이전됩니다. 이전된 사용자 대부분은 **임시 역할**로 나타납니다.

[임시 역할 관리](#managing-temp-roles)에 대해 더 알아보세요.

### API를 통해 역할 데이터 가져오기

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_roles">역할 조회 API</Anchor>를 통해 전체 역할 목록과 각 역할의 고유 속성을 검색할 수 있습니다.

## 커스텀 역할 관리

<div id="creating-custom-roles" />

<Accordion title="커스텀 역할 생성">

* **전제 조건:** 오직 [계정 소유자](#계정-소유자) 또는 [관리자 관한](#관리자)이 있는 사용자만 커스텀 역할을 생성할 수 있습니다.

**커스텀 역할 생성 방법:**

1. **역할** 탭의 왼쪽 패널 검색창 아래에서 **+ 새 커스텀 역할**을 클릭하세요.
2. **역할 이름:** 생성하는 새 역할의 이름을 입력합니다.
   * **참고:** 커스텀 역할을 저장한 후에는 역할 이름을 편집할 수 없습니다.
   * **권장 사항:** 이름은 맡은 역할이 잘 드러내고 쉽게 식별 가능하도록 만들어주세요.
3. **역할 템플릿:** 커스텀 하려는 역할과 가장 유사한 권한을 가진 사전 정의된 역할을 템플릿으로 활용하세요.
4. 선택한 역할 템플릿을 가져와, 새로 만들려는 역할에 요구되는 조건에 따라 커스텀 하세요. 편집 가능한 모든 권한의 권한 수준이 버튼으로 표시됩니다. 새 커스텀 역할에 대한 권한 수준을 변경하려면 이 버튼을 클릭합니다. (전체 권한 목록을 보려면 아래로 스크롤해야 합니다.)
   * **참고:** 버튼으로 표시되지 않는 권한은 현재 편집할 수 없습니다.
5. 모든 관련 권한에 대한 권한 수준을 설정한 후 **역할 저장**을 클릭하십시오.  
   새 커스텀 역할은 왼쪽 패널에 표시되며 새 사용자를 생성하거나 기존 사용자를 편집할 때 할당될 수 있습니다.

</Accordion>

<div id="editing-custom-roles" />

<Accordion title="커스텀 역할 편집하기">

**커스텀 역할 편집 방법:**

1. **역할** 탭의 왼쪽 패널에서 편집하려는 커스텀 역할의 이름을 클릭합니다.
2. 페이지 오른쪽 상단 모서리에서 **편집** 아이콘 <Image alt="edit-icon.jpg" src="https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg" width="25px" />을 클릭하십시오. 오른쪽 패널이 다르게 표시되며, 역할 권한 설정을 편집할 수 있습니다.
   * **참고:** 역할 이름은 편집할 수 없습니다. 변경하려면 역할을 삭제하고 다른 이름으로 새 역할을 만들어야 합니다.
3. 편집 가능한 모든 권한의 권한 수준이 버튼으로 표시됩니다. 새 커스텀 역할에 대한 권한 수준을 변경하려면 이 버튼을 클릭합니다. (전체 권한 목록을 보려면 아래로 스크롤해야 합니다.)
4. 선택 사항을 확인하고 **역할 저장** 버튼을 클릭합니다.
5. 모든 신규 및 기존 사용자에 대해 역할 권한 수준이 변경됩니다.

> 🚧 **중요!**
>
> 커스텀 역할에 대한 모든 변경 사항은 해당 역할을 할당받은 **모든 사용자**에게 자동으로 적용됩니다.

</Accordion>

<div id="deleting-custom-roles" />

<Accordion title="커스텀 역할 삭제">

**커스텀 역할 삭제 방법:**

1. **역할** 탭의 왼쪽 패널에서 삭제하려는 커스텀 역할의 이름을 클릭합니다.
2. 페이지 오른쪽 상단 모서리에서 **삭제** 아이콘 <Image alt="delete-icon.jpg" src="https://files.readme.io/87f206e21926af0836690be064a5af7cb3bce0007f0fc62301b2925701b1d9f9-31780971797265.jpg" width="24px" />을 클릭하십시오.
3. 역할 삭제 여부를 확정합니다.
   * 커스텀 역할은 할당된 사용자가 없는 경우에만 삭제할 수 있습니다. 현재 커스텀 역할에 할당된 사용자가 있는 경우, 해당 사용자를 다른 역할에 할당한 후 커스텀 역할을 삭제합니다.

</Accordion>

## 특수 상황 및 추가 절차

<div id="managing-temp-roles" />

<Accordion title="임시 역할 관리">

구 버전 사용자 관리 시스템을 사용하던 사용자의 권한이 바뀌지 않도록 임시 역할이 부여되어 새로운 시스템으로 이전됩니다.

* 동일한 권한을 가진 사용자에게 동일한 임시 역할이 할당되었습니다.
* [역할 탭](/docs/user-management#roles-tab)의 기능을 사용하여 각 임시 역할의 권한과 현재 해당 역할을 부여받은 사용자를 검색할 수 있습니다.

#### 임시 역할 제한사항

임시 역할은 이전 버전의 사용자 관리 시스템에서 새로운 시스템으로 원활하게 전환할 수 있도록 특별히 설계되었습니다. 따라서 다음과 같은 제한된 상황에서만 사용됩니다.

* 임시 역할을 다른 사용자(새 사용자와 기존 사용자)에게 할당할 수 없습니다.
* 임시 역할을 할당받은 사용자에게는 다른 임시 역할을 할당할 수 없습니다(해당 사용자가 액세스할 수 있는 앱, 미디어 소스 및 지역 변경은 가능).
  * 사용자가 임시 역할을 맡는 동안에는 향후 추가되는 앱에 대한 사용자 액세스 변경이 **불가**합니다.
* 임시 역할을 맡은 사용자에 사전 정의된 역할을 할당하면 이전에 할당된 임시 역할(또는 다른 임시 역할)로 되돌릴 수 없습니다.
* 마지막 임시 역할 사용자가 삭제되면 임시 역할이 계정에 더 이상 표시되지 않습니다.

> 📄 **예시**
>
> 귀하의 계정은 이전 버전의 사용자 관리 시스템을 사용했습니다. 귀하의 계정이 새로운 시스템으로 넘어갈 당시 있었던 사용자는 Diana와 Edward입니다. Diana는 현재 임시 역할 1을, Edward는 임시 역할 2를 맡고 있습니다.
>
> * 새 직원 Fiona를 고용합니다. Fiona에게 [사전 정의된 역할](/docs/user-management#사전-정의된-역할) 중 하나를 할당할 수 있습니다. 그러나 Fiona에게 임시 역할 1 또는 2를 할당할 수 없습니다.
> * Diana는 임시 역할 1에서 임시 역할 2로 이동할 수 없습니다. 하지만 Diana에게 사전 정의된 역할을 할당할 수 있습니다. 필요에 따라 앱, 미디어 소스 및 지역에 대한 Diana의 액세스 권한을 변경할 수 있습니다.
> * Diana를 임시 역할 1에서 회계 역할로 옮기면, 임시 역할 1로 다시 복귀할 수 없습니다.
> * Diana가 회계 역할로 옮겨가면서 임시 역할 1 사용자가 한 명도 남지 않게 되었다면 임시 역할 1은 더 이상 계정에 나타나지 않습니다.

</Accordion>

<div id="dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access" />

<Accordion title="미디어 소스/지역 액세스가 제한된 사용자를 위한 대시보드 및 기능">

다음 앱스플라이어 대시보드는 특정 미디어 소스 및 지역에 대한 액세스가 제한된 사용자는 **사용할 수 없습니다**.

* SKAN 개요
* SKAN 컨버전 스튜디오
* Protect360
* 잔존율
* 사람 중심 어트리뷰션
* 성과증분측정

더불어 해당 사용자는 다음 앱스플라이어 기능을 **사용할 수 없습니다**.

* 피봇
* 원링크
* 유효성 검증 규칙
* 시청자 그룹 ( 미디어 소스 제한이 있는 사용자는 이용할 수 없습니다. 지역 제한이 있는 사용자는 "국가" 필터가 포함된 오디언스 에만 액세스 할 수 있으며, 액세스 권한이 있는 국가에 대해서만 액세스 할 수 있습니다.)
* SDK 정보
* 광고 지출 데이터 수집
* Cost ETL

</Accordion>

<div id="changing-the-account-owner" />

<Accordion title="계정 소유자 변경">

모든 관리자는 계정 소유자와 동일한 권한을 가지므로 일반적으로 계정 소유자를 변경할 필요는 없습니다. 그럼에도 계정 소유자를 변경해야 하는 경우에는 다음 단계를 수행하십시오.

> 🚧 **중요!**
>
> 계정 소유자 변경은 다음 단계에 따라 수동으로 완료해야 합니다. **사용자 관리** 페이지에서는 수행할 수 없습니다.

#### #1 – 팀원 중 한 명에게 관리자 역할을 부여합니다.

계정 소유자 변경 요청은 관리자 권한을 가진 사용자에게만 요청할 수 있습니다. 따라서 다음과 같이 하는 것이 좋습니다.

* 모든 단계를 완료할 수 있는 팀원에게 **관리자** 역할을 부여하세요.
* 사용자는 계정을 활성화해야 합니다(즉, 최소 한 번 로그인해야 합니다).

#### #1–이메일 요청 보내기

관리자 권한을 가진 사용자는 **현재 계정 소유자의 이메일 주소로** 앱스플라이어 에 이메일 요청을 보내야 합니다.

* 이 주소가 앱스플라이어 계정에 표시되는 현재 계정 소유자의 이메일 주소인지 확인합니다.
* 현재 계정 소유자가 회사에 소속되어 있지 않다면 IT 팀에 해당 주소에서 이메일을 보낼 수 있도록 요청하십시오.

요청 사항에 다음 정보를 포함하십시오.

| 받는 사람: | 앱스플라이어 CSM 또는 hello@appsflyer.com |
| --- | --- |
| 참조: | 새 계정 소유자의 이메일 |
| 제목: | `{account name}`에 대한 계정 소유자 변경 요청 |
| 본문: | 새 계정 소유자의 이름과 직함을 포함한 짧은 메시지 |

이 샘플 이메일을 참고하세요.

![account_owner_change_email.png](https://files.readme.io/eb10736386a7a8cfc274979a3aa933e23288c74d1b26c0f06d72005ceebafe06-31780969048081.png)

#### #2–다음 단계

변경이 완료되면 귀하는 앱스플라이어로부터 이메일 알림을 받게 됩니다.

* 이전 계정 소유자가 앱스플라이어 계정을 계속 사용하도록 하려면 해당 계정에 대한 [새 사용자 생성](/docs/user-management#creating-users) 후 새 역할을 할당하십시오.
* 토큰 v2를 사용하는 API는 계정 소유자 변경에 영향을 받지 않습니다. <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">토큰 관리에 대해 더 알아보세요.</Anchor>

</Accordion>

<div id="troubleshooting-can-t-create-this-user" />

<Accordion title="문제해결: 이 사용자를 생성할 수 없습니다.">

새 사용자의 이메일 주소를 입력할 때 *이 사용자를 생성할 수 없음*이라는 오류 메시지가 표시되면 일반적으로 해당 이메일이 앱스플라이어 사용자(계정 또는 다른 사용자)와 이미 연결되어 있다는 의미입니다. 사용자의 상황을 고려하여 적절한 절차를 수행하십시오.

사용자가 귀하의 계정에 포함된 경우:

* 사용자가 계정을 활성화했는지 확인하십시오. 활성화하지 않았다면 필요에 따라 [초대장을 다시 보내십시오](/docs/user-management#resending-a-user-invitation).
* 사용자가 계정을 활성화한 경우 사용자와 연결된 이메일 주소를 사용하여 다시 로그인하도록 요청합니다. 필요한 경우 **암호 분실** 절차를 따르도록 안내합니다.

사용자의 이메일이 다른 계정에서 사용되거나 사용자의 이메일이 사용되는 계정을 알 수 없는 경우 다음 옵션 중 하나를 선택합니다.

* 다른 계정에서 해당 사용자를 삭제하고 사용자를 귀하의 계정에 추가합니다(귀하 혹은 사용자가 다른 계정의 권한을 가지고 있는 경우에만 가능)
* 다른 이메일 주소를 사용하여 계정에 추가합니다. 실제로 이메일 전송이 가능한 유효한 이메일 주소여야 합니다.
* 또는 고객 성공 관리자(CSM)에게 문의하거나 [hello@appsflyer.com](mailto:hello@appsflyer.com) 고객 인게이지먼트 팀으로 메일 주세요.

</Accordion>

<div id="resending-a-user-invitation" />

<Accordion title="사용자 초대 재전송">

새 사용자가 [계정 활성화 초대](#사용자-활성화)를 받지 못했거나 48시간 이내에 활성화되지 않은 경우 다음과 같이 이메일을 재발송할 수 있습니다.

1. **사용자** 탭에서 사용자 행의 맨 오른쪽에 있는 **조치** 버튼 <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />을 클릭합니다.
   * 사용자에게 아직 계정을 활성화하지 않았음을 나타내는 봉투 아이콘 ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png)이 계속 표시됩니다.
2. 메뉴에서 **이메일 초대 재전송**을 선택합니다.

</Accordion>

<div id="resetting-twofactor-authentication-2fa" />

<Accordion title="사용자의 2단계 인증(2FA) 재설정">

귀하의 계정이 2FA를 사용하는 경우, 사용자의 2FA를 재설정해야 하는 경우가 있을 수 있습니다. 다음을 수행하세요.

1. **사용자** 탭에서 사용자 행의 맨 오른쪽에 있는 **조치** 버튼 <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />을 클릭합니다.
2. 메뉴에서 **2FA 재설정**을 선택합니다.

**참고:** 관리자는 본인 또는 [계정 소유자](#계정-소유자) 이외의 다른 관리자의 2FA를 재설정할 수 있습니다. 계정 소유자의 2FA를 재설정하려면 앱스플라이어 지원팀에 문의하십시오.

</Accordion>

<div data-zendesk-anchors="background=%EA%B0%9C%EC%9A%94 h_01H9Q9007QP8YMPDVZ57N4M1HD=%EA%B0%9C%EC%9A%94 user-management-page=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B4%80%EB%A6%AC-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01H9Q9007QW1RD3MTTV01Q8QRE=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B4%80%EB%A6%AC-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01J6W88SQ45MA3AZ29K3WMW9PV=users-tab h_01J6W88SQ5B16Q897YMJ7ZNMQX=roles-tab managing-users=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B4%80%EB%A6%AC%ED%95%98%EA%B8%B0 h_01H9Q9007QYSJZYZMP0C8NA98G=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B4%80%EB%A6%AC%ED%95%98%EA%B8%B0 h_01H9Q9007QH3ME2P8PHC9DJBZV=creating-users user-details=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A0%95%EB%B3%B4 h_01HMP4EYM562HFSP80MQQ82B47=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A0%95%EB%B3%B4 h_01H9Q9007Q6SK4391P8C3A147N=%EC%A4%91%EC%9A%94 role=%EC%97%AD%ED%95%A0 h_01HMP4Q56XP10343YFW17VX00W=%EC%97%AD%ED%95%A0 app-access=%EC%95%B1-%EC%95%A1%EC%84%B8%EC%8A%A4 h_01HMP4RDXVRM3Z0WDCJD3P2W8S=%EC%95%B1-%EC%95%A1%EC%84%B8%EC%8A%A4 data-access=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%95%A1%EC%84%B8%EC%8A%A4 h_01HMP4SW7RMESGDFNP1KFN7641=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%95%A1%EC%84%B8%EC%8A%A4 h_01HR6VBJHTZM48493B29FCWQT8=%EC%B0%B8%EA%B3%A0 media-sources=%EB%AF%B8%EB%94%94%EC%96%B4-%EC%86%8C%EC%8A%A4 h_01HRPRS4BHX2AMR9W4FNGE0N1P=%EB%AF%B8%EB%94%94%EC%96%B4-%EC%86%8C%EC%8A%A4 01HRPRSF0F8ENJ9ZAE1ZDTMAMB=%EC%B0%B8%EA%B3%A0-1 geos=%EC%A7%80%EC%97%AD h_01HRPRVXYFX4P2ZG0H5HPNF2AG=%EC%A7%80%EC%97%AD user-activation=%EC%82%AC%EC%9A%A9%EC%9E%90-%ED%99%9C%EC%84%B1%ED%99%94 h_01HFRCWNR8T5J990TV68K6B45T=%EC%82%AC%EC%9A%A9%EC%9E%90-%ED%99%9C%EC%84%B1%ED%99%94 h_01HFRFRQXD1RD66EBRQH0T7Q78=%EC%B0%B8%EA%B3%A0-2 01HFRF6SENRY51A4ZAQJTMTDA3=multiple-accounts log-in-to-multiple-accounts=%EC%97%AC%EB%9F%AC-%EA%B3%84%EC%A0%95%EC%97%90-%EB%A1%9C%EA%B7%B8%EC%9D%B8 h_01J2GN6ZA29SFC12HR4ZVBDFDT=%EC%97%AC%EB%9F%AC-%EA%B3%84%EC%A0%95%EC%97%90-%EB%A1%9C%EA%B7%B8%EC%9D%B8 supported-accounts-and-users=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-%EA%B3%84%EC%A0%95-%EB%B0%8F-%EC%82%AC%EC%9A%A9%EC%9E%90 h_01H9Z7XXE0CKRSE191ZN017MGE=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-%EA%B3%84%EC%A0%95-%EB%B0%8F-%EC%82%AC%EC%9A%A9%EC%9E%90 limitations-on-adding-users-to-multiple-accounts=%EC%97%AC%EB%9F%AC-%EA%B3%84%EC%A0%95%EC%97%90-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%B6%94%EA%B0%80-%EC%8B%9C-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD 01J2GMV7ZYV5G0Q6C18RRY1TY0=%EC%97%AC%EB%9F%AC-%EA%B3%84%EC%A0%95%EC%97%90-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%B6%94%EA%B0%80-%EC%8B%9C-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD add-users-to-multiple-accounts=%EC%97%AC%EB%9F%AC-%EA%B3%84%EC%A0%95%EC%97%90-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%B6%94%EA%B0%80 h_01H9G1MP3Z7VCQQ8ZSQDGSWPC3=%EC%97%AC%EB%9F%AC-%EA%B3%84%EC%A0%95%EC%97%90-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%B6%94%EA%B0%80 h_01H9Q9007RTMXVRMR4RM6J80CW=editing-users individual-editing=%EA%B0%9C%EB%B3%84-%ED%8E%B8%EC%A7%91 h_01H9Q9007R3QW4AYRJBTF0X7B9=%EA%B0%9C%EB%B3%84-%ED%8E%B8%EC%A7%91 multiuser-editing=%EB%8B%A4%EC%A4%91-%EC%82%AC%EC%9A%A9%EC%9E%90-%ED%8E%B8%EC%A7%91 h_01H9Q9007R4JQPKQS2HVB251GH=%EB%8B%A4%EC%A4%91-%EC%82%AC%EC%9A%A9%EC%9E%90-%ED%8E%B8%EC%A7%91 h_01H9Q9007R9M9YDMJ2YYNZDW3D=%EC%B0%B8%EA%B3%A0-3 h_01H9Q9007RAFXB899YK6CADD9R=%EC%98%88%EC%8B%9C h_01H9Q9007RF8QKS7YBZ1GRXVCF=deleting-users h_01HGTR4NEBYJZTW4BA5V9JJX5X=%EC%B0%B8%EA%B3%A0-4 h_01HGTK2664A0R2RBJM37EYWNZG=to-delete-users manage-users-in-bulk-via-api=api%EB%A5%BC-%ED%86%B5%ED%95%9C-%EB%8B%A4%EC%88%98%EC%9D%98-%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B4%80%EB%A6%AC h_01HYASD07FG0HGX22FTHEQ9APP=api%EB%A5%BC-%ED%86%B5%ED%95%9C-%EB%8B%A4%EC%88%98%EC%9D%98-%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B4%80%EB%A6%AC more-about-roles=%EC%97%AD%ED%95%A0-%EA%B4%80%EB%A6%AC h_01H9Q9007Q8CMR2RD6E4KN26YE=%EC%97%AD%ED%95%A0-%EA%B4%80%EB%A6%AC predefined-roles=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%97%AD%ED%95%A0 h_01H9Q9007Q28D43B6JRP71NDQM=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%97%AD%ED%95%A0 h_01J6VZ7ANV3JHJZ5EVBF1BY585=%EC%B0%B8%EA%B3%A0-5 h_01H9Q9007QXSGG375PR2SCS7QS=%EC%98%88%EC%8B%9C-1 admin%E2%80%94a-special-role=%EA%B4%80%EB%A6%AC%EC%9E%90 h_01H9Q9007Q4A6KETAAGAWEPQQ9=%EA%B4%80%EB%A6%AC%EC%9E%90 access=%EC%95%A1%EC%84%B8%EC%8A%A4 h_01HF8N2Z8ZP3HV06XJPMQ19DTK=%EC%95%A1%EC%84%B8%EC%8A%A4 manage-tokens=%ED%86%A0%ED%81%B0-%EA%B4%80%EB%A6%AC h_01HV1F5S0FE083B73P8MEYX4FM=%ED%86%A0%ED%81%B0-%EA%B4%80%EB%A6%AC role-duplication=%EC%97%AD%ED%95%A0-%EB%B3%B5%EC%A0%9C h_01HF8N6DKWYKMBE35QKKB55KEM=%EC%97%AD%ED%95%A0-%EB%B3%B5%EC%A0%9C invite-new-partners-to-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90-%EC%83%88%EB%A1%9C%EC%9A%B4-%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%B4%88%EB%8C%80%ED%95%98%EA%B8%B0 h_01HVK8EB3SMC09VD8TJND9YWCD=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90-%EC%83%88%EB%A1%9C%EC%9A%B4-%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%B4%88%EB%8C%80%ED%95%98%EA%B8%B0 account-owner=%EA%B3%84%EC%A0%95-%EC%86%8C%EC%9C%A0%EC%9E%90 h_01HF8N69VYE3ZJVFW1ENC0XA62=%EA%B3%84%EC%A0%95-%EC%86%8C%EC%9C%A0%EC%9E%90 custom-roles=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%97%AD%ED%95%A0 h_01H9Q9007QZ7F2TX8B9D1TNYPN=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%97%AD%ED%95%A0 temp-roles=%EC%9E%84%EC%8B%9C-%EC%97%AD%ED%95%A0 h_01H9Q9007QE8YT1DNRPNTFQWYH=%EC%9E%84%EC%8B%9C-%EC%97%AD%ED%95%A0 get-roles-data-via-api=api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%97%AD%ED%95%A0-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 h_01J6VZ2XP6HM6NJ2TB5DJXD6SA=api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%97%AD%ED%95%A0-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 managing-custom-roles=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%97%AD%ED%95%A0-%EA%B4%80%EB%A6%AC h_01H9Q9007RQHHNHZ3M38E88YPW=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%97%AD%ED%95%A0-%EA%B4%80%EB%A6%AC h_01H9Q9007RYZD19CFNSM60EARZ=creating-custom-roles h_01H9Q9007R6E6JGD8BC2WY8G3G=editing-custom-roles h_01H9Q9007RANMZP4T6S8R6WA1B=%EC%A4%91%EC%9A%94-1 h_01H9Q9007R16190B6RB884FY61=deleting-custom-roles special-situations-and-additional-procedures=%ED%8A%B9%EC%88%98-%EC%83%81%ED%99%A9-%EB%B0%8F-%EC%B6%94%EA%B0%80-%EC%A0%88%EC%B0%A8 h_01H9Q9007RSWFVAZQ5DNVNN7T2=%ED%8A%B9%EC%88%98-%EC%83%81%ED%99%A9-%EB%B0%8F-%EC%B6%94%EA%B0%80-%EC%A0%88%EC%B0%A8 h_01H9Q9007RNZ28128XDB76ZVZC=managing-temp-roles temp-role-limitations=%EC%9E%84%EC%8B%9C-%EC%97%AD%ED%95%A0-%EC%A0%9C%ED%95%9C%EC%82%AC%ED%95%AD h_01H9Q9007RJ0CQRGEYNEQJ2QR5=%EC%9E%84%EC%8B%9C-%EC%97%AD%ED%95%A0-%EC%A0%9C%ED%95%9C%EC%82%AC%ED%95%AD h_01H9Q9007RHBYD2B6PHQRD7TWV=%EC%98%88%EC%8B%9C-2 h_01H9Q9007RRY6QERXQ0C4FSYCN=dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access h_01H9Q9007R221KXA7DFTXJY0PE=changing-the-account-owner h_01H9Q9007RR4M8V599A19B2M0F=%EC%A4%91%EC%9A%94-2 1%E2%80%93send-an-email-request=1--%ED%8C%80%EC%9B%90-%EC%A4%91-%ED%95%9C-%EB%AA%85%EC%97%90%EA%B2%8C-%EA%B4%80%EB%A6%AC%EC%9E%90-%EC%97%AD%ED%95%A0%EC%9D%84-%EB%B6%80%EC%97%AC%ED%95%A9%EB%8B%88%EB%8B%A4 h_01H9Q9007RSA5406WXCB1E4JRK=1--%ED%8C%80%EC%9B%90-%EC%A4%91-%ED%95%9C-%EB%AA%85%EC%97%90%EA%B2%8C-%EA%B4%80%EB%A6%AC%EC%9E%90-%EC%97%AD%ED%95%A0%EC%9D%84-%EB%B6%80%EC%97%AC%ED%95%A9%EB%8B%88%EB%8B%A4 h_01K5P1G80QACK6YMKX4AGJA5ZK=1%EC%9D%B4%EB%A9%94%EC%9D%BC-%EC%9A%94%EC%B2%AD-%EB%B3%B4%EB%82%B4%EA%B8%B0 2%E2%80%93next-steps=2%EB%8B%A4%EC%9D%8C-%EB%8B%A8%EA%B3%84 h_01H9Q9007RZ2X9RAY8067SZETF=2%EB%8B%A4%EC%9D%8C-%EB%8B%A8%EA%B3%84 troubleshooting-can%E2%80%99t-create-this-user=troubleshooting-can-t-create-this-user h_01H9Q9007RR4VYEPGT90MEHV3T=troubleshooting-can-t-create-this-user h_01H9Q9007R11BQWQZC66X5FV0N=resending-a-user-invitation h_01H9Q9007R72FAH89XW58MWCXT=resetting-twofactor-authentication-2fa" />
