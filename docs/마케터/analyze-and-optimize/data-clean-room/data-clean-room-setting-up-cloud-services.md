---
title: Data Clean Room - 클라우드 서비스 설정
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-03-06T08:23:55Z'
  edited_at: '2026-10-14T10:36:46Z'
  id: 4591167507217
  locale: ko
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ko/articles/4591167507217
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 요약: 하나 이상의 데이터 웨어하우스(BigQuery, Snowflake) 및/또는 클라우드 스토리지 버킷(Amazon S3, GCS)을 설정하여 Data Clean Room에 데이터를 공유하고 리포트를 수신합니다.

<div id="overview" />

## 개요

DCR(Data Clean Room) 사용 준비에는 다음 설정이 포함됩니다.

* DCR이 사용자의 시스템에서 퍼스트파티 데이터를 읽는 클라우드 서비스/위치(커스텀 소스). 이러한 위치는 **인바운드 연결**을 만드는 데 사용됩니다.
* 처리 후 DCR이 리포트를 전달하는 클라우드 서비스/위치입니다. 이러한 위치는 **아웃바운드 연결**을 만드는 데 사용됩니다.

인바운드 또는 아웃바운드 연결 만들기는 2단계 프로세스입니다.

* **1 단계 –** 선택한 클라우드 서비스의 인터페이스를 사용하여 DCR과 함께 사용할 수 있도록 준비합니다(본 기사).
* **#2단계 –** 앱스플라이어 플랫폼을 사용하여 DCR에 연결합니다. (<Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-connections">Data Clean Room - 연결 작업</Anchor> 참조).

<div id="note" />

> 📘 **참고사항**
>
> <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-sources#source-format">Data Clean Room—소스</Anchor> 데이터 요구사항에 대한 전체 정보는 소스 작업을 참조하십시오.
>
> * 테이블 열(*데이터 웨어하우스의 원본용)*
> * 파일 이름 및 형식*(Cloud Storage 버킷의 소스용)*

<div id="supported-cloud-services" />

### 지원되는 클라우드 서비스

DCR에 대한 인바운드 및 아웃바운드 연결에 두 가지 유형의 클라우드 서비스가 지원됩니다.

인바운드 및 아웃바운드 연결에 이러한 서비스 중 하나 또는 임의의 조합을 사용할 수 있습니다.

<div id="important" />

> 🚧 **중요!**
>
> * 단일 리포트에 여러 커스텀 소스를 사용하려는 경우 해당 소스는 클라우드 저장소 버킷에 있어야 합니다.
> * 인바운드 및 아웃바운드 연결 모두에 대해 Amazon S3 또는 GCS에서 동일한 클라우드 스토리지 버킷을 사용하는 것은 매우 일반적입니다. [해당 설정에 대한 특별 지침](/docs/data-clean-room-setting-up-cloud-services#인바운드-및-아웃바운드-연결-모두에-대해-동일한-클라우드-저장소-버킷-설정)을 반드시 따라야 합니다.

<div id="setting-up-cloud-services-for-inbound-connections" />

## 인바운드 연결을 위한 클라우드 서비스 설정

다음 탭의 지침에 따라 DCR 인바운드 연결에 사용할 클라우드 서비스를 선택하여 준비합니다.

<div id="data-warehouses--bigquery-and-snowflake" />

### 데이터 웨어하우스 – BigQuery와 Snowflake

<div id="bigquery-inbound" />

<Accordion title="빅쿼리">

**참고:** 일러두기: 다음 절차는 Google Cloud 관리자가 수행해야 합니다.

**데이터 세트 생성 및 DCR 권한 부여 방법:**

1. Google Cloud 콘솔에 로그인합니다.
2. BigQuery 페이지로 이동합니다.
3. 신규 또는 기존 Google Cloud 프로젝트에서 DCR만 사용할 데이터세트를 생성합니다.

   2. **데이터 세트 만들기**를 선택합니다.

      <Image align="center" alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. * 문자, 숫자 및 밑줄(\_)만으로 자신에게 맞는 이름을 사용할 수 있습니다.
        * **권장 사항:** 권장사항: 데이터 세트가 인바운드 연결에 사용되고 있음을 알 수 있는 이름을 사용하십시오.
      * 테이블이 만료된 후 DCR이 소스를 읽을 수 없으므로 **테이블 만료 활성화** 옵션을 사용하지 **않는** 것이 좋습니다.
4. 다음과 같이 데이터 세트에 대한 DCR 권한을 부여합니다.

   2. **공유**를 선택합니다.
   4. **주요 사용자 추가** 섹션에서 **새 주요 사용자** 필드에 다음 계정을 입력합니다.  
      `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. **역할 할당** 섹션에서 **BigQuery > BigQuery 메타데이터 뷰어**를 선택합니다.

      <Image align="center" alt="BQ_data_viewer.png" src="https://files.readme.io/beec60ee830957ff265f8046875d1b8fa006a2c0cb60427ac969d7d45efa8b5b-14964740088721.png" width="311px" />
   6. **저장**을 클릭하세요.
   7. **닫기**를 클릭하여 오른쪽 패널을 닫습니다.

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

**참고:** 참고: Snowflake **계정 관리자**가 다음 절차를 수행해야 합니다.

**DCR에서 사용할 비공개 공유 생성 방법:**

1. DCR과 공유하려는 데이터가 포함된<Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Snowflake 계정에 로그인</Anchor>합니다.
2. 사용자 역할을 **계정 관리자**로 전환합니다.
3. 왼쪽 패널에서 비공개 공유를 선택합니다.
4. 페이지가 열리면 계정에서 공유탭을 선택합니다.

   <Image align="center" alt="snowflake_private_sharing.png" src="https://files.readme.io/e99ddd6acf3a3714ea1818fc1d28489b0ea458abac3519d6e4fe67ab643de5bb-13879858362257.png" width="609px" />
5. <Image align="center" alt="snowflake_create_direct_share.png" src="https://files.readme.io/0a33cddd326d03a13da19a1e1b4d75a7f6a9c5479dad2fdcad52f111bc5b4e14-13879858320913.png" width="219px" />
6. DCR과 공유하려는 테이블 및/또는 뷰를 선택한 다음 완료를 클릭합니다.
7. 필요에 따라 보안 공유 식별자를 변경하고 선택사항으로 설명을 추가합니다.
8. 이름으로 사용자 영역의 계정 추가필드에 Snowflake 계정 지역에 따라 다음 앱스플라이어 Snowflake 계정 중 하나를 입력합니다. 

| 지역 | 앱스플라이어 계정 |
| --- | --- |
| EU 서부(eu-west-1) | QL63117 |
| 미국 동부 - 버지니아 북부(us-east-1) | MWB70410 |
| 미국 동부 - 오하이오(us-east-2) | BM15378 |

9. **공유 만들기** 버튼을 클릭합니다.

</Accordion>

<div id="code-snippet" />

<div id="step-4" />

<div id="cloud-storage-buckets--amazon-s3-and-gcs" />

### 클라우드 스토리지 버킷 – Amazon S3 및 GCS

하나 이상의 버킷을 사용하여 DCR에 데이터를 업로드할 수 있습니다(Amazon S3, GCS 또는 둘 다). 그러나 대부분의 경우 가장 관리하기 쉬운 구조에는 단일 클라우드 서비스의 단일 버킷이 포함됩니다.

* [다음 지침](/docs/data-clean-room-setting-up-cloud-services#인바운드-및-아웃바운드-연결-모두에-대해-동일한-클라우드-저장소-버킷-설정)에 따라 인바운드 및 아웃바운드 연결 모두에 동일한 버킷을 설정할 수 있습니다.

<span id="both-cloud-services"></span>다음 요구 사항은 두 클라우드 서비스의 버킷과 관련이 있습니다.

* 사용 버킷은 앱스플라이어 Data Clean Room 전용이어야 합니다. 즉, 다른 서비스는 이 버킷에 데이터를 쓸 수 없습니다.
* 권한 앱스플라이어 DCR 서비스에는 버킷 권한이 부여되어야 합니다. 아래의 각 클라우드 서비스에 대한 탭에서 이러한 권한 부여에 대한 지침을 참조하십시오.
* **이름:**
  * 예: `af-dcr-example-bucket`
* <span id="dcr-naming-requirements"></span>DCR 이름 지정 요구 사항 다음 이름 지정 요구 사항은 모든 DCR 데이터 엔터티(버킷, 폴더 및 파일)에 적용됩니다.
  * 최대 길이: 2-40자
  * 유효한 문자:

    * 숫자 `(0-9)`(0-9) (0-9), *이름의 첫 문자가 될 수 없습니다.*
    * 하이픈 `(-)`(-) (-) *이름의 첫 번째 문자가 될 수 없습니다.*
    * 유효하지 않은 문자:
      * 공백
      * 기타 모든 기호 또는 특수 문자
    * 특별한 목적으로만 사용되는 문자:
      * * 등호 `(=)`(=) (=), *날짜 및 버전 폴더 이름에서* <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version">필요한 경우에만</Anchor>
        * 밑줄`(_)`(\_) (\_), *다중 부분 GZIP 파일의 일부를* <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-sources#file-format">식별하거나 \_SUCCESS 파일</Anchor>*의 이름을 지정하는 데* <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-sources#_success-files">사용되는 경우에만</Anchor>
        * 점`(.)`(.) (.), *파일 이름 확장자*`(.csv, .gzip)`(.csv, .gzip) (.csv,> 바로 앞

<div id="amazon-s3-inbound" />

<Accordion title="Amazon S3">

**참고:** 일러두기: 다음 절차는 AWS 관리자가 수행해야 합니다.

**버킷 생성 및 앱스플라이어에 권한 부여 방법:**

1. AWS 콘솔에 로그인합니다.
2. S3 서비스로 이동합니다.
3. 버킷 생성 방법:
   1. **버킷 생성(Create Bucket)** 을 클릭합니다.
   2. **버킷 이름**을 `af-dcr-`af-dcr-af-dcr- 또는 `af-datalocker-`af-dl-af-datalocker-로 시작하고 텍스트를 입력하여 완성합니다(위의 [DCR 이름 지정 요구 사항](/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements)에 따라).
   3. **버킷 생성(Create Bucket)** 을 클릭합니다.
4. 앱스플라이어 버킷 권한 부여 방법:
   1. 생성한 버킷을 선택합니다.
   2. **권한** 탭으로 이동합니다.
   3. **버킷 정책** 섹션에서 **편집하기**를 클릭하세요.  
      버킷 정책 편집/strong> 창이 열립니다.
   4. 다음 코드 스니펫을 창에 붙여 넣습니다.

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF-DCR-DL",
            "Effect": "Allow",
            "Principal": {
              "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
              ]
            },
            "Action": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Resource": [
              "arn:aws:s3:::af-dcr-mybucket",
              "arn:aws:s3:::af-dcr-mybucket/*"
            ]
          }
        ]
      }
      ```
5. 스니펫에서 *`af-dcr-mybucket`af-dcr-mybucketaf-dcr-mybucket*(표시되는 두 줄)을 생성한 버킷의 이름으로 바꿉니다.  
   **주의!** 스니펫에서 버킷 이름을 바꿀 때 버킷 이름이 나타나는 두 번째 줄의 /*`/*`를 덮어쓰지 않도록 하십시오/* .
6. **변경 사항 저장**을 클릭하세요.

</Accordion>

<div id="gcs-inbound" />

<Accordion title="GCS">

**참고:** 일러두기: 다음 절차는 Google Cloud 관리자가 수행해야 합니다.

**버킷 생성 및 앱스플라이어에 권한 부여 방법:**

1. GCS 콘솔에 로그인합니다.
2. Cloud Storage 브라우저 페이지로 이동합니다.
3. 버킷 생성 방법:
   1. **버킷 생성**을 클릭합니다.
   2. **버킷 생성** 페이지에서 버킷 정보를 입력하십시오. 버킷 이름을 af-dcr- 또는 af-dl-로 시작하고 텍스트를 입력하여 포함합니다(위의 `af-dcr-`DCR 이름 지정 요구 사항af-dcr-에 따라).
   3. **계속**을 클릭합니다.
   4. **생성**을 클릭하세요.
4. 앱스플라이어 버킷 권한 부여 방법:
   1. 생성한 버킷을 선택합니다.
   2. **권한** 탭으로 이동합니다.
   3. **권한** 섹션에서 **+ 추가**를 클릭합니다.  
      **회원 추가** 창이 열립니다.
   4. `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. **역할** 목록에서 **클라우드 스토리지** > **스토리지 관리자**를 선택하십시오.  

      <Image align="center" alt="dcr_gcs_permissions.png" src="https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png" />
   6. **저장**을 클릭하세요.

</Accordion>

<div id="setting-up-cloud-services-for-outbound-connections" />

## 아웃바운드 연결을 위한 클라우드 서비스 설정

DCR은 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers">앱스플라이어 데이터 락커</Anchor>를 사용하여 선택한 클라우드 서비스에 리포트를 제공합니다.

* **참고:** DCR 리포트를 수신하는 데 데이터 락커에 대한 프리미엄 구독이 필요하지 않습니다. 데이터 락커를 통해 다른 앱스플라이어 리포트를 수신하려면 CSM에 문의하거나 [hello@appsflyer.com](mailto:hello@appsflyer.com)로 이메일을 보내주십시오.

DCR 리포트는 클라우드 서비스의 하나 이상의 위치로 전달될 수 있습니다(인바운드 연결에 동일한 서비스를 사용하는지 여부에 관계없이). 다음 탭의 지침에 따라 아웃바운드 연결과 함께 사용할 수 있도록 준비합니다.

<div id="data-warehouses--bigquery-and-snowflake-1" />

### 데이터 웨어하우스 – BigQuery와 Snowflake

<div id="bigquery-outbound" />

<Accordion title="빅쿼리">

**참고:** 일러두기: 다음 절차는 Google Cloud 관리자가 수행해야 합니다.

**데이터 세트 생성 및 데이터 락커 권한 부여 방법:**

1. Google Cloud 콘솔에 로그인합니다.
2. BigQuery 페이지로 이동합니다.
3. 신규 또는 기존 Google Cloud 프로젝트에서 데이터 락커에서만 사용할 데이터세트를 생성합니다.

   2. **데이터 세트 만들기**를 선택합니다.

      <Image align="center" alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. * 문자, 숫자 및 밑줄(\_)만으로 자신에게 맞는 이름을 사용할 수 있습니다.
        * **권장 사항:** 권장사항: 데이터 세트가 아웃바운드 연결에 사용되고 있음을 알 수 있는 이름을 사용하십시오.
      * 테이블이 만료된 후 데이터 락커는 데이터 세트에 대한 리포트를 쓸 수 없으므로 **테이블 만료 활성화** 옵션을 사용하지 **않는** 것이 좋습니다.
4. 데이터 세트에 대한 데이터 락커 권한 부여 방법:

   2. **공유**를 선택합니다.
   4. **주요 사용자 추가** 섹션에서 **새 주요 사용자** 필드에 다음 계정을 입력합니다.  
      `datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com`
   5. **역할 할당** 섹션에서 **BigQuery > BigQuery 데이터 편집기**를 선택합니다.

      <Image align="center" alt="BQ_data_editor.png" src="https://files.readme.io/cc26288d02f10805c971167d42d77efc9c7702f7fe231724b66eddd9b1b0e252-13879852726929.png" width="323px" />
   6. **저장**을 클릭하세요.
   7. **닫기**를 클릭하여 오른쪽 패널을 닫습니다.

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

아웃바운드 연결을 위한 Snowflake를 준비하는 절차는 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-connections#snowflake-outbound">아웃바운드 연결 자체를 만드는 절차</Anchor>와 함께 완료됩니다.

</Accordion>

<div id="cloud-storage-buckets--amazon-s3-and-gcs-1" />

### 클라우드 스토리지 버킷 – Amazon S3 및 GCS

아웃바운드 연결을 위해 클라우드 스토리지 버킷을 준비하는 절차는 [인바운드 연결을](/docs/data-clean-room-setting-up-cloud-services#인바운드-연결을-위한-클라우드-서비스-설정) 위해 준비하는 절차와 매우 유사합니다(두 클라우드 스토리지 서비스와 관련된 지침 포함).

아래 탭의 지침은 **아웃바운드 연결에만** 버킷을 사용하는 경우에 적용됩니다.

* 인바운드 및 아웃바운드 연결 모두에 동일한 버킷을 사용하는 경우 [해당 설정에 대한 특별 지침을](/docs/data-clean-room-setting-up-cloud-services#인바운드-및-아웃바운드-연결-모두에-대해-동일한-클라우드-저장소-버킷-설정) 따릅니다.

<div id="amazon-s3-outbound" />

<Accordion title="Amazon S3">

[인바운드 연결을 위한 Amazon S3 버킷](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound) 생성 지침을 따르십시오(해당 절차는 변경하지 않음).

</Accordion>

<div id="gcs-outbound" />

<Accordion title="GCS">

[인바운드 연결을 위한 GCS 버킷](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound) 생성 안내를 따르십시오.   
`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

</Accordion>

<div id="setting-up-the-same-cloud-storage-bucket-for-both-inbound-and-outbound-connections" />

## 인바운드 및 아웃바운드 연결 모두에 대해 동일한 클라우드 저장소 버킷 설정

앞서 언급했듯이 인바운드 및 아웃바운드 연결 모두에 대해 Amazon S3 또는 GCS에서 동일한 버킷을 사용하는 것이 일반적입니다.

이 설정에 대한 지침은 [인바운드 연결에 대한 지침](/docs/data-clean-room-setting-up-cloud-services#인바운드-연결을-위한-클라우드-서비스-설정)과 약간만 다릅니다.  그러나 다음과 같은 경우에 따라 다릅니다.

* DCR 인바운드 및 아웃바운드 연결에 사용할 새 버킷 생성; ***또는***
* 이전에 데이터 락커에만 사용되었던 버킷을 인바운드 및 아웃바운드 DCR 연결 모두에 사용되는 버킷으로 수정

이 두 시나리오에 대한 지침은 아래 탭에 포함되어 있습니다.

<div id="amazon-s3-inbound-outbound" />

<Accordion title="Amazon S3">

<div id="creating-a-new-bucket-for-inboundoutbound-connections" />

#### 인바운드/아웃바운드 연결을 위한 새 버킷 생성

[인바운드 연결을 위한 Amazon S3 버킷](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound) 생성 지침을 따르십시오(해당 절차는 변경하지 않음).

<div id="modifying-an-existing-bucket-previously-used-only-for-data-locker" />

#### 이전에 데이터 락커에만 사용되었던 기존 버킷 수정

이전에 데이터 락커에만 사용했던 기존 버킷을 수정하려면 버킷 권한을 변경해야 합니다(DCR과 데이터 락커 모두에 대한 액세스 허용).

**버킷 권한 변경 방법:**

1. AWS 콘솔에 로그인합니다.
2. S3 서비스로 이동합니다.
3. 이전에 데이터 락커에만 사용된 버킷을 선택합니다.
4. **권한** 탭으로 이동합니다.
5. **버킷 정책** 섹션에서 **편집하기**를 클릭하세요.  
   버킷 정책 편집/strong> 창이 열립니다.
6. 기간의 내용을 다음 코드 조각으로 **바꿉**니다.

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "AF-DCR-DL",
         "Effect": "Allow",
         "Principal": {
           "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
           ]
         },
         "Action": [
           "s3:GetObject",
           "s3:ListBucket",
           "s3:DeleteObject",
           "s3:PutObject"
         ],
         "Resource": [
           "arn:aws:s3:::af-dcr-mybucket",
           "arn:aws:s3:::af-dcr-mybucket/*"
         ]
       }
     ]
   }
   ```

   * 스니펫에서 *`af-dcr-mybucket`af-dcr-mybucketaf-dcr-mybucket*(표시되는 두 줄)을 생성한 버킷의 이름으로 바꿉니다.
   * **주의!** 스니펫에서 버킷 이름을 바꿀 때 버킷 이름이 나타나는 두 번째 줄의 /*`/*`를 덮어쓰지 않도록 하십시오/* .
7. **변경 사항 저장**을 클릭하세요.

</Accordion>

<div id="gcs-inbound-outbound" />

<Accordion title="GCS">

<div id="creating-a-new-bucket-for-inboundoutbound-connections-1" />

#### 인바운드/아웃바운드 연결을 위한 새 버킷 생성

[인바운드 연결을 위한 GCS 버킷](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound) 생성 안내를 따르십시오.   
`appsflyer-dcr@dcr-report.iam.gserviceaccount.com`  
`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

<div id="modifying-an-existing-bucket-previously-used-only-for-data-locker-1" />

#### 이전에 데이터 락커에만 사용되었던 기존 버킷 수정

이전에 데이터 락커에만 사용했던 기존 버킷을 수정하려면 버킷 권한을 변경해야 합니다(DCR과 데이터 락커 모두에 대한 액세스 허용).

**버킷 권한 변경 방법:**

1. GCS 콘솔에 로그인합니다.
2. Cloud Storage 브라우저 페이지로 이동합니다.
3. 이전에 데이터 락커에만 사용된 버킷을 선택합니다.
4. **권한** 탭으로 이동합니다.
5. **권한** 섹션에서 + 추가를 클릭합니다.  
   **회원 추가** 창이 열립니다.
6. `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
7. **역할** 목록에서 **클라우드 스토리지** > **스토리지 관리자**를 선택하십시오.  

   <Image align="center" alt="dcr_gcs_permissions.png" src="https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png" />
8. **저장**을 클릭하세요.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01J6Y2P4CKMZ3R8WZ4X76DZ6ZY=%EA%B0%9C%EC%9A%94 h_01J6Y2P4CMJ4CXJZ3EDDXQG4Y3=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD supported-cloud-services=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4 h_01J6Y2P4CMNMTSPWDK9GGSDYMJ=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4 h_01J6Y2P4CM8VDWCD5XH91DJPYX=%EC%A4%91%EC%9A%94 setting-up-cloud-services-inbound=%EC%9D%B8%EB%B0%94%EC%9A%B4%EB%93%9C-%EC%97%B0%EA%B2%B0%EC%9D%84-%EC%9C%84%ED%95%9C-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%84%A4%EC%A0%95 h_01J6Y2P4CM61DEXMWB626X25TT=%EC%9D%B8%EB%B0%94%EC%9A%B4%EB%93%9C-%EC%97%B0%EA%B2%B0%EC%9D%84-%EC%9C%84%ED%95%9C-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%84%A4%EC%A0%95 data-warehouses-inbound=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9B%A8%EC%96%B4%ED%95%98%EC%9A%B0%EC%8A%A4--bigquery%EC%99%80-snowflake h_01J6Y2P4CMDX64XXGNS7ZP3GKZ=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9B%A8%EC%96%B4%ED%95%98%EC%9A%B0%EC%8A%A4--bigquery%EC%99%80-snowflake h_01J6Y2P4CMY5DHFEFGHQQPAPK9=bigquery-inbound h_01J6Y2P4CMMZFYDZWK82F5J65W=snowflake-inbound cloud-storage-buckets-inbound=%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80-%EB%B2%84%ED%82%B7--amazon-s3-%EB%B0%8F-gcs h_01J6Y2P4CMCJDT2W6C52MF71TB=%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80-%EB%B2%84%ED%82%B7--amazon-s3-%EB%B0%8F-gcs h_01J6Y2P4CMS2JF9Z7F13XW485F=amazon-s3-inbound code-snippet=%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80-%EB%B2%84%ED%82%B7--amazon-s3-%EB%B0%8F-gcs h_01J6Y2P4CM9Y9114CH1ESY0QPJ=gcs-inbound step-4=%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80-%EB%B2%84%ED%82%B7--amazon-s3-%EB%B0%8F-gcs setting-up-cloud-services-outbound=%EC%95%84%EC%9B%83%EB%B0%94%EC%9A%B4%EB%93%9C-%EC%97%B0%EA%B2%B0%EC%9D%84-%EC%9C%84%ED%95%9C-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%84%A4%EC%A0%95 h_01J6Y2P4CMEEG6PNM2PMEYGQ3A=%EC%95%84%EC%9B%83%EB%B0%94%EC%9A%B4%EB%93%9C-%EC%97%B0%EA%B2%B0%EC%9D%84-%EC%9C%84%ED%95%9C-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%84%A4%EC%A0%95 data-warehouses-outbound=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9B%A8%EC%96%B4%ED%95%98%EC%9A%B0%EC%8A%A4--bigquery%EC%99%80-snowflake-1 h_01J6Y2P4CMNWQ0D3EZXJZZM1EY=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9B%A8%EC%96%B4%ED%95%98%EC%9A%B0%EC%8A%A4--bigquery%EC%99%80-snowflake-1 h_01J6Y2P4CM8MVS3SZAYE2YDV2T=bigquery-outbound h_01J6Y2P4CN97P8GCV314TQ91EE=snowflake-outbound cloud-storage-buckets-outbound=%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80-%EB%B2%84%ED%82%B7--amazon-s3-%EB%B0%8F-gcs-1 h_01J6Y2P4CNZ61PG9BTCVRFZ20K=%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80-%EB%B2%84%ED%82%B7--amazon-s3-%EB%B0%8F-gcs-1 h_01J6Y2P4CN4ZRAMQ2E3R4Q4KHS=amazon-s3-outbound h_01J6Y2P4CN39GT0QT6THFAA3ZY=gcs-outbound setting-up-cloud-services-inbound-outbound=%EC%9D%B8%EB%B0%94%EC%9A%B4%EB%93%9C-%EB%B0%8F-%EC%95%84%EC%9B%83%EB%B0%94%EC%9A%B4%EB%93%9C-%EC%97%B0%EA%B2%B0-%EB%AA%A8%EB%91%90%EC%97%90-%EB%8C%80%ED%95%B4-%EB%8F%99%EC%9D%BC%ED%95%9C-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%A0%80%EC%9E%A5%EC%86%8C-%EB%B2%84%ED%82%B7-%EC%84%A4%EC%A0%95 h_01J6Y2P4CN2ARMJKRSAFZNN59G=%EC%9D%B8%EB%B0%94%EC%9A%B4%EB%93%9C-%EB%B0%8F-%EC%95%84%EC%9B%83%EB%B0%94%EC%9A%B4%EB%93%9C-%EC%97%B0%EA%B2%B0-%EB%AA%A8%EB%91%90%EC%97%90-%EB%8C%80%ED%95%B4-%EB%8F%99%EC%9D%BC%ED%95%9C-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%A0%80%EC%9E%A5%EC%86%8C-%EB%B2%84%ED%82%B7-%EC%84%A4%EC%A0%95 h_01J6Y2P4CNKC9P1FKECHZJ6AXP=amazon-s3-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections=%EC%9D%B8%EB%B0%94%EC%9A%B4%EB%93%9C%EC%95%84%EC%9B%83%EB%B0%94%EC%9A%B4%EB%93%9C-%EC%97%B0%EA%B2%B0%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%83%88-%EB%B2%84%ED%82%B7-%EC%83%9D%EC%84%B1 h_01J6Y2P4CN216K0VZSWRP699TF=%EC%9D%B8%EB%B0%94%EC%9A%B4%EB%93%9C%EC%95%84%EC%9B%83%EB%B0%94%EC%9A%B4%EB%93%9C-%EC%97%B0%EA%B2%B0%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%83%88-%EB%B2%84%ED%82%B7-%EC%83%9D%EC%84%B1 modifying-an-existing-bucket-previously-used-only-for-data-locker=%EC%9D%B4%EC%A0%84%EC%97%90-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4%EC%97%90%EB%A7%8C-%EC%82%AC%EC%9A%A9%EB%90%98%EC%97%88%EB%8D%98-%EA%B8%B0%EC%A1%B4-%EB%B2%84%ED%82%B7-%EC%88%98%EC%A0%95 h_01J6Y2P4CNDW888XTMKAMZAFCS=%EC%9D%B4%EC%A0%84%EC%97%90-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4%EC%97%90%EB%A7%8C-%EC%82%AC%EC%9A%A9%EB%90%98%EC%97%88%EB%8D%98-%EA%B8%B0%EC%A1%B4-%EB%B2%84%ED%82%B7-%EC%88%98%EC%A0%95 h_01J6Y2P4CN0MEEKG0D2SKMDZVY=gcs-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections::e1cda9c8=%EC%9D%B8%EB%B0%94%EC%9A%B4%EB%93%9C%EC%95%84%EC%9B%83%EB%B0%94%EC%9A%B4%EB%93%9C-%EC%97%B0%EA%B2%B0%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%83%88-%EB%B2%84%ED%82%B7-%EC%83%9D%EC%84%B1-1 h_01J6Y2P4CN336CRH1CWRJVCHHY=%EC%9D%B8%EB%B0%94%EC%9A%B4%EB%93%9C%EC%95%84%EC%9B%83%EB%B0%94%EC%9A%B4%EB%93%9C-%EC%97%B0%EA%B2%B0%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%83%88-%EB%B2%84%ED%82%B7-%EC%83%9D%EC%84%B1-1 modifying-an-existing-bucket-previously-used-only-for-data-locker::ba0d4803=%EC%9D%B4%EC%A0%84%EC%97%90-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4%EC%97%90%EB%A7%8C-%EC%82%AC%EC%9A%A9%EB%90%98%EC%97%88%EB%8D%98-%EA%B8%B0%EC%A1%B4-%EB%B2%84%ED%82%B7-%EC%88%98%EC%A0%95-1 h_01J6Y2P4CNYCTVGN6CH0748S24=%EC%9D%B4%EC%A0%84%EC%97%90-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4%EC%97%90%EB%A7%8C-%EC%82%AC%EC%9A%A9%EB%90%98%EC%97%88%EB%8D%98-%EA%B8%B0%EC%A1%B4-%EB%B2%84%ED%82%B7-%EC%88%98%EC%A0%95-1" />
