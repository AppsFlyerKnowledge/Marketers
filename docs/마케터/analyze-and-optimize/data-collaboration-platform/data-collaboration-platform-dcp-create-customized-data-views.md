---
title: 데이터 협업 플랫폼(DCP) - 맞춤형 데이터 뷰 생성
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-11-22T12:57:55Z'
  edited_at: '2026-10-14T10:33:50Z'
  id: 30296051098897
  locale: ko
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ko/articles/30296051098897
---
> **한눈에 보기:** 변환 및 집계 기능과 데이터 필터링 도구를 사용하여 데이터 소스에서 사용자정의 데이터 뷰를 만듭니다. 변경된 데이터 샘플을 미리 볼 수 있으며, 변경 상황을 반영할 수 있습니다.

<div id="about-data-views" />

## 개요

데이터 뷰 빌더를 사용하면 원래의 데이터 세트를 수정하지 않고도 사용자정의된 데이터 소스 버전을 만들 수 있습니다. SQL 지식, 데이터 전문가 또는 데이터 엔지니어가 필요하지 않으므로 데이터를 미리 검토하고 나중에 조정하면서 데이터를 수정, 수정 및 요약하는 기능을 수행할 수 있습니다.

<div id="data-view-functions" />

### 데이터 보기 함수 (Data view functions)

Data View Builder 도구에는 다음 기능이 있습니다.

* **전환:** 데이터의 형식, 구조 또는 값을 수정하여 분석에 대비합니다. 이렇게 하면 기존 데이터에서 인사이트를 통합할 수 있는 새로운 열이 생성됩니다.
* 집약 Sum, Average, Count, Min, Max과 같은 함수를 사용하여 요약 또는 그룹을 생성하기 위해 여러 개의 데이터 레코드를 결합합니다.
* 필터 시간 범위, 카테고리 또는 사용자정의 파라미터와 같은 선택된 속성을 적용하여 특정 관련 정보에 초점을 맞추어 데이터를 좁힙니다.

<div id="the-data-view-builder" />

## 데이터 뷰 빌더

<Image align="center" alt="" src="https://files.readme.io/33957c796bf0e45fa01a7c079ef0a9ae4ad988d153b38a2ef7e94a12beabd53b-51912738864145.png" />

Data View Builder 페이지는 두 가지 섹션이 있습니다.

### 메인 섹션

이 섹션에서는 다음 세 가지 주요 구성 요소로 구성된 데이터 보기 생성 요소를 찾을 수 있습니다.

* 세부 정보 데이터 보기의 이름 및 설명
* **데이터 맞춤화:** 데이터 사용자 정의를 위한 기능 및 필터 적용
* Fields 보기 불필요한 필드를 제거하거나 필드 유형을 조정하여 데이터 보기 구조를 선택합니다.

### 측면 패널

페이지 오른쪽의 측면 패널은 원래의 소스에서 하나, 생성된 데이터 보기에서 하나의 두 개의 데이터 세트를 표시합니다. 각각의 세트에는 테이블 이름 및 설명, 필드 수 및 행 수와 다섯 개의 데이터 행이 포함된 샘플 테이블이 포함됩니다. 기능과 필터가 데이터 뷰에 적용되면 측면 패널이 이러한 변경 사항을 반영하여 수정하는 동안 데이터를 검증하고 원래 버전과 비교할 수 있습니다.

<div id="create-a-data-view" />

## 데이터 보기 설정

앱스플라이어에서 데이터 뷰를 생성하고 커스터마이징하는 방법을 알아보세요. 원래의 데이터셋을 수정하지 않고도 데이터를 원래의 오디언스에 맞게 연관지도록 데이터를 변환, 통합, 필터링할 수 있습니다.

<div id="set-the-data-view-general-details" />

<Accordion title="데이터 보기 일반 세부 사항 설정">

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **데이터 클린룸**을 선택합니다.
2. **소스** 탭에서 데이터 보기 생성에 사용할 소스 위로 마우스 오버하고 행 끝에 있는 <Image alt="ellipsis.png" src="https://files.readme.io/d3e33f1864edb1d9d2f8e18c9c7887454018a67e9f7fed054e7134231dba60a2-30296671836433.png" width="0.6%" /> (메뉴 아이콘) 을 클릭합니다.
3. **데이터 보기 만들기**를 선택합니다. **새 데이터 보기** 페이지로 이동합니다.
4. 다음 필드를 설정합니다.
   * 데이터 조회 이름 데이터 보기의 이름을 입력합니다. 식별에 도움이 되는 고유 이름일 수 있습니다. 아래의 [명명 요구 사항 및 지침](#이름-지정-요구-사항-및-지침)을 참조하십시오.
   * **설명:** 설명을 입력하세요. 이것은 **소스** 탭의 데이터 보기 이름 위에 마우스 오버할 때 도구 설명으로 나타납니다. 주요 목표와 수행된 데이터 조작을 강조하는 것이 좋습니다.
   * **표 추가:** 보기의 구조와 데이터를 가장 잘 나타내는 레이블을 선택할 수 있습니다.

<div id="h_01K4SDE8H7R9YZYXMRVXV5GZSV" />

<div id="naming-requirements-and-guidelines" />

#### 이름 지정 요구 사항 및 지침

* 이름이 계정의 다른 모든 소스와 하위 소스 중에 고유한 이름인지 확인하십시오. 그렇지 않으면 저장할 수 없습니다.
* 클라우드 연동의 경우, 이름이 파일 이름과 일치할 필요가 없습니다.
* 이름 요구사항:
  * 길이: 2&#126;80자
  * 유효한 문자:
    * 문자 (A-Z, a-z)
    * 숫자 *(0-9)*, 이름의 첫 문자가 될 수 없습니다
  * 유효하지 않은 문자:
    * 공백
    * 밑줄,
    * 기타 모든 기호 또는 특수 문자

</Accordion>

<div id="transform-aggregate-and-filter-data" />

<Accordion title="데이터 사용자 정의">

아래 도구를 적용하여 데이터 사용자 정의:

* **전환** 및 **집약** 함수: 사용자정의 필드를 작성하는 데 사용하십시오. 새로 생성된 각 필드는 데이터 보기에서 열로 추가됩니다.
* 필터 선택한 속성을 사용하여 데이터를 좁히고 관련 정보를 집중하세요.

프로세스 중에 수정된 데이터 샘플을 [측면 패널](#측면-패널)에서 미리 볼 수 있습니다.

> 📘 **참고**
>
> * 필터는 언제든지 추가할 수 있지만, 집계 함수가 있는 경우 필터는 해당 함수를 실행한 후에 데이터에 적용됩니다.
> * 날짜 유형 필드(열)에서 함수 또는 필터를 사용할 때, 날짜 값이 선택한 함수에 특정한 지원되는 날짜 형식과 일치하는지 확인하십시오. 제공된 옵션 중 어떤 옵션이든 차이가 나면 최적의 옵션이 아닐 수 있습니다.

<div id="transform-and-aggregate-your-data" />

<Accordion title="데이터 변환 및 집약">

**전환 또는 통합 필드를 만드려면:**

1. **전환 및 집계** 항목에서 **필드 생성** 을 클릭합니다.
2. **전환** 또는 **집계** 탭을 선택하고 + **새로 만들 필드**를 클릭합니다.
3. 필드의 이름을 입력합니다.
4. **임의 설정** 을 클릭하고 [임의 목록](#list-of-functions-and-use-case-examples)에서 함수를 선택합니다. 필요한 정보를 입력하는 관련 필드는 자동으로 추가됩니다.
5. **집약** 필드의 경우:

   [선택 사항] 함수가 실행되기 전에 집계가 이루어지는 조건을 적용하려면 **+ Condition** 을 클릭합니다.

   **참고:**

   이 조건은 **모든 집계 함수**에 적용됩니다.
6. [선택 사항] **+ 새 필드를** 클릭하여 더 많은 **변환** 또는 **집약** 필드를 추가합니다. 필요에 따라 여러 개를 추가할 수 있습니다.

새 필드가 생성되면:

* [전환 & 집계](#transform-aggregate-and-filter-data) 섹션에 나타납니다.
* 모든 함수 및 필터에서 사용할 수 있는 필드 목록에 포함됩니다.
* [필드 선택](#select-fields) 섹션의 필드 목록에 포함됩니다.
* "재개" 아이콘을 클릭하면 [면 패널](#측면-패널)에 반영되며 샘플 표와 열 또는 행 수를 업데이트합니다.

</Accordion>

<div id="filter-your-data" />

<Accordion title="데이터 필터">

선택한 속성을 사용하여 데이터를 좁히도록 필터를 적용하여 특정한 관련 정보에 집중할 수 있습니다.

> 📘 **참고**
>
> 통합 함수가 추가되거나 업데이트되면 필터는 실행한 후에만 데이터에 적용됩니다.

필터 적용

1. **필터** 아래에서 **데이터 필터링** 을 클릭합니다.
2. **열 선택** 을 클릭하고 필터할 열을 선택합니다.
3. 클릭 **연산자** > **일치** 또는 **일치하지 않음**.
4. 값 입력
5. [선택 사항] 필터에 조건을 추가하려면 **+ 조건**을 클릭합니다.

   <div id="group-by" />

   <div id="note" />

   > 📘 **참고**
   >
   > * AND 및 OR 작업을 사용하여 필요에 따라 많은 조건을 추가할 수 있습니다.
   > * 다중 조건은 표준 논리 순서에 따라 처리되며 AND 작업이 OR보다 우선 적용됩니다.


</Accordion>

<div id="zd-list-of-functions-and-use-case-examples" />

<div id="list-of-functions-and-use-case-examples" />

<Accordion title="함수 목록 및 사용 사례 예시">

<div id="transformation-functions" />

#### **전환 함수**

* **IF:** 특정 조건이 true인지 false인지 여부에 따라 다양한 조치를 수행하는 조건적 문구.
* CONCAT 두 문자열의 연결
* CONST CONCAT 함수의 파라미터를 리턴합니다.
* LEAST 두 개의 값 중 가장 낮은 값을 리턴합니다.
* **가장 좋음:** 두 개의 값 중 가장 높은 값을 리턴합니다.

<div id="example-transformation" />

#### **예: 전환**

협업하는 다른 브랜드의 제품을 가리키면서 공동 작업자로부터 구매한 제품을 표시하고 싶습니다.

<Image align="center" alt="" src="https://files.readme.io/f27f134083694e7453df113960a240b5dfa92c921b0288995bbd432a0c08c01c-51912738865041.png" />

<div id="aggregate-functions" />

#### **통합 함수**

* 횟수 행 수를 리턴합니다.
* 합계 (SUM) 모든 값의 합계를 리턴합니다.
* AVG 전체 값의 평균을 리턴합니다.
* MIN 두개의 숫자의 최소 값을 리턴합니다.
* MAX 두개의 숫자의 최대값을 리턴합니다.

<div id="example-aggregation" />

#### **예: 집약**

사용자당 총 구매 횟수를 계산하고 총 구매 가격을 합산할 수 있습니다.

<Image align="center" alt="" src="https://files.readme.io/ed5c27acd42890958753ed77080f95be39a32c3d4560154804831fc7d809d6d1-51912723197713.png" />

<div id="example-aggregation-with-a-condition" />

#### 예시: 조건이 있는 집약

독일에 거주하고 P&G 제품을 구매한 유저의 최근 구매에 대한 데이터를 원합니다.

<Image align="center" alt="" src="https://files.readme.io/e88bda9e19c4dbfa3bd479c2bf622c11c5d0259bfdff454a1ac49ff891b58a17-51912738874001.png" />

</Accordion>

</Accordion>

<div id="select-fields" />

<Accordion title="Fields 보기">

데이터 뷰 구조에는 원래의 데이터 소스의 필드와 데이터 뷰 빌더 내에서 생성된 사용자정의 데이터 필드가 포함됩니다. 여기에서 (식별자 필드 제외) 필드를 제거하거나 순서를 변경할 수 있습니다.

<div id="transactional-data-sources" />

<div id="common-use-cases" />

<div id="h_01JVSEG13462Z4XXD1NE8GW1HE" />

<div id="note-3" />

<div id="use-cases" />

<div id="note-2" />

<div id="note-1" />

> 📘 **참고**
>
> * 통합 함수가 적용될 때 필드를 제거하면 데이터 세분성이 감소하여 데이터 보기 결과에 영향을 미칠 수 있습니다.
> * 집계 함수가 필드에 적용되면 해당 필드는 리스토어 옵션 없이 목록에서 제거되고 **제거됨** 섹션 아래에 배치됩니다. 이는 함수가 해당 필드의 데이터를 결합했기 때문입니다.
> * 새 데이터 뷰를 저장한 후에는 삭제된 모든 필드가 더 이상 보이지 않으며 복원할 수 없습니다.
> * 필드 유형은 원래의 소스에서만 변경할 수 있으며, 데이터 화면에서는 변경할 수 없습니다.

<div id="adjust-field-types" />

<Accordion title="필드 유형 조정">

각 필드를 검토하고 옆 드롭다운 목록에서 적절한 데이터 유형을 선택하여 변경하십시오.

</Accordion>

<div id="remove-fields" />

<Accordion title="필드 제거">

식별자 필드를 제외하고 필드는 모두 제거할 수 있습니다.

**필드를 제거하려면:**

1. 제거하려는 필드의 오른쪽 위로 마우스를 이동합니다.
2. 나타나는 오류 아이콘을 클릭합니다. 이제 삭제한 필드를 다시 가져올 수 있도록 **복구** 버튼이 있는 **제거** 섹션에 필드가 나타납니다.
3. [저장](#save-your-data-view)을 클릭하세요.

</Accordion>

<div id="restoring-temporarily-removed-fields" />

<Accordion title="일시적으로 제거된 필드 복원하기">

목록에서 필드를 삭제하면 해당 필드는 **제거됨** 섹션에 배치됩니다. 데이터 뷰를 저장하지 않으면 **복구** 버튼을 클릭하여 복원할 수 있습니다.

</Accordion>

</Accordion>

<div id="save-your-data-view" />

<Accordion title="데이터 보기 저장">

데이터 뷰는 어느 단계에서든 저장할 수 있습니다. 저장한 후에는 소스 목록의 원래 데이터 소스 아래에 추가되며, [편집, 공유 또는 삭제할 수 있습니다](#데이터-보기-편집).

> 📘 **참고**
>
> 새 데이터 뷰를 저장하면 더 이상 [제거된 필드](#remove-fields)가 보이지 않습니다. 즉, 복원할 수 없습니다. 하지만 항상 원래의 데이터 소스를 사용하여 다른 데이터 뷰를 만들 수 있습니다.

**데이터 뷰를 저장하려면:**

* 페이지 하단에서 **저장**을 클릭합니다.

</Accordion>

<div id="manage-data-views" />

## 데이터 보기 편집

데이터 뷰는 원본 소스 아래의 **소스** 탭에 표시됩니다. 공동 작업자와 편집, 삭제 또는 공유할 수 있습니다.

<div id="edit-details" />

<Accordion title="일반 세부 정보 수정">

데이터 보기 설명 또는 설명에 사용된 레이블을 수정할 수 있습니다.

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **데이터 클린룸**을 선택합니다.
2. **소스** 탭에서 소스 이름을 클릭합니다. 연관된 데이터 뷰가 표시됩니다.
3. 데이터 뷰 위로 마우스를 이동하여 수정한 다음 행 끝에 있는 [<Image alt="edit-subdomain.png" src="https://files.readme.io/ffe3da7d1c065a806a44c607bcf1231e06bf7e7478ca50187e57cb5ab876ae72-30192959751185.png" width="2.39%" />](/docs/data-collaboration-platform-dcp-create-customized-data-views#share-a-data-view) (편집 아이콘) 을 클릭합니다.
4. 적용된 설명 또는 레이블을 편집합니다.

</Accordion>

<div id="edit-customization-fields" />

<Accordion title="사용자 정의 필드 편집">

기능과 필터를 조정하거나, 새 필드를 만들거나, 기존 필드를 편집하거나, 데이터 뷰에서 필드를 제거할 수 있습니다.

**변환 또는 통합 필드 편집 방법:**

1. **데이터 사용자 정의**에서 **필드 관리** 를 클릭합니다.
2. [전환 & 집계](#transform-aggregate-and-filter-data) 탭에서 해당 필드를 선택하여 편집하고 필요한 변경을 수행합니다.
3. **저장**을 클릭하세요.

**필터를 편집하려면:**

* **데이터 사용자정의** > [필터](#filter-your-data) 항목에서 필터 및 조건에 필요한 변경 사항을 적용합니다.

**참고:** 변환 또는 통합 함수가 업데이트되면 필터는 실행한 후에만 데이터에 적용됩니다.

</Accordion>

<div id="edit-structure" />

<Accordion title="필드 편집">

* [필드 선택](#select-fields)에서 필요한 사항을 변경하십시오.

</Accordion>

<div id="delete-a-data-view" />

<Accordion title="데이터 보기 삭제">

데이터 뷰를 삭제할 때, 다음이 적용됩니다.

* 데이터 뷰가 목록에서 삭제되었습니다.
* 연결된 모든 오디언스는 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-build-and-activate-audiences#잠재-고객-상태">만료되고</Anchor> 회색으로 표시됩니다.
* 연관된 모든 [공유 데이터가](#share-a-data-view) 공유되지 않음

**데이터 보기 삭제 방법:**

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **데이터 클린룸**을 선택합니다.
2. **소스** 탭에서 소스 이름을 클릭합니다. 연관된 데이터 뷰가 표시됩니다.
3. 삭제하려는 데이터 화면 위로 마우스를 가져가서 행 끝에 있는 <Image alt="delete.jpeg" src="https://files.readme.io/a763fd0bf1379242e3f1bc6b4433e3f9b58329af1a708a9a0e8127af2973c8e3-51912738874257.jpg" width="2.3%" /> 를 클릭합니다.
4. 삭제 확인 창에서 **삭제** 를 클릭합니다. 데이터 뷰가 삭제되었습니다.

</Accordion>

<div id="share-a-data-view" />

<Accordion title="데이터 보기 공유">

데이터 뷰를 공동 작업자와 공유하고 권한을 부여합니다.

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **데이터 클린룸**을 선택합니다.
2. **소스** 탭에서 소스 이름을 클릭합니다. 연관된 데이터 뷰가 표시됩니다.
3. 공유할 데이터 화면 위로 마우스를 가져가서 행 끝에 있는 <Image alt="share-icon.jpeg" src="https://files.readme.io/1d8b59793e030a27e22fed2400f3c6ce28346615edff3c9c4545dc81a35d603c-51912723203345.jpg" width="3.01%" /> (공유 아이콘) 을 클릭합니다.
4. 공동 작업자의 이메일 주소를 입력하고 **다음**을 클릭하세요.
5. 해당하는 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#공유-권한">공유 권한을 선택합니다</Anchor>.
6. **저장 및 전송** 을 클릭합니다.

<div id="note-4" />

> 📘 **참고**
>
> 소스에서 생성된 데이터 보기만 공유할 수 있습니다. 공유 소스에서 만든 보기는 다른 사람과 공유할 수 없습니다.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 01JD9Z4WKKDWS2EQND0SY7EADZ=%EA%B0%9C%EC%9A%94 data-view-functions=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0-%ED%95%A8%EC%88%98-data-view-functions 01JD9Z4WKMTZ18E13E6V3KZYB3=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0-%ED%95%A8%EC%88%98-data-view-functions the-data-view-builder=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B7%B0-%EB%B9%8C%EB%8D%94 01JD9Z4WKNREMCMB9PNSVVQ024=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B7%B0-%EB%B9%8C%EB%8D%94 main-section=%EB%A9%94%EC%9D%B8-%EC%84%B9%EC%85%98 01JD9Z4WKQQXPN1SBK5K5C8ZGC=%EB%A9%94%EC%9D%B8-%EC%84%B9%EC%85%98 side-panel=%EC%B8%A1%EB%A9%B4-%ED%8C%A8%EB%84%90 01JD9Z4WKRTXMMBBPS41AXHPE1=%EC%B8%A1%EB%A9%B4-%ED%8C%A8%EB%84%90 set-a-data-view=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0-%EC%84%A4%EC%A0%95 01JD9Z4WKRD4V4A07WT5YG42RZ=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0-%EC%84%A4%EC%A0%95 01JD9Z4WKWQJJE9Q8EMQY8NCMD=set-the-data-view-general-details naming-requirements=%EC%9D%B4%EB%A6%84-%EC%A7%80%EC%A0%95-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD-%EB%B0%8F-%EC%A7%80%EC%B9%A8 01JD9Z4WKX3BGN7V9V1V1YBYWT=%EC%9D%B4%EB%A6%84-%EC%A7%80%EC%A0%95-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD-%EB%B0%8F-%EC%A7%80%EC%B9%A8 01JD9Z4WM1EQVKS9B4EHMTHW41=transform-aggregate-and-filter-data 01JD9Z4WM2TMAX43HEP7J68E0Y=%EC%B0%B8%EA%B3%A0 01JD9Z4WM4RP9HVF171YH7BFQZ=transform-and-aggregate-your-data 01JD9Z4WM9TP35VPCNMQ98Z8R1=filter-your-data 01JDEVJ95NXPNDT8VMX0YS179S=%EC%B0%B8%EA%B3%A0-1 01JDEVRX2EV64YQN2JE901CEK8=%EC%B0%B8%EA%B3%A0-2 01JD9Z4WMDV8B7P8W5E13J7HNJ=list-of-functions-and-use-case-examples transformation-functions=%EC%A0%84%ED%99%98-%ED%95%A8%EC%88%98 h_01JDA45VWKH2ZKVBTK87VFVKTB=%EC%A0%84%ED%99%98-%ED%95%A8%EC%88%98 example-transformation=%EC%98%88-%EC%A0%84%ED%99%98 h_01JDA4611HFFEA17352NSNCJYX=%EC%98%88-%EC%A0%84%ED%99%98 aggregate-functions=%ED%86%B5%ED%95%A9-%ED%95%A8%EC%88%98 h_01JDA467NV99FDAXJCXYSD5PBF=%ED%86%B5%ED%95%A9-%ED%95%A8%EC%88%98 example-aggregation=%EC%98%88-%EC%A7%91%EC%95%BD h_01JDA46DWD6G3S4S5FM48KWQXA=%EC%98%88-%EC%A7%91%EC%95%BD example-aggregation-with-a-condition=%EC%98%88%EC%8B%9C-%EC%A1%B0%EA%B1%B4%EC%9D%B4-%EC%9E%88%EB%8A%94-%EC%A7%91%EC%95%BD 01JDETVS9XQ9XCNEFVCSC8GAJR=%EC%98%88%EC%8B%9C-%EC%A1%B0%EA%B1%B4%EC%9D%B4-%EC%9E%88%EB%8A%94-%EC%A7%91%EC%95%BD 01JD9Z4WMJ9XFBXPJAM6RNRP96=select-fields 01JD9Z4WMJJGXG9XXSW6Q6S5KE=%EC%B0%B8%EA%B3%A0-3 01JD9Z4WMKA2J94AYW9VXKKVKQ=adjust-field-types 01JD9Z4WMM4QQDP749R7H93Z67=remove-fields 01JD9Z4WMNHXCP4Q66C1TN67Y4=restoring-temporarily-removed-fields 01JD9Z4WMQGY8DCEWMPGX8FC2Y=save-your-data-view 01JDA2A87AC37C41ADJ9BHRW0H=%EC%B0%B8%EA%B3%A0-4 manage-data-views=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0-%ED%8E%B8%EC%A7%91 01JD9Z4WMRFS0S408ZJ2YKBZF3=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0-%ED%8E%B8%EC%A7%91 01JD9Z4WMT7GG4JV91JE5KAJ4X=edit-details 01JD9Z4WMVN8VXF3R471XSR0CG=edit-customization-fields 01JD9Z4WMYY6ZJ78S5ZH8QHFQY=edit-structure 01JD9Z4WMZGV916XJ77V3NR1HK=delete-a-data-view 01JD9Z4WN3VX56JDWK937D1WXH=share-a-data-view 01JDA2A87RG8V8RZW4EB1B2K56=%EC%B0%B8%EA%B3%A0-5" />
