---
title: Data Locker— 클라우드 서비스 설정
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-02-10T17:35:25Z'
  edited_at: '2026-10-14T10:35:08Z'
  id: 360017603577
  locale: ko
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/ko/articles/360017603577
---
> **간단히 보기**: Data Locker로부터 데이터를 수신할 수 있도록 클라우드 서비스를 설정하세요. GCS, AWS, BigQuery 또는 Snowflake.

Data Locker를 사용하면 버킷이든 데이터 웨어하우스든 선택한 자체 스토리지 솔루션으로 데이터를 스트리밍할 수 있습니다. 다음 절차 중 하나를 사용하여 클라우드 서비스를 설정합니다.

<div id="bucket-cloud-storage" />

## 버킷 클라우드 스토리지

<div id="gcs-storage" />

<Accordion title="GCS 스토리지">

시작하기 전에 다음 사항을 참고하세요.

* 이 섹션의 절차는 Google Cloud 관리자가 수행해야 합니다.
* Data Locker에 파일이 작성된 지 25시간 이상이 지나면 삭제할 수 있습니다. 그 전에는 파일을 삭제하지 마십시오.

**GCS 관리자에 대한 정보**

Data Locker는 스토리지로 데이터를 스트리밍하기 위한 앱스플라이어 솔루션입니다.

**요구 사항**

* Data Locker 전용 GCS 버킷을 생성하세요. 전용이란 다른 서비스가 해당 버킷에 데이터를 쓰지 않는 것을 의미합니다.
* 제안된 버킷 이름: `af-datalocker`.
* 다음 절차에 따라 Data Locker 권한을 부여하세요.

**Data Locker 권한 부여 방법:**

이 절차에서 `data-locker-example`은(는) 앞서 Data Locker 전용으로 생성한 버킷 이름으로 대체하세요.

1. GCS 콘솔에 로그인합니다.
2. **스토리지** > **스토리지 브라우저**로 이동합니다.

   <Image align="center" alt="mceclip0.png" src="https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png" />
3. 예를 들어 `data-locker-example`와(과) 같이 이전에 생성한 버킷을 선택하세요.
4. **권한** 탭으로 이동합니다.
5. **+추가**를 클릭합니다.  
   회원 추가 창이 열립니다.
6. 다음과 같이 완료하세요.
   1. **신규 회원**, 해당 스니펫을 붙여 넣으십시오.

      ```http
      af-data-delivery@af-raw-data.iam.gserviceaccount.com
      ```
   2. **역할 선택** **클라우드 스토리지** > **스토리지 객체 관리** .

      <Image align="center" alt="mceclip0.png" src="https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png" />
7. **저장**을 클릭하세요.

</Accordion>

<div id="aws-storage" />

<Accordion title="AWS 스토리지">

시작하기 전에 다음 사항을 참고하세요.

* 본 섹션의 절차는 AWS 관리자가 수행해야 합니다.
* Data Locker에 파일이 작성된 지 25시간 이상이 지나면 삭제할 수 있습니다. 그 전에는 파일을 삭제하지 마십시오.

**AWS 관리자 정보**

Data Locker는 스토리지로 데이터를 스트리밍하기 위한 앱스플라이어 솔루션입니다.

**요구 사항**

* af-datalocker-mybucket.라는 이름의 AWS 버킷을 만드세요. 접두사 af-datalocker-는 필수입니다. 접미사는 사용자가 설정합니다.
* af-datalocker-yyyy-mm-dd-hh-mm-free-text 형식을 제안합니다. 여기서 yyyy-mm-dd-hh-mm은 현재 날짜와 시간이고, 그 다음에 나오는 그림에 표시된 것과 같이 원하는 텍스트를 추가합니다.

**AWS 콘솔의 사용자 인터페이스**

<Image align="center" alt="MyBucket.jpg" src="https://files.readme.io/b8a16d185279200026388e146cfb3eb03ae3c7737ac26da3aa0d116a0cf9c078-4403551836305.jpg" />

버킷을 생성한 후 다음 절차에 따라 앱스플라이어 권한을 부여하세요.

**버킷 생성 및 앱스플라이어에 권한 부여 방법:**

1. AWS 콘솔에 로그인합니다.
2. S3 서비스로 이동합니다.
3. **버킷 생성 방법**:
   1. **버킷 생성**을 클릭합니다.
   2. 다음과 같이 **버킷 이름**을 설정하세요. `af-datalocker-`로 시작한 후 앞서 설명한 대로 나머지 텍스트를 추가하세요.
   3. [지원되는 AWS](#지원되는-aws-지역) 리전 중 하나를 지정하세요.
   4. **버킷 생성**을 클릭합니다.
4. **앱스플라이어에 권한 부여 방법:**
   1. 버킷을 선택합니다.
   2. **권한** 탭으로 이동합니다.
   3. **버킷 정책** 섹션에서 **편집**을 클릭합니다.   
      버킷 정책 창이 나타납니다.
   4. 다음 스니펫을 창에 붙여 넣습니다.

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF_DataLocker_Direct",
            "Effect": "Allow",
            "Principal": {
              "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
            },
            "Action": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Resource": [
              "arn:aws:s3:::af-datalocker-my-bucket",
              "arn:aws:s3:::af-datalocker-my-bucket/*"
            ]
          }
        ]
      }
      ```
5. 스니펫에서 `af-datalocker-my-bucket`을(를) 생성한 버킷 이름으로 대체하세요.
6. [선택 사항] KMS 암호화 버킷에 대한 지원을 추가합니다. 이렇게 하려면 **주요 정책(Key Policy)** 섹션에서 **정책 보기로 전환**을 선택하고 **문(Statement) 배열**에 다음 스니펫을 붙여넣으세요.

   ```json
   {
         "Sid": "Allow use of the key",
         "Effect": "Allow",
         "Principal": {
             "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
         },
         "Action": "kms:GenerateDataKey*",
         "Resource": "*"
     }
   ```
7. **변경 사항 저장**을 클릭합니다.
8. <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers#데이터-락커-리포트-설정하기">Data Locker 설정 절차</Anchor>를 완료합니다.

<div id="supported-aws-regions" />

#### **지원되는 AWS 지역**

Data Locker 는 다음 AWS 지역을 지원합니다.

* 아시아 태평양 (도쿄): `ap-northeast-1`
* 아시아 태평양 (서울): `ap-northeast-2`
* 아시아 태평양 (뭄바이): `ap-south-1`
* 아시아 태평양 (싱가포르): `ap-southeast-1`
* 아시아 태평양 (시드니): `ap-southeast-2`
* 캐나다 (중부): `ca-central-1`
* EU (프랑크푸르트): `eu-central-1`
* EU (아일랜드): `eu-west-1`
* EU (런던): `eu-west-2`
* 남미(상파울루): `sa-east-1`
* 미국 동부 (버지니아 북부): `us-east-1`
* 미국 동부 (오하이오): `us-east-2`
* 미국 서부 (북부 캘리포니아): `us-west-1`
* 미국 서부 (오리건): `us-west-2`

</Accordion>

<div id="beta--azure-storage" />

<Accordion title="Azure 스토리지">

시작하기 전에 다음 사항을 참고하세요.

* 이 섹션의 절차는 Azure 클라우드 관리자가 수행해야 합니다.
* Data Locker에 파일이 작성된 지 25시간 이상이 지나면 삭제할 수 있습니다. 그 전에는 파일을 삭제하지 마십시오.

**Azure 관리자에 대한 정보**

Data Locker는 데이터를 스토리지 계정으로 스트리밍하기 위한 앱스플라이어 솔루션입니다.

**Data Locker에 대한 저장소 계정을 정의하려면:**

1. Azure 포털에서 [Azure storage accounts](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts)로 이동한 후 <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**Create**를 클릭하여 앱스플라이어 데이터를 수신할 스토리지 계정을 생성하세요.
2. **기본** 탭 **> 프로젝트 세부 정보,** 에서 드롭다운 메뉴를 선택하십시오.
   1. **구독.**
   2. **리소스 그룹.**  
      선택 사항: 리소스 그룹이 없는 경우, **새로 만들기를** 클릭하여 리소스 그룹을 생성하세요.
3. **인스턴스 세부정보:** 아래에서:
   1. **스토리지 계정 이름**을 입력합니다.
   2. 드롭다운에서 **지역**을 선택합니다.
4. **다음** 클릭: Advanced >
5. **보안** 탭에서 **계층적 네임스페이스 사용**을(를) 선택하세요.
6. **검토 > 만들기**를 클릭하세요.
7. 배포가 완료되면 [Azure 스토리지 계정](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts)으로 돌아가서 새로 만든 계정을 선택하세요.
8. **액세스 키**로 이동하고 **저장소 계정 이름** 과 **키** 중 하나를 복사하세요.
9. **스토리지 브라우저 > Blob 컨테이너**로 이동하여 <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**컨테이너 추가**를 클릭하세요.
   1. 새 컨테이너 **이름**을 입력하세요.
   2. **생성**을 클릭합니다.
10. 활성화되면 앱스플라이어에서 <Anchor target="_blank" href="https://hq1.appsflyer.com/datalocker/overview">**Data Locker**</Anchor> **> <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />새 연결**로 이동하세요.
11. 새로운 연결에서:
    1. 연결 이름을 지정합니다.
    2. **Azure Blob을** 선택하세요.
    3. **버켓 이름** 필드에 Azure **컨테이너 이름**(9단계에서 생성한 이름)을 입력하세요.
    4. 8단계에서 복사한 **스토리지 계정 이름을** 입력하세요.
    5. 8단계에서 복사한 **키를** 입력하세요.
    6. **연결 테스트**를 클릭합니다.
    7. **저장**

</Accordion>

<div id="yandex" />

<Accordion title="[베타] Yandex 클라우드 스토리지">

시작하기 전에 다음 사항을 참고하세요.

* 이 섹션의 절차는 Yandex 클라우드 관리자가 수행해야 합니다.
* Data Locker에 파일이 작성된 지 25시간 이상이 지나면 삭제할 수 있습니다. 그 전에는 파일을 삭제하지 마십시오.

**Yandex 관리자에 대한 정보**

Data Locker는 스토리지로 데이터를 스트리밍하기 위한 앱스플라이어 솔루션입니다.

**버킷 생성 및 Data Locker 권한 부여 방법:**

1. <Anchor target="_blank" href="https://console.cloud.yandex.com/">Yandex Cloud 콘솔</Anchor>에서 **서비스 계정** 탭으로 이동하여 **서비스 계정 만들기**를 클릭합니다.
2. 서비스 계정의 이름을 지정하십시오, 예를 들어, `af-datalocker`.
3. 서비스 계정에 대한 정적 액세스 키를 생성합니다. 서비스 계정에서 다음을 수행합니다.
   1. **새 키 만들기**를 클릭합니다.
   2. **정적 액세스 키 만들기**를 선택합니다.
   3. **키 ID**와 **비밀 키**를 저장합니다.
4. 새 서비스 계정에 **storage.editor** 권한을 제공합니다.
   1. 버킷 설정에서 **액세스 바인딩**으로 이동하여 **바인딩 할당**을 클릭합니다.
   2. 새 서비스 계정의 경우 **storage.editor** 역할을 추가하고 **저장**을 클릭합니다.
5. 앱스플라이어 CSM에게 연락하여 Data Locker에서 Yandex를 활성화하십시오.
6. 활성화되면 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers#set-up-data-locker">Data Locker 설정</Anchor> 중 키 ID와 비밀 키를 사용합니다.

</Accordion>

<div id="data-warehouse-cloud-storage" />

## 데이터 웨어하우스 클라우드 스토리지

<div id="bigquery" />

<Accordion title="BigQuery">

본 섹션의 절차는 BigQuery 관리자가 수행해야 합니다.

**BigQuery 관리자 정보**

Data Locker는 스토리지로 데이터를 스트리밍하기 위한 앱스플라이어 솔루션입니다.

**요구 사항**

* BigQuery 데이터세트 생성

**BigQuery 데이터세트 생성:**

1. BigQuery에서 프로젝트를 만들거나 기존 프로젝트를 사용합니다.
2. 프로젝트에서 **CREATE DATASET**를 클릭합니다. [![GCSCreateDataSEt_1_.png](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)
3. 데이터 세트에 적합한 ID를 부여합니다.

   <div id="note" />

   > 📘 **참고**
   >
   > 타깃 프로젝트 또는 데이터세트가 활성화된 결제 계정에 연결되어 있는지 확인하세요. 결제 계정이 없으면 Data Locker가 BigQuery 목적지에 테이블을 생성하거나 데이터를 쓸 수 없으며, 연결 설정 프로세스가 실패할 수 있습니다.

4. 앱스플라이어에게 데이터 세트에 대한 액세스 권한을 부여합니다. <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/control-access-to-resources-iam#grant_access_to_a_resource">Big Query 지침 참조</Anchor>
   * **보안 주체 추가**의 경우 다음 앱스플라이어 사용자를 사용합니다: [datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com](mailto:datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com)
   * **역할 할당**에서 BigQuery 데이터 편집기를 선택합니다.
5. 필요에 따라 나머지 설정을 완료합니다.

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Data Locker를 Snowflake 계정에 연결합니다. 그러면 데이터가 Snowflake로 전송되고 선택한 클라우드 스토리지에서 계속 사용할 수 있습니다.

**BI 개발자를 위한 고려사항**

* 데이터 최신성 업데이트 주기는 버킷에 제공되는 데이터의 업데이트 주기와 동일합니다.
* 데이터의 테이블 및 컬럼 구조는 Data Locker 버킷에서 직접 제공되는 데이터와 동일합니다.
* Snowflake 공유에 행이 추가됨에 따라 `_ingestion_time` 열은 UTC가 아닌 시스템의 로컬 시간대로 채워집니다. 행 고유성을 유지하고 동일한 행이 두 번 이상 수집되지 않도록 하려면 다음과 같이 하십시오.
  1. 수집된 테이블별로 `max_ingestion_time`을(를) 저장하세요.
  2. 수집 프로세스를 진행할 때마다 `_ingestion_time > max_ingestion_time` 행만 인제스트하세요.

다음 절차에 따라 Snowflake를 Data Locker에 연결하세요.

<div id="snowflake-connector-procedures" />

#### **Snowflake 커넥터 절차**

**Snowflake 계정 ID와 지역을 가져오는 방법**:

1. Snowflake에서 <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Snowflake 계정에 로그인합니다</Anchor>.
2. 메뉴 바에서 이름을 선택합니다.  
   계정 ID와 지역이 표시됩니다.

   <Image align="center" alt="Snowflake 계정 세부 정보" src="https://files.readme.io/6f508a5c2c6cd5dd84dd2639c73e62ff819e0a06ea3323d7a999a6b4fc717009-40394499797393.png" width="875px" />

**Data Locker를 Snowflake에 연결하는 방법**:

1. 앱스플라이어에서 **리포트** > **Data Locker**로 이동합니다.
2. Snowflake를 선택합니다.
3. 이전에 Snowflake로부터 받은 정보를 사용하여 Snowflake 지역 및 계정 로케이터를 입력하세요.
4. **저장**을 클릭하세요.

**Snowflake의 공유에서 데이터베이스를 생성하는 방법**:

1. Snowflake에서 <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Snowflake 계정에 로그인합니다</Anchor>.
2. 역할을 **Accountadmin**으로 전환합니다. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/data-share-consumers.html#creating-a-database-from-a-share">공유에서 데이터베이스 생성</Anchor>을 참조하세요.
3. **공유**를 선택합니다.
4. 예를 들어 APPSFLYER\_ACC\_XXX\_DATA\_LOCKER와 같이 앱스플라이어 공유를 선택하세요.
5. **Secure Share에서 데이터베이스 생성**을 클릭하고 필요한 상세 정보를 입력하세요. **참고**! 공유 데이터베이스의 데이터는 제한된 기간(현재 14일) 동안만 이용할 수 있으므로, 해당 데이터를 내부 테이블로 로드해야 합니다.
6. 데이터베이스에 가져온 테이블이 표시됩니다. 표 이름 및 구조는 Data Locker 버킷의 이름 및 구조와 동일합니다.

</Accordion>

<div id="traits-and-limitations" />

## 특징 및 제한 사항

| 특징 | 설명 |
| --- | --- |
| 앱스플라이어 클라우드 연결 | 보고서는 압축되지 않은 상태로 저장할 수 없습니다. |
| BigQuery 데이터 세트 위치 변경 | BigQuery에서 데이터세트 위치를 변경하는 경우, 앱스플라이어에서 연결 설정을 다시 저장해야 합니다. 앱스플라이어 연결 설정에서 변경할 구성 요소가 없으므로 **저장** 버튼이 비활성화됩니다. 버튼을 활성화하려면 임시로 설정을 변경한 뒤 연결을 저장하고, 다시 원래대로 되돌린 후 연결을 한번 더 저장하세요. |
| 지원되는 Snowflake 지역 | **AWS 지원 지역:**<ul><li>us-east-1</li><li>us-east-2</li><li>us-west-2</li><li>eu-west-1</li><li>eu-west-2</li><li>eu-west-3</li><li>eu-central-1</li><li>eu-north-1</li><li>ca-central-1</li><li>sa-east-1</li><li>ap-south-1</li><li>ap-southeast-1</li><li>ap-southeast-2</li><li>ap-northeast-1</li><li>ap-northeast-2</li><li>ap-northeast-3</li></ul>**Azure 지원 지역:**<ul><li>australia-east</li><li>east-us-2</li><li>central-us</li><li>southcentral-us</li><li>west-europe</li><li>west-us-2</li></ul>**GCP 지원 지역**<ul><li>제한된 지원. 귀하의 지역에서 이용 가능한지 확인하려면 앱스플라이어 지원팀에 문의하세요.</li></ul> |

<div data-zendesk-anchors="bucket-cloud-storage=%EB%B2%84%ED%82%B7-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80 h_01HE2SPKYZWFXA63YD5NK4KJRD=%EB%B2%84%ED%82%B7-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80 h_01HE2SPKYZM9QQCGFN86J7FNDY=gcs-storage h_01HE2SPKYZK4F9E22MG3K8SJE8=aws-storage supported-aws-regions=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-aws-%EC%A7%80%EC%97%AD h_01J2DSZ4NVVMTTNSXP2Z9DAS0Q=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-aws-%EC%A7%80%EC%97%AD %5Bbeta%5D-azure-storage=beta--azure-storage h_01HE2SRAJA94R8ZKHRBEFNKX8D=beta--azure-storage h_01HE2SPKYZXAXMKPH5DQV40X1W=yandex data-warehouse-cloud-storage=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9B%A8%EC%96%B4%ED%95%98%EC%9A%B0%EC%8A%A4-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80 h_01HE2SPKYZ77X8WP9ZNRB1D05B=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9B%A8%EC%96%B4%ED%95%98%EC%9A%B0%EC%8A%A4-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80 h_01HE2SPKYZMNW776CZRZAFVV5H=bigquery h_01JXQM7DAHD40DJYERY106H826=%EC%B0%B8%EA%B3%A0 h_01HE2SPKYZC3W4G3YXFM10H9D3=snowflake snowflake-connector-procedures=snowflake-%EC%BB%A4%EB%84%A5%ED%84%B0-%EC%A0%88%EC%B0%A8 h_01HE2SPKYZ11B1MJYX2HRCS07D=snowflake-%EC%BB%A4%EB%84%A5%ED%84%B0-%EC%A0%88%EC%B0%A8 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01KYVRP8CVMD01EZY5561W2RCJ=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD" />
