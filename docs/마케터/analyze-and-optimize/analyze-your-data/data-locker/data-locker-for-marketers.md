---
title: 마케터용 데이터 락커
metadata:
  keywords:
    - Reports
    - Data Locker
    - Advertisers
    - Raw Data
    - Developers
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2019-02-03T12:20:08Z'
  edited_at: '2026-10-14T10:31:03Z'
  id: 360000877538
  locale: ko
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/ko/articles/360000877538
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 데이터 락커(Data Locker)는 리포트 데이터를 클라우드 스토리지로 전송하여 BI 시스템에 로드합니다. 여러 저장 위치 중에서 선택할 수 있습니다: 사용자는 AWS의 앱스플라이어 소유 버킷, AWS GCS, Yandex, BigQuery 및 Snowflake와 같은 다양한 스토리지 대상 중에서 선택할 수 있습니다. 데이터 락커는 [여러 대상](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination)을 지원합니다. 즉, 모든 데이터를 다중 대상으로 보내거나 대상별로 데이터를 분리하거나 이 두 가지를 조합할 수 있습니다.

## 개요

![6133DataLockerForAdvertisers.png](https://files.readme.io/820fee89515ccdcdfac2043bcb9fde722ddc8ec852a140ec250378c581d9c375-32966274469649.png)

데이터 락커에서 앱스플라이어가 선택한 클라우드 스토리지 옵션으로 전송할 데이터에 포함할 앱, 미디어 소스, 이벤트 및 리포트를 선택하세요. 스토리지에서 BI 시스템으로 프로그래밍 방식으로 데이터를 로드합니다.

<div id="data-locker-features" />

<Accordion title="데이터 락커—기능">

| 기능 | 설명 |
| --- | --- |
| [스토리지 옵션(클라우드)](/docs/data-locker-for-marketers#storage-options) | 데이터 락커는 데이터를 다음 클라우드 서비스 제공업체에 전송할 수 있습니다.<ul><li>앱스플라이어가 소유한 AWS의 스토리지</li><li><Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup">사용자가 소유한 스토리지</Anchor>:<ul><li>AWS</li><li>GCS</li><li>Azure Blob</li><li>[베타] Yandex</li><li>BigQuery</li><li>Snowflake</li></ul></li></ul>데이터 락커에서 대상을 1개 이상 설정할 수 있습니다. 즉, 데이터의 전부 또는 일부를 [여러 대상으로](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination)보낼 수 있습니다.<br /><br />**예시**<ul><li>리포트 유형별로 데이터를 분리합니다. 로데이터를 GCS로 전송하고 데이터를 Snowflake로 집계합니다.</li><li>앱별로 데이터를 분리하고 앱 그룹별로 데이터를 다른 버킷으로 보냅니다.</li></ul> |
| 멀티 앱 | 계정에 있는 1개, 그 이상, 또는 모든 앱의 데이터를 전송합니다. 앱을 계정에 추가하면 자동으로 포함될 수 있습니다. |
| 사용가능 기간 | 14일 |
| [데이터 분리](/docs/data-locker-for-marketers#app-segregation) | 사용 가능한 데이터 분리 옵션(버킷 클라우드 스토리지 관련):<ul><li>[기본값] **통합:** 모든 앱의 데이터 결합. 행 수준 앱 ID 필드는 데이터 파일에서 앱을 식별하는 데 사용됩니다.</li><li>**앱별로 분리:** 각 앱의 데이터는 별도의 폴더에 있습니다. 폴더 이름은 앱 ID로 구성됩니다.</li></ul> |
| 데이터 형식 옵션 | <ul><li>버킷 클라우드 스토리지의 경우:<ul><li>CSV</li><li>Parquet</li><li><Anchor target="_blank" href="/marketers/ko/docs/adobe-experience-platform-aep-integration-with-appsflyer-data-locker">Adobe</Anchor></li></ul></li><li>데이터 웨어하우스</li></ul> |
| 데이터 최신성 | 최신성은 리포트 유형에 따라 다릅니다.<ul><li>**시간별:** 데이터는 연속적으로 생성됩니다. 예를 들어 인스톨 및 인앱 이벤트 데이터는 이벤트가 앱스플라이어에 도착한 후 몇 시간 이내에 기록됩니다.</li><li>**일별:** 앱 삭제와 같은 리포트는 매일 생성되며 다음 날 사용할 수 있습니다.</li><li>**버전 관리** 동일한 기간 동안 동일한 리포트가 여러 번 생성되는 경우 버전 관리 메커니즘이 적용됩니다.</li></ul> |

</Accordion>

<div id="reports-available-via-data-locker" />

<Accordion title="데이터 락커를 통해 사용 가능한 리포트">

<Anchor target="_blank" href="/marketers/ko/docs/data-locker-advertiser-reports">데이터 락커를 통해 사용 가능한 리포트</Anchor>

</Accordion>

<div id="set-data-locker-report-settings" />

## 데이터 락커 리포트 설정하기

데이터 락커를 설정하려면 다음의 단계에 따라 클라우드 서비스를 연결하고, 내보내기 설정을 정의하고, 리포트 내용을 사용자 지정해야 합니다.

<div id="1-set-up-your-cloud-service" />

<Accordion title="1. 다음을 사용하여 클라우드 서비스를 설정합니다.">

하나 이상의 클라우드 서비스 공급자에 데이터 락커를 연결할 수 있습니다. 데이터 락커와 함께 작동하도록 설정하는 방법은 다음을 참조하십시오:

* <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor> 버킷
* <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor> 버킷
* <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor> Blob
* [베타] Yandex 버킷
* <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor> 데이터 웨어하우스
* <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor> 데이터 웨어하우스

**참고**! 데이터 락커 구독이 없고 코호트 분석 또는 SKAN 데이터에 액세스하는 경우 마케터 소유 스토리지 절차를 완료해야 합니다.

</Accordion>

<div id="2-add-a-connection-to-your-cloud-service" />

<Accordion title="2. 클라우드 서비스에 연결 추가">

클라우드 서비스 계정을 데이터 락커와 함께 작동하도록 설정한 후(위의 "클라우드 서비스 설정" 참조), 계정의 자격 증명을 사용하여 데이터 락커에서 연결을 생성하십시오. 최대 두 개의 연결을 생성할 수 있습니다.

<div id="note" />

> 📘 **참고사항**
>
> 기본적으로 각 계정은 최대 **2개의 데이터 락커 연결**을 열 수 있습니다. 추가 연결이 필요한 경우 고객 성공 관리자(CSM)에게 문의하십시오.

클라우드 공급자와 연결을 생성하려면 다음 단계를 수행하십시오.

1. 앱스플라이어의 사이드바에서 **내보내기(Exports)**>**데이터 락커**로 이동합니다.
2. 오른쪽에서 **새 연결(New connection)** 을 클릭하세요.
3. **연결 이름(Connection name)** 에 연결 이름을 입력하세요. 소문자, 숫자, 하이픈 "-"만 사용하세요.
4. 연결하려는 클라우드 서비스의 아이콘을 클릭하세요.
5. 선택한 서비스에 따라 다음 연결 정보를 입력하십시오.

   <div id="aws-cloud-bucket-connection" />

   <Accordion title="AWS 클라우드 버킷 연결">

   AWS 연결을 설정하기 전에 AWS 버킷을 생성하십시오. 생성 방법에 대해 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#aws-storage">여기</Anchor>를 참조하세요.

   연결을 설정하려면:

   1. AWS S3 버킷 이름을 입력하십시오. `af-`접두사는 필수이며 수동으로 입력해야 합니다.
   2. **연결 테스트(Test connection)** 를 클릭합니다.
   3. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
   4. **이 연결을 Adobe Experience Platform과 호환할지**여부를 선택합니다.  선택한 후, **저장**을 클릭하고 [글로벌 수준 필터 선택](#select-global-level-filters)을 계속 진행하십시오.
   5. **저장**을 클릭하세요.

   </Accordion>

   <div id="gcs-cloud-bucket-connection" />

   <Accordion title="GCS 클라우드 버킷 연결">

   GCS 연결을 설정하기 전에 GCS에 버킷을 생성하십시오. 연결 방법에 대해 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#gcs-storage">여기</Anchor>를 참조하세요.

   연결을 설정하려면:

   1. **GCS 버킷 이름**을 입력합니다.
   2. **연결 테스트(Test connection)** 를 클릭합니다.
   3. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
   4. **이 연결을 Adobe Experience Platform과 호환할지**여부를 선택합니다.  선택한 후, **저장**을 클릭하고 [글로벌 수준 필터 선택](#select-global-level-filters)을 계속 진행하십시오.
   5. **저장**을 클릭하세요.

   </Accordion>

   <div id="azure-cloud-bucket-connection" />

   <Accordion title="Azure 클라우드 버킷 연결">

   Azure 연결을 설정하기 전에 Azure에서 스토리지 계정을 엽니다. 스토리지 계정을 여는 방법에 대해 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#beta--azure-storage">여기</Anchor>를 참조하세요.

   연결을 설정하려면:

   1. **연결** 이름, **스토리지 계정 이름** 및 **키를** 입력합니다.
   2. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
   3. **이 연결을 Adobe Experience Platform과 호환할지**여부를 선택합니다.  선택한 후, **저장**을 클릭하고 [글로벌 수준 필터 선택](#select-global-level-filters)을 계속 진행하십시오.
   4. **저장**을 클릭하세요.

   </Accordion>

   <div id="yandex-cloud-bucket-connection" />

   <Accordion title="Yandex Cloud 버킷 연결">

   AWS 연결을 설정하기 전에 Yandex에서 서비스 계정을 생성하십시오. 스토리지 계정을 여는 방법에 대해 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#yandex">여기</Anchor>를 참조하세요.

   연결을 설정하려면:

   1. **버킷 이름**, **액세스 키** 및 **비밀 키**를 입력합니다.
   2. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
   3. **이 연결을 Adobe Experience Platform과 호환할지**여부를 선택합니다.  선택한 후, **저장**을 클릭하고 [글로벌 수준 필터 선택](#select-global-level-filters)을 계속 진행하십시오.
   4. **저장**을 클릭하세요.

   </Accordion>

   <div id="bigquery-data-warehouse-connection" />

   <Accordion title="BigQuery 데이터 웨어하우스 연결">

   BigQuery 연결을 설정하기 전에 BigQuery에서 데이터 세트를 생성하십시오. 스토리지 계정을 여는 방법에 대해 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#bigquery">여기</Anchor>를 참조하세요.

   연결을 설정하려면:

   1. BigQuery 프로젝트 ID와 데이터셋 이름을 입력합니다.
   2. **연결 테스트(Test connection)** 를 클릭합니다.
   3. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
   4. **저장**을 클릭하고 [글로벌 수준 필터 선택](#select-global-level-filters)을 계속 진행하십시오.

   </Accordion>

   <div id="snowflake-data-warehouse-connection" />

   <Accordion title="Snowflake 데이터 웨어하우스 연결">

   Snowflake 연결을 설정하기 전에 Snowflake에서 계정을 여세요. 스토리지 계정을 여는 방법에 대해 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#snowflake">여기</Anchor>를 참조하세요.

   연결을 설정하려면:

   1. Snowflake 지역과 계정 ID를 입력합니다.
   2. **연결 테스트(Test connection)** 를 클릭합니다.
   3. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
   4. **저장**을 클릭하고 [글로벌 수준 필터 선택](#select-global-level-filters)을 계속 진행하십시오.

   </Accordion>

6. **저장**을 클릭하세요. **리포트 출력 설정 섹션**이 표시됩니다.

<div id="note-1" />

> 📘 **참고사항**
>
> 연결이 생성, 업데이트 또는 삭제되었는지, 그리고 누가 변경했는지 확인하려면 [감사 로그](#track-connection-changes-in-the-audit-log)를 참조하세요.

</Accordion>

<div id="3-set-the-report-output-settings" />

<Accordion title="3. 리포트 출력 설정을 지정합니다.">

클라우드 서비스와의 연결을 설정한 후, 데이터 락커 리포팅 출력을 위한 일반 설정을 계속해서 설정할 수 있습니다. **클라우드 서비스가 BigQuery 또는 Snowflake인 경우 이 단계를 건너뛸 수 있습니다**

1. **Report output settings(리포트 출력 설정)** 섹션에서 폴더 구조 ([data segregation(데이터 분리)](/docs/data-locker-for-marketers#app-segregation))를 선택하십시오.
   * **통합** (기본값): 리포트 파일에는 모든 앱의 기록이 포함되어 있습니다.
   * **앱별로 분리:** 각 리포트 파일은 하나의 앱에 할당됩니다.
2. 리포트 파일 형식을 선택하십시오. Parquet(기본값) 또는 CSV.
3. 리포트 파일의 압축 유형을 선택하십시오:
   * Snappy(Parquet 파일에만 사용 가능)
   * GZIP
4. 파일에서 원하는 최대 행 번호를 선택하세요. 10k, 25k, 50, 100k, 200k, 또는 500k 중 선택할 수 있습니다. 파일에 행이 많을수록 파일 수는 적지만 파일 크기는 커집니다.

   <div id="note-2" />

   > 📘 **참고사항**
   >
   > 아래에서 리포트의 경로 패턴을 확인하세요. 참고: 실제 경로는 표시된 것과 다를 수 있습니다.


</Accordion>

<div id="select-global-level-filters" />

<Accordion title="4. 글로벌 수준 필터 선택">

글로벌 수준의 필터를 사용하면 **앱 또는 미디어 소스별로 리포트를 필터링할 수 있습니다**. 이 필터는 귀하의 데이터 락커 계정 대부분의 리포트에 적용되지만, 리포트 수준에서도 설정할 수 있습니다(아래 [7-select-the-reportlevel-filters](#select-the-report-level-filters) 참조). 두 수준 모두에 동일한 필터가 적용되면 리포트 수준의 필터가 우선합니다.

필터를 적용하려면 다음을 수행하십시오.

1. **리포트** 섹션에서 필터를 클릭하고 리포트에 포함할 항목을 선택하십시오. 예를 들어, <Image alt="Untitled.png" src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" width="53px" /> **앱** 필터를 클릭하고 리포트에 포함할 앱을 선택합니다.
2. Enter (⏎) 버튼을 클릭하세요.

</Accordion>

<div id="5-select-the-report" />

<Accordion title="5. 리포트 그룹 선택">

클라우드 서비스에서 받고 싶은 리포트를 선택하세요. 리포트는 그룹으로 나열됩니다. 리포트 그룹 이름을 클릭하면 그룹이 확장되거나 축소됩니다.

* 리포트를 선택하려면 <Image alt="down.png" src="https://files.readme.io/3f59bcc54434374270c0099394a740cc650a3b4a1be0f3f34d298be1ebcad40c-34623601355409.png" width="20px" />를 클릭하여 리포트 그룹을 확장하십시오. 그룹의 각 리포트에 대해 다음 정보가 제공됩니다:
  * **리포트 이름:** 리포트의 제목.
  * **데이터셋 이름:** 리포트의 기록이 포함된 데이터셋의 이름.
  * **데이터 최신성:** 리포트가 새로운 기록으로 얼마나 자주 업데이트되는지 (예: 매시간, 매일 또는 버전별).
  * **필드:** 선택 가능한 총 필드 수 대비 리포트에서 선택한 필드(또는 열)의 수

</Accordion>

<div id="customize-or-duplicate" />

<Accordion title="6. 리포트 사용자 정의 또는 복제">

리포트 그룹에서 하나 이상의 리포트를 선택한 후, **원본 리포트 사용자 정의** 또는 복제하여 **별도의 사용자 정의 사본**을 생성할 수 있습니다. 이렇게 하면 원본 버전에 영향을 주지 않고 리포트의 필드와 필터를 특정 요구 사항에 맞게 조정할 수 있습니다.

**옵션 A: 원본 리포트 사용자 정의**

1. 리포트 이름 옆에 있는 <Image alt="customize.png" src="https://files.readme.io/35f4653b944cd5dc81c6de76f8dcacd9c3413ea49915ba2b5865a244ede3c4b6-35437232722833.png" width="20px" /> **사용자 정의** 버튼을 클릭합니다.
2. 리포트 편집기가 열리며, 필드를 선택하고 필터를 적용할 수 있습니다.
3. 변경 사항은 원본 리포트 구성에 저장됩니다.

*참고: 이것은 리포트가 귀하의 클라우드 스토리지에 전달되는 방식을 수정합니다.*

**옵션 B: 리포트 복제**

* 리포트 이름 옆에 있는 <Image alt="Untitled 2.png" src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" width="5px" />를 클릭합니다.
* 드롭다운 메뉴에서 <Image alt="duplicate2.png" src="https://files.readme.io/d8fbf09b3a8e3839f80a0a4fec90e0360dc1c2a4a066bf58438364c0d8a15c65-35439088509073.png" width="17px" /> **복제**를 선택합니다.
* 리포트의 사본이 생성되며, 접두사 `copy_of_`가 붙어 이름이 지정됩니다.
* 복제된 리포트는 추가 사용자 지정을 위해 편집 모드에서 열립니다.

*팁: 복제는 다양한 사용 사례에 맞는 리포트 변형을 만드는 데 이상적입니다.*

사용자 지정 또는 복제 여부를 선택한 후, 다음 단계에 설명된 대로 리포트 필드를 설정합니다.

</Accordion>

<div id="6-select-the-report-fields" />

<Accordion title="7. 리포트 필드 선택">

리포트를 사용자 지정하거나 복제하기로 선택하면, 다음 단계에서는 어떤 데이터 필드가 포함되어야 하는지 정의합니다. 각 리포트는 사용 가능한 전체 필드 세트를 보여주며, 분석 또는 연동에 관련된 것만 포함하도록 선택을 사용자 지정할 수 있습니다. 기본적으로 모든 필드가 선택되지만, 특정 필드를 수동으로 선택하여 리포트를 세분화할 수 있습니다.

리포트에 포함될 필드를 선택하려면:

1. 선택한 리포트 대화 상자에서 **필드** 탭 아래의 필드 위에 마우스를 올려 설명을 확인합니다.

   [![HQ1_2024-08-26_15.44.23.png](https://files.readme.io/293d227464e3907982e0c82187915ee1b16386a4111e83ebd8db065ade64a48b-34623601367697.png)](https://files.readme.io/293d227464e3907982e0c82187915ee1b16386a4111e83ebd8db065ade64a48b-34623601367697.png)
2. 리포트에 포함할 필드를 선택하거나 제외할 필드의 선택을 해제합니다.
3. 설정을 저장하려면 **Apply(적용)** 을 클릭하세요.

**다른 리포트에서 필드 선택 복사하기**

다른 리포트에서 필드 선택을 복사하여 시작점으로 삼고, 계속해서 필드를 선택하거나 선택 해제하여 리포트를 세밀하게 조정할 수 있습니다.

1. **필드** 탭에서 임의의 필드를 선택 해제하십시오.
2. **리포트에서 스키마 가져오기(Pull schema from report)** 를 클릭하세요.
3. 복사하고자 하는 필드 설정을 포함하는 리포트를 선택하십시오.
4. 필드를 계속 선택하거나 선택 해제하십시오.
5. 리포트의 원래 필드 선택을 복원하려면 <Image alt="제목 없음 4.png" src="https://files.readme.io/dda26e3d18c52049cf92d7862a87ce7a46e6a00c349afd70dfe6d1809e00b89e-34623601369361.png" width="15px" /> **새로 고침**을 클릭하십시오.

</Accordion>

<div id="7-select-the-reportlevel-filters" />

<Accordion title="8. 리포트 수준 필터 선택">

리포트 수준 필터를 사용하면 **앱, 미디어 소스 또는 기타 디멘션을 기준으로 리포트를 필터링할 수 있습니다**. 계정의 모든 리포트에 적용되는 필터를 설정할 수도 있습니다. [글로벌 수준 필터 선택](#select-global-level-filters)를 참조하십시오. 기본적으로 리포트 수준 필터는 글로벌 수준 필터 설정에 맞춰져 있지만, 선택한 보고서에만 적용되는 사용자 지정 설정으로 업데이트할 수 있습니다.

지정된 리포트에 적용할 필터를 선택하려면:

1. 사용자 지정하려는 특정 리포트 위에 마우스를 올립니다.
2. 작업 메뉴를 열려면 <Image alt="Untitled 2.png" src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" width="6px" />를 클릭하고, <Image alt="Untitled 3.png" src="https://files.readme.io/c27f864253e6749f883047b4529ad292153500db5aebd452568a6aa04407472e-34623601366033.png" width="20px" /> **리포트 편집(Edit report)** 을 선택하세요.
3. **필터** 탭을 엽니다. 필터가 글로벌 수준 필터 설정으로 설정되었습니다.
4. 필터를 클릭하고 리포트에 포함할 항목을 선택하세요. 예를 들어, <Image alt="Untitled.png" src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" width="53px" /> **앱** 필터를 클릭하고 리포트에 포함할 앱을 선택합니다.
5. Enter (⏎) 버튼을 클릭하세요. 귀하의 선택이 글로벌 수준 설정보다 우선합니다.
6. (선택 사항) **인앱** 리포트의 경우 **인앱 이벤트** 필터를 설정할 수 있습니다. 이름을 정확하게 입력하여 선택하십시오.
7. 설정을 저장하려면 **Apply(적용)** 을 클릭하세요.

</Accordion>

<div id="8-remove-legacy-fields" />

<Accordion title="9. 레거시 필드를 제거합니다.">

레거시 필드는 이전에 리포트 스키마에 포함되었지만 현재는 제외된 필드입니다. 이 필드를 제거하여 리포트에 관련 정보만 포함되도록 하는 것이 좋습니다. 변경하기 전에 워크플로우와 연동이 이 필드에 의존하지 않는지 확인하세요.

**특정 레거시 필드 제거하기**

1. **레거시 필드** 탭을 엽니다.
2. 켜기: **리포트에 레거시 필드 포함하기**
3. 제외할 필드를 선택 해제하세요.
4. **Apply(적용)** 을 클릭합니다.
5. 연결 설정을 저장하십시오.

**모든 레거시 필드 제거하기:**

1. 레거시 필드 탭을 엽니다.
2. 끄기: **리포트에 레거시 필드 포함하기**

<div id="note-3" />

> 📘 **참고사항**
>
> 리포트에 레거시 필드를 포함하고 싶지만 레거시 필드 목록이 회색으로 표시되고 잠겨 있어 포함할 수 없는 경우 고객 성공 관리자에게 문의하세요.

<div id="non-empty-legacy-fields" />

#### 비어 있지 않은 레거시 필드

대부분의 레거시 필드는 비어 있거나 `null`입니다. 그러나 그 중 일부는 값을 포함하고 있지만 여전히 레거시로 간주됩니다. 그 이유는 다음과 같습니다:

* 리포트에 다른 이름(이름 변경됨)으로 나타납니다.
* 리포트 스키마에서 제외되었습니다(사용 중단됨).

[비어 있지 않은 레거시 필드 목록 다운로드 (CSV).](https://docs.google.com/spreadsheets/d/e/2PACX-1vRzJr2IgKTHKq_6IFX-PFFv6_89ixtlbGZ9RNH134TniGlWa_M-85D1L2E7LhzQrDjictnSnNNnN2mm/pub?output=csv)

</Accordion>

<div id="9-save-the-connection" />

<Accordion title="10. 연결 저장">

**저장(Save)** 을 클릭하면 첫 번째 데이터 덤프가 3시간 이내에 클라우드 서비스에 작성됩니다. 후속 데이터 업데이트 일정은 각 리포트에 따라 다릅니다.

<div id="important" />

> 🚧 **중요!**
>
> 데이터 락커에 적용한 모든 변경 사항이 적용되는 데 최대 3시간이 소요됩니다.

</Accordion>

<div id="set-user-permissions" />

## 사용자 권한 설정

관리자와 팀원 모두 올바른 권한을 가지고 데이터 락커에 접근할 수 있습니다.

* 관리자는 데이터 락커 페이지에 액세스하고, 모든 연결을 생성 및 관리하고, 편집자를 추가하고, 기존 연결에 소유자를 할당할 수 있습니다.
* 팀원은 데이터 락커 페이지에 접근하거나, 자신이 소유한 기존 연결을 편집하거나, 새 연결을 만들 수 있습니다. 그들은 계정 소유자라 하더라도 소유권(소유자 및 편집자 설정)을 관리할 수 없습니다.

<div id="manage-data-locker-access-and-ownership-admins" />

### 데이터 락커 액세스 및 소유권 관리 (관리자)

<div id="give-data-locker-access" />

#### 데이터 락커 액세스 부여하세요

* 팀 구성원에게 데이터 락커 접근 권한을 부여하려면, 데이터 락커 권한이 '관리(Manage)'로 설정된 **역할(role)** 을 할당해야 합니다.

<div id="manage-ownership-and-editors" />

#### 소유권 및 편집자 관리

기존 연결의 소유권을 이전하거나 팀 구성원을 편집자로 추가하려면 다음 단계를 따르세요.

1. 점 세 개로 된 옵션 메뉴를 클릭하세요.<Image alt="점 3개 아이콘.png가 있습니다" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="1.18%" /> 연결 안에 .
2. **소유권 관리를** 선택하세요.
3. 연결 소유자를 변경하거나 편집자를 추가하세요.

<div id="review-filters-after-changing-ownership" />

#### 소유권 변경 후 검토 필터

데이터 락커 연결의 소유자를 데이터 액세스 제한이 있는 사용자(예: 앱, 미디어 소스, 에이전시 또는 국가별로 제한됨)로 변경하는 경우 기존의 [전역 수준](#select-global-level-filters) 또는 [보고서 수준 필터가](#7-select-the-reportlevel-filters) 새 소유자의 권한에 맞게 재설정될 수 있습니다.

소유권 이전 후 필터를 검토하고 연결이 의도한 데이터 범위를 반영하는지 확인하십시오.

데이터 액세스 제한에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/user-management#데이터-액세스">유저 관리 > 데이터 액세스</Anchor> 참조하세요.

<div id="note-4" />

> 📘 **참고사항**
>
> AF AWS 연결에서는 관리자조차도 **소유권 관리** 옵션이 없습니다. AF AWS 연결을 편집, 삭제 또는 새로 생성할 수 있는 권한은 관리자만 가지고 있기 때문입니다. 이 예방 조치는 버킷 자격 증명의 노출을 방지하기 위해 취해집니다.

<div id="data-storage-architecture" />

## 데이터 스토리지 아키텍처

<div id="zd-overview" />

<div id="overview" />

<Accordion title="개요">

스토리지 내 데이터 구조는 해당 데이터가 클라우드 스토리지로 전송되는지, 아니면 데이터 웨어하우스로 전송되는지에 따라 달라집니다. 여기에 설명한 폴더 구조는 스토리지(버킷)에 적용됩니다. 데이터 웨어하우스 스토리지의 경우 폴더에 대한 참조가 보기에 적용된다는 점을 고려합니다.

데이터는 선택한 스토리지 옵션에 따라 기록됩니다. 클라우드 스토리지의 경우, 스토리지는 AWS상에서 앱스플라이어가 소유하고 있거나 AWS, GCS 또는 Yandex에서 소유하고 있습니다. 언제든지 스토리지 옵션을 전환하거나 데이터의 일부 또는 전체를 여러 스토리지 옵션으로 전송할 수 있습니다.

클라우드 버킷 스토리지의 데이터는 리포트 유형, 날짜 및 시간에 따라 계층적 폴더 구조로 구성됩니다. 다음 그림은 이 구조의 예시를 나타냅니다.

![DLFolderOVerview.png](https://files.readme.io/78f360ec1df72253e5b2cd725f3eecf4e17548a7f06b544a94a75a2c319d77a0-18107910420369.png)

지정된 리포트의 데이터는 해당 리포트와 연결된 시간(h) 폴더에 포함됩니다.

* 시간 폴더 수는 리포트 데이터 새로 고침(시간별, 일별 또는 버전별)에 따라 달라집니다.
* 데이터는 Snappy 또는 GZIP 압축 파일 또는 Parquet 또는 CSV 형식의 압축되지 않은 파일로 제공됩니다.
* 데이터 파일은 열(필드)로 구성됩니다.
* <Anchor target="_blank" href="/marketers/ko/docs/data-locker-advertiser-reports#user-journey">사용자 여정 리포트</Anchor>의 스키마(필드) 구조는 서로 동일하며 선택한 필드에 따라 달라질 수 있습니다. 다른 리포트에는 각각 고유한 명시적 필드인 스키마 제외 리포트를 포함합니다. 사용 가능한 리포트와 리포트 사양에 대한 링크는 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-advertiser-reports#user-journey">데이터 락커 마케터 리포트</Anchor>를 참조하세요.

</Accordion>

<div id="folder-structure" />

<Accordion title="폴더 구조">

| 폴더 | 설명 |
| --- | --- |
| 구독 ID | <Image alt="DataLockerFolders.png" src="https://files.readme.io/0cda5728e48dab772878cad13ed3b81168f152e1bf01604ac45b700af804dd16-32966264039185.png" width="439px" /><ul><li>버킷의 최상위 폴더는 스토리지 담당자 및 제공업체에 따라 다릅니다. 일반적으로 최상위 폴더는 구독 ID이지만, 예를 들어 Cyberduck을 사용하는 경우 ID가 북마크에 설정되고 폴더 구조에 표시되지 않는 경우가 있습니다.</li><li>*data-locker-hourly* 폴더에는 리포트 주제가 포함되어 있습니다. 이 수준 이상의 폴더는 버킷 소유권 및 클라우드 서비스 제공자에 따라 다릅니다.</li></ul>**버킷 소유자 및 클라우드 제공자에 기반한 폴더 구조 예시**<ul><li>**앱스플라이어 버킷**: &lt;af-ext-reports>/&lt;unique\_identifier>/&lt;data-locker-hourly></li><li>**AWS 버킷**: *&lt;af-datalocker-your bucket prefix>/&lt;generated-home-folder>&lt;subscription-id>*</li><li>**GCS 버킷:** &lt;your bucket name>/&lt;generated-home-folder>/&lt;subscription-id></li></ul> |
| 주제(t) | 리포트 유형은 리포트의 주제와 관련됩니다. |
| 날짜(dt) | 이는 관련된 데이터 날짜입니다. 로데이터의 경우 이벤트가 발생한 날짜를 의미합니다. 집약형 데이터의 경우 바로 리포트 날짜입니다. |
| 시간(h 또는 버전) | 리포트 유형에 따라 날짜 폴더가 **시간별(h)** 또는 **버전** 폴더로 구분됩니다.<br /><br />**<span id="hourly-folders"></span>시간별 폴더**<br /><br />h 폴더는 앱스플라이어가 데이터를 수신한 시간과 관련됩니다. 예를 들어, 14:00-15:00 UTC 사이에 수신한 인스톨 이벤트는 h=14 파일에 기록됩니다. 참고! 데이터가 앱스플라이어에 도착하는 시점부터 h 폴더가 데이터 락커에 기록될 때까지 약 1-3시간의 지연이 발생합니다. 예를 들어, h=14 폴더는 15:00 UTC에서 1시간 후에 기록됩니다.<br /><br />**시간별 폴더 특징**:<ul><li>0-23으로 번호가 지정된 24개 시간 폴더가 있습니다. 예를 들어, h=0, h=1 입니다.</li><li>late 폴더 h=late는 자정 이후에 도착하는 이전 날의 이벤트를 포함합니다. 이것은 다음 날 00:00–02:00 UTC에 도착하는 이벤트라는 의미입니다. 예를 들어 사용자가 월요일 08:00 UTC에 앱을 인스톨하고 이벤트가 화요일 01:00 UTC에 도착하면 이벤트는 월요일의 late 폴더에 기록됩니다.</li><li>02:00 UTC 이후 도착하는 데이터는 실제 도착 날짜 및 시간의 폴더에 기록됩니다.</li><li>h=late인 폴더의 데이터가 사용되는지 확인하십시오. 다른 폴더에는 포함되어 있지 않습니다.</li><li>\_임시 폴더: 경우에 따라 h 폴더 내에 임시 폴더를 생성합니다. 임시 폴더 및 하위 폴더를 무시하십시오. Example: /t=impressions/dt=2021-04-11/h=18/**\_temporary**.</li></ul>일별 보고서<ul><li>일별 데이터 최신성을 가진 로데이터 리포트는 h=23 폴더에 저장됩니다. 언인스톨 리포트는 일반적으로 h=2 폴더에 있지만 다른 폴더에 있을 수도 있습니다.</li><li>코호트 및 증분 리포트는 dt 폴더에 직접 저장됩니다.</li><li>버전별 리포트는 이 섹션에 나와있는 대로 각기 다른 규칙을 따릅니다.</li></ul>**UTC 시간을 사용하지 않는 앱에 대한 시간별 리포트 고려 사항.**<br /><br />지정된 달력 요일의 모든 데이터를 얻으려면 앱 시간대에서 정의한 요일에 따라 폴더를 세부적으로 사용해야 합니다.<ul><li>**동부 시간대**: 주어진 달력 날짜의 모든 데이터를 얻으려면 UTC 시간 및 날짜에 따라 폴더를 소비해야 합니다. 예시: 앱 시간대가 UTC+10(호주 시드니)이라고 하겠습니다. 화요일(시드니)와 관련된 모든 시간별 데이터를 얻으려면 다음 폴더를 사용해야 합니다: 월요일 h=14–23 및 늦은 시간, 화요일 h=0–13 및 14-15. 화요일 h=14-15를 소비해야 하는 이유는 무엇입니까? 일부 데이터는 늦게 도착할 수 있습니다. 따라서 h=14–15 폴더에는 늦게 도착하는 이벤트가 포함될 수 있습니다. event\_time을 UTC 기준 앱 캘린더 일자와 일치하도록 필터링해야 합니다.</li><li>**서반구 시간대:** 주어진 달력 날짜의 모든 데이터를 얻으려면 UTC 시간 및 날짜에 따라 폴더를 소비해야 합니다. 예시: 앱 시간대는 UTC- 7(로스앤젤레스)입니다. 화요일(로스앤젤레스)과 관련된 모든 시간별 데이터를 얻으려면 다음 폴더를 사용해야 합니다: 화요일 h=7–23 및 late, 수요일 h=0–6 및 7-8. 수요일 h=7-8을 사용해야 하는 이유는 무엇입니까? 일부 데이터는 늦게 도착할 수 있습니다. 따라서 h=7–8 폴더에는 늦게 도착하는 이벤트가 포함될 수 있습니다. event\_time을 UTC 기준 앱 캘린더 일자와 일치하도록 필터링해야 합니다.</li></ul>**<span id="version-folders"></span>버전 폴더**<br /><br />일부 리포트에는 버전별 옵션이 있습니다. 즉, 주어진 날짜에 대해 최근에 업데이트된 데이터가 여러 번 제공됩니다. 데이터가 늦게 도착하거나 더 정확한 데이터로 인해 계속 업데이트될 수 있으므로 동일한 보고서에는 여러 버전이 존재하며, 가장 최근 버전이 가장 정확합니다.<br /><br />지정된 날짜에 대한 리포트는 해당 날짜의 버전 폴더에 포함됩니다. 각 버전은 별도의 폴더에 포함되며, 해당 폴더 이름은 보고서를 고유하게 식별하는 Epoch 타임스탬프를 사용하여 설정됩니다.<br /><br />데이터 가져오기 프로세스에서는 데이터를 소급하여 기록할 수 있다는 점을 고려해야 합니다. 예를 들어, 1월 14일에는 데이터가 1월 1일 폴더에 기록될 수 있습니다. 버킷을 소유한 경우 클라우드 서비스 알림을 사용하여 가져오기 프로세스(<Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/NotificationHowTo.html">AWS</Anchor> \| <Anchor target="_blank" href="https://cloud.google.com/storage/docs/pubsub-notifications">GCS</Anchor>)를 트리거합니다. |

</Accordion>

<div id="app-segregation" />

<Accordion title="앱 분리">

버킷 클라우드 스토리지의 경우 데이터는 선택한 모든 앱의 데이터를 포함하는 통합 데이터 파일로 제공되거나 앱별로 폴더로 분리됩니다. 분리는 다음 표에 설명된 대로 h 폴더 내에 있습니다.

| 분리 유형 | 설명 |
| --- | --- |
| [기본값] 통합 | 모든 앱의 데이터는 통합된 데이터 파일로 제공됩니다. 데이터를 사용할 때 행 수준 app\_id 필드를 사용하여 앱을 구별합니다.<br /><br />**데이터 파일의 예시는 h= 2 폴더에 있습니다.**<br /><br />![UnifiedByApp.png](https://files.readme.io/dbc39c2ce99c1ff607fd553b9c9034e55728c102f31fd18a501cc00910267b28-18107874522513.png)<br /><br />데이터 파일 이름 지정 규칙은 unique\_id.gz입니다.<ul><li>데이터 로딩 프로세스는 다음과 같아야 합니다:<ul><li>\_SUCCESS 플래그가 설정된 다음에 데이터를 로드합니다.</li><li>*.gz* 확장자가 있는 폴더의 모든 파일을 로드합니다. 부품 번호 지정 논리를 사용하여 가져오기 프로세스를 구축하지 마십시오.</li></ul></li></ul> |
| 앱별로 분리 | 폴더에는 앱별 서브폴더가 포함됩니다. 지정된 앱의 데이터 파일은 앱 폴더에 포함되어 있습니다. 다음 그림에서 h=19 폴더에는 앱 폴더가 포함됩니다. 각 앱 폴더에는 연관된 데이터 파일이 포함됩니다. 참고! 데이터 파일에 app\_id가 포함되어 있지 않습니다. 폴더를 사용하여 app\_id를 확인해야 합니다.<br /><br />![DLSegregateByApp.png](https://files.readme.io/90639507da82f7dafacfa5bfb67fa96a8277747cd0eee226d74498bf5ff16869-32966264040977.png)<br /><br />각 앱 폴더에서 이름 지정 규칙은 unique\_id.gz입니다.<ul><li>데이터 로딩 프로세스는 다음과 같아야 합니다:<ul><li>\_SUCCESS 플래그가 설정된 다음에 데이터를 로드합니다.</li><li>*.gz* 확장자가 있는 폴더의 모든 파일을 로드합니다. 부품 번호 지정 논리를 사용하여 가져오기 프로세스를 구축하지 마십시오.</li></ul></li></ul>제한 사항: 이 옵션은 사람 기반 어트리뷰션 리포트에 사용할 수 없습니다. |

</Accordion>

<div id="data-files" />

<Accordion title="데이터 파일">

데이터 파일은 분리 유형에 따라 다릅니다.

<table><thead><tr><th>콘텐츠</th><th colspan="2">세부 정보</th></tr></thead><tbody><tr><td>완료 플래그</td><td colspan="2"><p>마지막 파일(완료) 플래그는 지정된 h 폴더에 대한 모든 데이터가 기록될 때 설정됩니다.  </p><ul><li>_SUCCESS 플래그가 존재하는지 확인하기 전에 폴더의 데이터를 읽지 마십시오.</li><li>_SUCCESS 플래그는 지정된 폴더에 기록할 데이터가 없고 폴더가 비어 있는 경우에도 설정됩니다. </li><li>참고! 앱별 구분 옵션에서는 플래그가 개별 앱 폴더가 아닌 h 폴더에 설정됩니다. 이전 섹션의 그림을 참조하십시오.  </li></ul></td></tr><tr><td>파일 형식</td><td colspan="2"><ul><li>데이터는 Snappy 또는 GZIP 압축 파일 또는 Parquet 또는 CSV 형식의 압축되지 않은 파일로 제공됩니다.</li><li>압축 해제 이후 데이터 파일은 사용자의 설정에 따라 Parquet 또는 CSV 형식을 가집니다.</li></ul></td></tr><tr><td>열 순서(CSV 파일)  </td><td colspan="2"><p>CSV 파일의 경우 리포트의 필드 순서는 항상 동일합니다. 새 필드를 추가하면 기존 필드 오른쪽에 추가됩니다.  </p><p>이와 관련하여:  </p><ul><li>사용자 여정 리포트의 열 구조는 동일합니다. 따라서 서로 다른 리포트 유형에 대해 유사한 데이터 로드 절차를 수행할 수 있습니다. 리포트에 포함될 필드를 선택합니다. 필드 의미는 <a href="./raw-data-field-dictionary" target="_blank">로데이터 사전</a>에 자세히 설명되어 있습니다. </li><li>리포트 가용성 섹션에 FF 표기가 있는 리포트는 공통 열 구조를 따르지 않습니다.  </li></ul></td></tr><tr><td>필드 채우기 고려사항</td><td colspan="2"><p><strong>빈 또는 공백 필드:</strong> 일부 필드는 null로 채워져 있거나 비어 있습니다. 이것은 지정된 리포트의 맥락에서 볼 때 리포트할 데이터가 없음을 의미합니다. 일반적으로 <em>null</em> 은 주어진 보고서 및 앱 유형의 컨텍스트에서 이 필드가 채워지지 않음을 의미합니다. 공백 "" 은 필드가 해당 컨텍스트에서는 관련이 있지만 채울 데이터가 없음을 의미합니다.  </p><p>제한된 미디어 소스의 경우 제한된 필드의 내용이 null로 설정됩니다.  </p><p>전체적으로 null과 blank를 동일한 것으로 간주하며, 사용할 수 있는 데이터가 없습니다.  </p><p><strong>시간대와 통화</strong></p><p>앱별 시간대와 통화 설정은 데이터 락커에 기록된 데이터에 영향을 주지 않습니다. 다음 사항이 적용됩니다.  </p><ul><li> <strong>시간대</strong>: 날짜 및 시간 데이터는 UTC에 있습니다.</li><li> <strong>통화</strong>: event_revenue_usd 필드는 미국 달러화(USD) 기준입니다.</li></ul><p><strong>쉼표를 포함하는 값</strong>: 이 쉼표는 큰따옴표 "" 사이에 포함되어 있습니다. 예를 들어, <code>`"iPhone6,1"`</code>.</p></td></tr></tbody></table>

</Accordion>

<div id="storage-options" />

<Accordion title="스토리지 옵션">

<div id="caution" />

> ❗️ **주의!**
>
> 마케터 소유 스토리지 옵션을 사용하는 경우:
>
> * GDPR 및 광고 네트워크/SRN 데이터 리텐션 정책과 같은 개인 정보 보호 규정을 준수하는지 확인합니다.
> * 마케터 소유의 스토리지 솔루션을 사용하여 데이터를 제3자에게 전송하지 마십시오.

* 데이터는 다음과 같이 사용자가 선택한 스토리지 소유자에게 기록됩니다.
  * 앱스플라이어 스토리지
  * 고객 스토리지 - AWS, GCS, Azure, Yandex, BigQuery 및 Snowflake
* 스토리지 선택은 언제든 변경할 수 있습니다.
* 스토리지를 변경하는 경우 다음 사항이 발생합니다.
  * 새로 선택한 스토리지에 한 시간 이내에 기록을 시작할 수 있습니다.
  * 7일의 전환 기간 동안 기존 스토리지에 계속 기록합니다. 전환 기간 만료 시간이 사용자 인터페이스에 표시됩니다. 전환 기간을 사용하여 데이터 로딩 프로세스를 업데이트합니다. 전환 기간을 다시 시작하거나 필요한 경우 앱스플라이어 버킷으로 되돌릴 수 있습니다.
  * **스토리지 변경**: 다중 스토리지 옵션을 사용하여 데이터를 여러 대상에 동시에 전송함으로써 한 스토리지 옵션에서 다른 스토리지 옵션으로 마이그레이션할 수 있습니다. 마이그레이션 및 테스트가 완료되면 더 이상 필요하지 않은 스토리지 옵션을 삭제합니다.

|  | 앱스플라이어 소유 스토리지(AWS) | 마케터 소유 스토리지(GCS, AWS, Azure, Yandex, BigQuery, Snowflake) |
| --- | --- | --- |
| 버킷 이름 | 앱스플라이어가 설정 | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>: 제한 없음</li><li><Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>: 사용자가 설정. 접두사 af-가 있어야 합니다.</li></ul>예시: `af-datalocker-your-bucket-name` |
| 스토리지 소유권 | 앱스플라이어 | 마케터 |
| 스토리지 플랫폼 | AWS | AWS, GCS, Azure, Yandex, BigQuery, Snowflake |
| 사용자가 데이터에 액세스하기 위한 자격 증명 | 앱스플라이어 계정 관리자에게 제공되는 데이터 락커 사용자 인터페이스에서 이용 가능합니다. | 앱스플라이어에는 알려지지 않습니다. 클라우드 제공업체가 제공하는 자격 증명을 사용하십시오. |
| 데이터 보존 | 데이터는 14일 이후에 삭제됩니다. | 마케터 책임 |
| 데이터 삭제 요청 | 앱스플라이어 책임 | 마케터 책임 |
| 보안 | 앱스플라이어는 스토리지를 제어합니다. 고객은 읽기 액세스 권한을 가집니다. | 마케터는 스토리지를 제어합니다.<ul><li>**AWS**: 앱스플라이어는 버킷에 대한 GetObject, ListBucket, DeleteObject, PutObject 권한이 필요합니다. 버킷은 앱스플라이어 사용 전용이어야 합니다. 다른 목적으로 사용하지 마십시오.</li><li>**GCS**: <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup">GCS 설정 아티클</Anchor>을 참조하십시오.</li></ul> |
| 스토리지 용량 | 앱스플라이어에서 관리 | 마케터가 관리 |
| 버킷 정책을 포함한 VPC 엔드 포인트를 사용한 액세스 제어 | 해당 사항 없음. | [선택 사항] AWS에서 버킷 수준에서 VPC 엔드포인트 보안을 구현하는 경우 앱스플라이어 서버 목록을 허용해야 합니다. |

<div id="notice-to-security-officers-in-the-case-of-customer-controlled-storage" />

#### **고객이 관리하는 스토리지의 경우 보안 담당자 알림 사항**

효과적 관리를 위해 다음과 같은 사항을 고려해야 합니다.

* 버킷 또는 대상은 앱스플라이어 사용 전용입니다. 다른 엔터티는 해당 대상에 기록할 수 없습니다.
* 데이터를 작성한 후 25시간 후에 대상의 데이터를 삭제할 수 있습니다.
* 대상에 기록된 데이터는 이미 서버에 있는 데이터의 사본입니다. 데이터는 회사 리텐션 정책에 따라 서버에 계속 남아 있습니다.
* 기술적인 이유로 인해, 때때로 데이터는 삭제되고 다시 작성됩니다. 이러한 이유로 인해, 삭제 및 리스트 권한이 필요합니다. 어떤 권한도 사용자에게 보안 위험이 되지 않습니다. 리스트의 경우, 앱스플라이어가 버킷에 기록할 수 있는 유일한 엔티티입니다. 삭제의 경우, 데이터를 재생성할 수 있습니다.
* 추가 정보에 대해서는 [hello@appsflyer.com](mailto:hello@appsflyer.com) 또는 CSM을 통해 보안 팀에 문의할 수 있습니다.

</Accordion>

<div id="multipleconnections-principles-more-than-one-destination" />

<Accordion title="다중 연결 원칙(하나 이상의 대상)">

데이터 락커에서 데이터의 일부 또는 전체를 2개의 대상(연결 설정에서 정의)으로 보낼 수 있습니다. 예를 들어 앱 A 데이터를 AWS로 보내고 앱 B 데이터를 GCS로 보낼 수 있습니다.

각 연결은 대상 위치를 포함한 데이터 락커 설정의 완전한 세트로 구성됩니다. 연결 설정은 서로 독립적입니다.

연결을 관리할 때 다음을 고려하십시오.

* 데이터 락커 설정에서 연결은 탭에 표시됩니다. 각 연결에는 연결을 관리할 수 있는 자체 설정 탭이 있습니다. 각 탭의 아이콘은 스토리지 유형을 나타냅니다.
* 연결 세부사항을 확인하거나, 연결을 복제 혹은 삭제하려면, ⋮ (옵션)을 클릭하세요.

</Accordion>

<div id="additional-information" />

## 추가 정보

<div id="track-connection-changes-in-the-audit-log" />

<Accordion title="감사 로그에서 연결 변경 사항을 추적합니다.">

데이터 락커 연결 변경 사항은 앱스플라이어 대시보드의 보안 센터에서 확인할 수 있는 감사 로그에서 확인할 수 있습니다. 감사 로그를 사용하여 변경이 이루어졌는지, 언제 발생했는지, 누가 했는지 확인합니다. 이것은 서포트팀에 연락할 필요 없이 누락된 데이터나 예상치 못한 연결 변경과 같은 문제를 해결하는 데 도움이 될 수 있습니다.

다음의 연결 수명 주기 이벤트가 추적됩니다:

* 새 연결 생성됨
* 연결 업데이트됨
* 연결 비활성화됨
* 연결 삭제됨

**감사 로그에 액세스하는 방법:**

1. 상단 탐색 바에서 <Image alt="HQ1 2025-05-05 10.48.04.png" src="https://files.readme.io/b7020f3b633fb66e0e2d4988c7903426509b1fa871693cee602a39b8eb9d69d1-34955489919889.png" width="4.24%" /> 계정 메뉴를 엽니다.
2. **보안 센터를 선택합니다.**
3. **감사 로그** 섹션에서 감사 로그 보기를 클릭합니다.
4. 서비스별로 필터링: 관련 항목을 보기 위해 **Datalocker**

자세한 내용은 다음을 참조하세요. <Anchor target="_blank" href="/marketers/ko/docs/audit-log">감사 로그.</Anchor>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| **특징** | 비고 |
| --- | --- |
| 애드 네트워크 | 애드 네트워크에서는 사용할 수 없습니다. |
| 에이전시 | 에이전시에서는 사용할 수 없습니다. |
| 앱별 시간대 | 해당 사항 없음. 데이터 락커 폴더는 UTC를 기준으로 시간별로 구분됩니다. 실제 이벤트에는 UTC 시간이 포함됩니다. 필요에 따라 시간을 다른 표준시로 변환합니다. 앱의 시간대와 무관하게 이벤트 발생 시점부터 데이터 락커에 기록될 때까지의 지연 시간은 동일하게 유지됩니다. |
| 앱별 통화 | 지원되지 않음 |
| 사이즈 제한 | 적용 불가 |
| 데이터 최신성 | <Anchor target="_blank" href="/marketers/ko/docs/data-locker-advertiser-reports#로데이터raw-data-보고서">이 아티클</Anchor>에 나와있듯이 데이터는 특정 리포트 데이터 최신성에 따라 업데이트됩니다. |
| 과거 데이터 | 지원되지 않음. 과거 데이터가 필요한 경우, 일부 보고서(전부는 아님)는 Pull API를 통해 이용 가능합니다. |
| 제한된 데이터 | 일부 리포트의 필드는 개인 정보 보호로 인해 제한됩니다. <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">더 알아보기</Anchor> |
| 유저 액세스 | <Anchor target="_blank" href="/marketers/ko/docs/user-management">필수 권한을 가진 계정 사용자</Anchor>만 데이터 락커를 설정할 수 있습니다. |
| 단일 앱/여러 앱 | 다중 앱 지원. 데이터 락커는 계정 수준에서 적용됩니다. |
| 최대 연결 수 | 기본적으로 각 계정은 최대 **2개의 데이터 락커 연결**을 열 수 있습니다. 추가 연결을 요청하려면, **CSM에 연락하세요**. |

</Accordion>

<div id="troubleshooting" />

<Accordion title="문제 해결">

* **증상**: AWS CLI를 사용하여 데이터를 확보할 수 없습니다.
* **오류 메시지**: ListObjectsV2 작업 호출 중 오류가 발생했습니다(액세스 거부됨): 액세스 거부됨
* **원인**: 사용된 AWS 인증 정보가 앱스플라이어 버킷에 대한 올바른 인증 정보가 아닙니다. 사용자 머신에 여러 개의 또는 잘못된 인증 정보를 갖고 있을 때 발생할 수 있습니다.
* **해결 방안**:
  1. 버킷에 액세스 하기 위해, CLI가 아닌 [Cyber Duck](/docs/data-locker-for-marketers#cyberduck) 같은 다른 방법을 사용합니다. 사용 중인 자격 증명이 작동하는지 확인하려면 이 작업을 수행합니다. Cyberduck을 사용하여 연결할 수 있는 경우 자격 증명 캐시에 문제가 있음을 나타냅니다.
  2. <Anchor target="_blank" href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-role.html">AWS 인증 정보 캐시를 새로 고칩니다</Anchor>.  
     **AWS 스크린샷에서** ![mceclip0.png](https://files.readme.io/e6608b196c39cb71e0a02e0eabe95378f24659a1578a16fd381bfd0053ca309e-32966264043537.png)

</Accordion>

<div id="aws-data-retrieval" />

## AWS 데이터 검색

선호하는 AWS 데이터 검색 툴, AWS CLI, 혹은 다음 섹션에 소개되는 툴 중 하나를 사용하십시오. 참고! 해당 지침은 앱스플라이어 소유 버킷에 적합합니다. 귀하의 버킷에 연결하는 경우 필요에 따라 지침을 조정하십시오.

<div id="aws-cli" />

<Accordion title="AWS CLI">

**시작하기 전에**:

* 컴퓨터에 AWS CLI를 설치합니다.
* 앱스플라이어에서 데이터 락커로 이동하여, 인증 정보 창에 포함된 정보를 가져옵니다.

**AWS CLI를 사용하려면**:

1. 터미널을 엽니다. Windows에서 수행하려면, &lt;Windows>+&lt;R>, **OK**를 클릭합니다.  
   명령행 창이 열립니다.
2. **aws configure**를 입력합니다.
3. 인증 정보 창에 표시된 대로, AWS Access Key를 입력합니다.
4. 인증 정보 창에 표시된 대로, AWS Secret Key를 입력합니다.
5. **eu-west-1**을 입력합니다.
6. 엔터를 누릅니다(없음).

필요할 경우, 다음 CLI 명령을 사용합니다.

다음 명령에서 `{home-folder}`의 값을 찾을 수 있습니다.

**버킷의 폴더를 나열하는 방법은 다음과 같습니다.**

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/
```

<div id="listing-files-and-folders" />

### 파일 및 폴더 나열하기

데이터 락커 버킷에는 세 가지 유형의 폴더가 있습니다.

* 리포트 유형
* 날짜 `dt=`
* 시간 `h=`

특정 리포트 유형에 해당하는 모든 리포트를 나열하려면:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/
```

특정 날짜의 특정 리포트 유형에 해당하는 모든 리포트를 나열하려면:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17
```

특정 날짜의 특정 시간대에 속한 특정 리포트의 모든 리포트를 나열하려면:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17/h=23
```

특정 날짜의 파일을 다운로드하는 방법은 다음과 같습니다.

```bash
aws s3 cp s3://af-ext-reports/<home-folder>/data-locker-hourly/t=installs/dt=2020-08-01/h=9/part-00000.gz ~/Downloads/
```

</Accordion>

<div id="cyberduck" />

<Accordion title="Cyberduck">

**시작하기 전에**:

* Cyberduck 클라이언트를 설치합니다.
* 앱스플라이어에서 데이터 락커로 이동하여 인증 정보 창에 포함된 정보를 가져옵니다.

**Cyberduck을 설정하려면**:

1. Cyberduck에서 Action을 클릭합니다.
2. **New Bookmark(새 북마크)** 를 선택하면, 창이 열립니다.
3. 첫 번째 필드(아래 스크린샷에서 [1]로 표시됨)에서 **Amazon S3.** [![DataDuckSmall2.png](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)를 선택합니다.
4. 다음과 같이 필드를 완성합니다.
   * **닉네임:** 자유 텍스트
   * **서버:** s3.amazonaws.com
   * **액세스 키 ID: 앱스플라이어 인증 정보 창에 표시된 AWS Access Key를 복사합니다.**
   * **비밀 액세스 키:** 앱스플라이어 인증 정보 창에 표시된 Bucket Secret key를 복사합니다.
   * **경로**: `{Bucket Name}/{Home Folder}` 예: **af-ext-reports/1234-abc-ffffffff**
5. 창을 닫습니다. 창의 우측 상단 모서리의 X를 클릭합니다.
6. 연결을 선택합니다.  
   데이터 디렉토리가 표시됩니다.

</Accordion>

<div id="amazon-s3-browser" />

<Accordion title="Amazon S3 browser">

**시작하기 전에**:

* Amazon S3 Browser를 설치합니다.
* 앱스플라이어에서 데이터 락커로 이동하여 인증 정보 창에 포함된 정보를 가져옵니다.

**Amazon S3 Browser를 설정하려면**:

1. S3 브라우저에서 **계정** > **새 계정 추가**를 클릭합니다.  
   새 계정 추가 창이 열립니다. [![mceclip0.png](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)
2. 다음과 같이 필드를 완성합니다.
   * **계정 이름**: 자유 텍스트.
   * **액세스 키 ID:** 앱스플라이어 인증 정보 창에 표시된 AWS Access Key를 복사합니다.
   * **비밀 액세스 키:** 앱스플라이어 인증 정보 창에 표시된 버킷 비밀 키를 복사합니다.
   * 비밀번호 포함 **액세스 키 암호화**를 선택하고, 비밀번호를 입력합니다. 이 비밀번호를 기록해두십시오.
   * **보안 전송 사용**을 선택합니다.
3. **변경 사항 저장(Save changes)** 을 클릭합니다.
4. **버킷** > **외부 버킷** 추가를 클릭합니다.  
   외부 버킷 추가 창이 열립니다.  
   <Image alt="mceclip2.png" src="https://files.readme.io/88dd43f62dbd68d0295b52a7f7b9b09449bd915e6a6d52703c24a50583e05a6e-32966264054929.png" width="433px" />
5. 버킷 이름/strong> 을 입력합니다. 버킷 이름은 다음 형식을 가집니다: `{버킷 이름}/{홈 폴더}`. 버킷 이름과 홈 폴더에 필요한 값은 자격 증명 창에 표시됩니다.
6. 클릭 **외부 버킷 추가.** 버킷이 생성되고 창의 왼쪽 패널에 표시됩니다.  
   이제 데이터 락커 파일에 액세스할 수 있습니다.

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/data-locker-advertiser-reports">데이터 락커를 통해 사용 가능한 리포트</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">올바른 로데이터 전달 툴 선택하기</Anchor>

<div data-zendesk-anchors="data-locker=%EA%B0%9C%EC%9A%94 h_01HE2S6FANNTNB580CMHNX34YA=%EA%B0%9C%EC%9A%94 data-locker%E2%80%94features=data-locker-features h_01HE2S6FANQH2GZ11S8S87H0YH=data-locker-features h_01HE2S6FAN6BFPJSZJBEE9P5VK=reports-available-via-data-locker set-data-locker-report-settings=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01JS45N2DNWZBHP5PH8ZG6FBTF=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01JS45N2DNEZZJRF2RKG1RM9NK=1-set-up-your-cloud-service h_01JS45N2DNVA0SHBA49G42GNFE=2-add-a-connection-to-your-cloud-service h_01K22P5FWJ96CPFJPW0XDCHNNJ=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01JS4ASE6J6X1DD33PEGQAPXPA=aws-cloud-bucket-connection h_01JS4ASE6J587JPHAMCSBA2Z92=gcs-cloud-bucket-connection h_01JS4ASE6J4NC7M0TRFDT7F2X7=azure-cloud-bucket-connection h_01JS4ASE6JKFTM3FYAEKFHRW2M=yandex-cloud-bucket-connection h_01JS4ASE6JKV8WJG68RMHKVCE5=bigquery-data-warehouse-connection h_01JS4ASE6JBNE5BK04QDRM7CW4=snowflake-data-warehouse-connection h_01JTFRHNRRJB76JBXXT1TBNRBY=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-1 h_01JS45N2DN8JTMQCK76PDBBWA4=3-set-the-report-output-settings h_01JSBTCZ5569RCV6W6QWT400R7=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-2 h_01JS45N2DNMQAGFVHDDD5JGF2M=select-global-level-filters h_01JS45N2DN388YVP29DDBBBFBP=5-select-the-report h_01JVPJ9CG45JREBKP3ZQXKZWRZ=customize-or-duplicate h_01JS45N2DP4FK9EZYNTY2GX2GK=6-select-the-report-fields h_01JS45N2DPN7B73X0TRC82JW87=7-select-the-reportlevel-filters h_01JS45N2DPYYABS9NXFXP23ARA=8-remove-legacy-fields h_01JS45N2DPYNBG9VPCZJ481DFE=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-3 nonempty-legacy-fields=%EB%B9%84%EC%96%B4-%EC%9E%88%EC%A7%80-%EC%95%8A%EC%9D%80-%EB%A0%88%EA%B1%B0%EC%8B%9C-%ED%95%84%EB%93%9C h_01JSCC6KZNKJAVYSFCDDSE80YW=%EB%B9%84%EC%96%B4-%EC%9E%88%EC%A7%80-%EC%95%8A%EC%9D%80-%EB%A0%88%EA%B1%B0%EC%8B%9C-%ED%95%84%EB%93%9C h_01JS45N2DPH1QAREYGN5H20T8R=9-save-the-connection h_01JS45N2DPNPXAEZ74J0ETP7BS=%EC%A4%91%EC%9A%94 set-user-permissions=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B6%8C%ED%95%9C-%EC%84%A4%EC%A0%95 h_01KH8D60TDTNS4EWNXJ4JPGXZ2=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B6%8C%ED%95%9C-%EC%84%A4%EC%A0%95 manage-data-locker-access-and-ownership-admins=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4-%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%8F-%EC%86%8C%EC%9C%A0%EA%B6%8C-%EA%B4%80%EB%A6%AC-%EA%B4%80%EB%A6%AC%EC%9E%90 h_01KH8D60TEFX2MCW00JT94F9AQ=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4-%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%8F-%EC%86%8C%EC%9C%A0%EA%B6%8C-%EA%B4%80%EB%A6%AC-%EA%B4%80%EB%A6%AC%EC%9E%90 give-data-locker-access=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4-%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B6%80%EC%97%AC%ED%95%98%EC%84%B8%EC%9A%94 h_01KH8D60TE541XMXWCVK0HZTJA=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4-%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B6%80%EC%97%AC%ED%95%98%EC%84%B8%EC%9A%94 manage-ownership-and-editors=%EC%86%8C%EC%9C%A0%EA%B6%8C-%EB%B0%8F-%ED%8E%B8%EC%A7%91%EC%9E%90-%EA%B4%80%EB%A6%AC h_01KH8D60TF69FN7KMBPMZHBW27=%EC%86%8C%EC%9C%A0%EA%B6%8C-%EB%B0%8F-%ED%8E%B8%EC%A7%91%EC%9E%90-%EA%B4%80%EB%A6%AC review-filters-after-changing-ownership=%EC%86%8C%EC%9C%A0%EA%B6%8C-%EB%B3%80%EA%B2%BD-%ED%9B%84-%EA%B2%80%ED%86%A0-%ED%95%84%ED%84%B0 h_01KH8D60TFYMEY8FEPR4YKJRYJ=%EC%86%8C%EC%9C%A0%EA%B6%8C-%EB%B3%80%EA%B2%BD-%ED%9B%84-%EA%B2%80%ED%86%A0-%ED%95%84%ED%84%B0 h_01KH8D60TGVN75TMS9QES0G6CQ=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-4 architecture=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80-%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98 data-storage-architecture=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80-%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98 h_01HE2S6FAN4H9DQ5HBTKSNJ72B=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80-%EC%95%84%ED%82%A4%ED%85%8D%EC%B2%98 h_01HE2S6FANY1FWEY6Y34T85GHM=overview h_01HE2S6FANDJ65MZ2H2FBAZYJR=folder-structure h_01HE2S6FAN7PBZ8M86FQVSN5KQ=hourly-folders h_01HE2S6FAN366V8HNCY4PFNTFG=version-folders h_01HE2S6FANHFZMCY3WZBZB9QMP=app-segregation h_01HE2S6FANVDFH9S9JN8E9J7ES=data-files h_01HE2S6FAN8ZDF5N4ECKKN1D1H=storage-options h_01HE2S6FAN2HY7V3G9NS9XCVE1=%EC%A3%BC%EC%9D%98 notice-to-security-officers-in-the-case-of-customercontrolled-storage=%EA%B3%A0%EA%B0%9D%EC%9D%B4-%EA%B4%80%EB%A6%AC%ED%95%98%EB%8A%94-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80%EC%9D%98-%EA%B2%BD%EC%9A%B0-%EB%B3%B4%EC%95%88-%EB%8B%B4%EB%8B%B9%EC%9E%90-%EC%95%8C%EB%A6%BC-%EC%82%AC%ED%95%AD h_01HE2S6FANRVGYPRWWFA50JAQ4=%EA%B3%A0%EA%B0%9D%EC%9D%B4-%EA%B4%80%EB%A6%AC%ED%95%98%EB%8A%94-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80%EC%9D%98-%EA%B2%BD%EC%9A%B0-%EB%B3%B4%EC%95%88-%EB%8B%B4%EB%8B%B9%EC%9E%90-%EC%95%8C%EB%A6%BC-%EC%82%AC%ED%95%AD h_01HE2S6FANBRXA0NS4E8SP3618=multipleconnections-principles-more-than-one-destination additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HE2S6FAP4SA77B0SX7R8JMTY=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01JTFQMKN0046SNBB4YSRJMQG9=track-connection-changes-in-the-audit-log h_01HE2S6FAP6FKAJCW92JVWD828=traits-and-limitations h_01HE2S6FAPJC20G7YZSRWP5E34=troubleshooting aws-data-retrieval=aws-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B2%80%EC%83%89 h_01HE2S6FAPJMKX567HSAR16TCN=aws-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B2%80%EC%83%89 h_01HE2S6FAPB5MW09Y4HKFV3RM8=aws-cli listing-files-and-folders=%ED%8C%8C%EC%9D%BC-%EB%B0%8F-%ED%8F%B4%EB%8D%94-%EB%82%98%EC%97%B4%ED%95%98%EA%B8%B0 h_01HE2S6FAP31H9NK6V870FGXZF=%ED%8C%8C%EC%9D%BC-%EB%B0%8F-%ED%8F%B4%EB%8D%94-%EB%82%98%EC%97%B4%ED%95%98%EA%B8%B0 h_01HE2S6FAP2E2TW4F5PJ4226Q0=cyberduck h_01HE2S6FAP74NG5VNEWKWXXJX2=amazon-s3-browser h_01HE7RB5N99WJ3XP69Z69H81AD=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
