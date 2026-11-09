---
title: 데이터 협업 플랫폼(DCP) — 연결을 추가하세요
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
  created_at: '2024-04-28T13:26:59Z'
  edited_at: '2026-10-14T10:33:16Z'
  id: 24603890457617
  locale: ko
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ko/articles/24603890457617
---
> **한눈에 보기:** 데이터 소스를 연결하고, 데이터를 풍부화하며, 클라우드 스토리지 및 미디어 파트너로 오디언스를 내보낼 수 있도록 DCP 연결을 설정하세요.

<div id="about-dcp-connections" />

## DCP 연결에 관하여

연결은 DCP가 데이터를 수집하고 오디언스를 내보내는 방식을 결정합니다. <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">클라우드 서비스를 설정</Anchor>한 후, **연결 관리** 모달을 사용하여 이를 DCP에 연결하세요. 다음과 같은 연결 유형을 사용할 수 있습니다.

* [**소스 연결**](#create-source-connections) : 클라우드 스토리지 또는 데이터 웨어하우스에서 퍼스트 파티 데이터를 DCP로 수집하기
* [**클라우드 스토리지 연결**](#create-cloud-storage-connections) : 오디언스를 Amazon S3 또는 Google Cloud Storage (GCS) 버킷으로 내보내기
* [**미디어 파트너 연결**](#create-media-partner-connections) : 오액티베이션을 위해 오디언스를 광고 플랫폼으로 전송하기
* [**데이터 및 신원 연결**](#create-data-identity-connections) : 매치 레이트를 높이고 파트너 측 오디언스를 확장하기 위해 파편화된 사용자 데이터를 통합하기

DCP는 연결 방향에 따라 다양한 클라우드 서비스를 지원합니다. 아래 표를 참고하여 각 연결 유형별로 사용할 수 있는 서비스를 확인하세요.

| 클라우드 서비스 | 소스(인바운드) | 클라우드 스토리지 내보내기(아웃바운드) |
| --- | --- | --- |
| Amazon S3 | ✓ | ✓ |
| Google Cloud Storage(GCS) | ✓ | ✓ |
| 빅쿼리 | ✓ | - |
| Snowflake | ✓ | - |
| Salesforce Cloud/CRM | ✓ | - |

Amazon S3 및 Google Cloud Storage의 경우, 단일 연결이 소스(인바운드)이자 클라우드 스토리지 내보내기(아웃바운드) 목적지 역할을 모두 수행합니다. S3 또는 GCS로 소스 연결을 생성하면 일치하는 클라우드 스토리지(내보내기) 연결이 자동으로 생성되며, 그 반대의 경우도 마찬가지입니다.

<div id="create-source-connections" />

<Accordion title="소스 연결 생성">

DCP로 자사 데이터를 가져오기 위한 소스 연결을 생성합니다.

**소스 연결을 생성하려면 다음 단계를 따르세요.**

1. 앱스플라이어에서 **협업** > **데이터 클린룸**으로 이동하세요.
2. 오른쪽 상단 모서리에 있는 **연결 관리**를 클릭하세요.
3. **소스** 탭으로 이동하여 **+ 새 연결**을 클릭합니다.  
   <Image align="center" alt="2026-07-27_13-30-46.png" src="https://files.readme.io/dec879432c0b9d6ba4eeec2c175dfce145c99652ccabb02d37f3434627f9310f-49189748198289.png" width="529px" />
4. 아래의 [소스 데이터용 클라우드 서비스 연결 지침](#소스-데이터에-대한-클라우드-서비스-연결)에 따라 계속 진행하세요.

소스를 설정할 때 소스 연결을 직접 생성할 수도 있습니다. 자세한 지침은 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources">소스 생성 및 관리</Anchor>를 참고하세요.

<div id="note" />

> 📘 **참고**
>
> S3 또는 GCS로 소스 연결을 생성하면 일치하는 클라우드 스토리지(내보내기) 연결이 자동으로 생성되며, 그 반대의 경우도 마찬가지입니다. Amazon S3 또는 GCS 연결을 삭제하면 다른 쪽 연결도 자동으로 삭제됩니다. 실제로는 하나의 단일 연결이므로, 어느 탭에서 삭제하든 해당 연결이 사용된 모든 위치에서 삭제됩니다.

<div id="cloud-service-connections-for-source-data" />

#### 소스 데이터에 대한 클라우드 서비스 연결

소스 연결은 데이터 소스를 DCP에 안전하게 연결하기 위한 기능입니다. **새 연결** 대화 상자에서 클라우드 서비스를 선택하고 해당 제공업체에 대한 세부 정보를 입력하세요.

**BigQuery:** **새 연결** 대화 상자에서 소스 데이터가 포함된 프로젝트의 BigQuery **프로젝트 ID**를 입력하세요. Google Cloud Console의 BigQuery 페이지에서 이 정보를 확인할 수 있습니다.

**Snowflake:** **새 연결** 대화 상자에서 소스 데이터가 포함된 계정의 **Snowflake 계정 ID**와 **지역**을 입력하세요. 이를 확인하려면 Snowflake 콘솔 좌측 하단의 계정 이름을 클릭하세요.

**ACCOUNTADMIN** > **계정** > 해당 계정에 마우스를 올린 후 > **계정 식별자 복사**를 클릭하세요. 자세한 내용은 <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/admin-account-identifier#finding-the-organization-and-account-name-for-an-account">Snowflake 문서</Anchor>를 참고하세요.

<div id="important" />

> 🚧 **중요!**
>
> 라고 표시된 ID 를 찾으세요. 이것은 아웃바운드 Snowflake 연결을 생성하는 데 사용되는 ID와 동일하지 **않습니다**.

**Amazon S3 및 GCS:** **새 연결** 대화 상자에서 앱스플라이어 Data Clean Room (DCR) 전용으로 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#cloud-storage-buckets-inbound">생성한 버킷</Anchor>의 이름을 입력하세요.

**Salesforce Cloud/CRM:** <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-integration-with-salesforce-data-cloud">Salesforce 연결 설정 방법을</Anchor> 확인하세요.

<div id="local-file-connection" />

#### 로컬 파일 연결

로컬 파일 시스템 연결을 사용하면 컴퓨터에서 DCP로 데이터 파일을 직접 업로드할 수 있습니다. 이 옵션은 보통 테스트 전용으로 사용되며, 지속적이거나 대규모의 데이터 수집에는 권장되지 않습니다.

<div id="set-up-a-local-file-connection" />

<Accordion title="로컬 파일 연결 설정">

로컬 파일 연결은 샘플 파일을 사용하여 플랫폼을 테스트하는 데 사용됩니다. 데이터 공유를 시작하기 전에 DCP 기능에 익숙해질 수 있도록 도와줍니다. 데이터 공유용으로는 권장되지 않으며, 데이터 보존 기간이 14일로 제한되고 자동화 프로세스를 지원하지 않는다는 점에 유의하세요.

로컬 파일 연결은 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#소스-위치는-로컬-파일입니다">소스 생성 중에 설정할 수 있습니다</Anchor>.

</Accordion>

</Accordion>

<div id="create-cloud-storage-connections" />

<Accordion title="클라우드 스토리지 연결 생성">

클라우드 스토리지 연결을 사용하면 오디언스가 업데이트될 때마다 DCP 오디언스를 Amazon S3 또는 Google Cloud Storage (GCS) 버킷으로 자동으로 내보낼 수 있습니다.

**클라우드 스토리지 연결을 생성하려면 다음 단계를 따르세요.**

1. 앱스플라이어에서 **협업** > **데이터 클린룸**으로 이동하세요.
2. 오른쪽 상단 모서리에 있는 **연결 관리**를 클릭하세요.
3. **클라우드 저장소** 탭으로 이동하여 **+ 새 연결**을 클릭하세요.  
   <Image align="center" alt="2026-07-27_13-30-34.png" src="https://files.readme.io/1da10127617317d0ff466433c89712d78c104b6a943b4b669e1d7180d22df958-49189843742609.png" width="533px" />
4. **새 클라우드 스토리지 연결** 모달 창이 열립니다.
5. **새 클라우드 스토리지 연결** 모달에서 클라우드 제공업체 선택하세요. **Google Cloud Storage** 또는 **Amazon Simple Storage** .
6. 버킷 이름 입력:
   * **GCS:** GCS 버킷 이름을 다음 형식으로 입력하세요.`gs://my-bucket` .
   * **S3:** S3 버킷 이름을 입력하세요.
7. DCP가 버킷에 연결할 수 있는지 확인하려면 **연결 테스트를** 클릭하세요.
8. **저장**을 클릭하세요. 새 연결이 **클라우드 스토리지** 탭의 **내 클라우드 스토리지 연결** 아래에 표시됩니다.

오디언스 빌더에서 직접 클라우드 스토리지 연결을 생성할 수도 있습니다. 자세한 지침은 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-build-and-activate-audiences">오디언스 생성 및 활성화</Anchor>를 참고하세요.

<div id="understand-export-path" />

<Accordion title="내보내기 경로를 이해하기">

오디언스가 내보내질 때마다 DCP는 고정되고 예측 가능한 경로를 사용하여 이를 버킷에 기록합니다:

```
<bucket>/dcp-output/audiences/<collaboration-id>/t=<audience_name>_<id>/dt=<YYYY-MM-DD>/v=<version>/<file>.csv
```

**1회 전송 시 예시 폴더 구성:**

```
s3://af-dcr-example-bucket/dcp-output/audiences/8f3a1c02-44b1-4e9a-9c7d-2b6e1a0f5d3e/t=example_audience_6148a3/dt=2026-07-18/v=1/
  ├── part-00000-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv
  ├── part-00001-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv
  └── _SUCCESS
```

| 경로 세그먼트 | 의미 |
| --- | --- |
|  | 연결된 S3 또는 GCS 버킷입니다. |
| dcp-output/audiences/ | DCP가 모든 오디언스 내보내기를 위해 자동으로 생성하는 고정 폴더입니다. |
|  | 이 오디언스가 속한 콜라보레이션의 고유 ID입니다. DCP의 콜라보레이션 URL에서 이를 확인할 수 있습니다. |
| t=\_ | 오디언스 이름(공백 및 특수 문자는 언더스코어로 대체됨)과 고유 ID입니다. 이렇게 하면 동일한 이름으로 삭제된 후 다시 생성된 오디언스가 이전 파일을 덮어쓰거나 충돌하지 않습니다. |
| dt= | 전송 날짜입니다. |
| v= | 이 사용자 그룹의 내보내기에 대한 버전 번호입니다. 새로운 전송이 있을 때마다 증가합니다. |
| part-NNNNN--c000.csv | 이 전송에 대한 출력 파일 중 하나입니다 — 아래의 파일 형식 및 분일을 참고하세요. |
| \_SUCCESS | 모든 파트 파일의 내보내기가 완료되면 작성되는 빈 마커 파일입니다. |

<div id="note-1" />

> 📘 **참고**
>
> 이 폴더 구조는 자동으로 생성되고 관리됩니다. 이 구조를 수동으로 이름을 변경하거나 재구성하지 마세요. 이 파일들을 읽는 모든 자동화 프로세스는 이 경로 패턴을 따르도록 구축되어야 하며, 부분적으로 전송된 파일을 읽지 않도록 파트 파일을 처리하기 전에 \_SUCCESS가 나타날 때까지 기다려야 합니다.

**파일 형식 및 분할**

* 오디언스는 항상 압축되지 않은 CSV 파일로 내보내지며, `value` 식별자와 `taxonomy` 식별자 유형의 두 개 열로 구성됩니다.
* 대규모 오디언스는 단일 파일 대신 여러 파일로 나누어 전달될 수 있으며, `part-00000`, `part-00001` 등 번호가 부여됩니다. 기본적으로 각 파일에는 최대 약 500,000개의 행이 포함됩니다.
* 단일 파일의 행 내에 여러 식별자 유형이 혼합되어 포함될 수 있으므로, 필요한 식별자는 `taxonomy` 열을 사용하여 필터링하세요. 일반적인 택소노미 값에는 다음이 포함됩니다.`customer_id`, `mobile_ad_id`, `hashed_email`, 및 `hashed_phone_number_without_plus_sha256`.

**예:**

```
value,taxonomy
6f1a2b3c4d5e6f7a8b9c0d1e2f3a4b5c,customer_id
1a2b3c4d-5e6f-4a7b-8c9d-0e1f2a3b4c5d,mobile_ad_id
b7e2c9a1f4d6e8b0a2c4d6e8f0a1b3c5d7e9f1a3b5c7d9e0f2a4b6c8d0e2f4a6,hashed_email
c1d3e5f7a9b1c3d5e7f9a1b3c5d7e9f1a3b5c7d9e1f3a5b7c9d1e3f5a7b9c1d3,hashed_phone_number_without_plus_sha256
```

</Accordion>

</Accordion>

<div id="create-media-partner-connections" />

<Accordion title="미디어 파트너와의 연결망 구축">

아웃바운드 미디어 파트너 연결을 사용하면 DCP 오디언스를 지원되는 미디어 파트너에 안전하게 연결하여 해당 플랫폼에서 맞춤형 캠페인을 활성화할 수 있습니다. 미디어 파트너는 오디언스 활성화의 주요 타겟 대상입니다. <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-media-partner-connections">특정 미디어 파트너와의 연결을 설정하는</Anchor> 방법을 알아보세요.

**미디어 파트너 연결 생성 방법:**

1. 앱스플라이어에서 **협업** > **데이터 클린룸**으로 이동하세요.
2. 오른쪽 상단 모서리에 있는 **연결 관리**를 클릭하세요.
3. **미디어 파트너** 탭으로 이동하여 **+ 새 연결**을 클릭하세요. 이미 기존 연결이 있는 경우 **미디어 파트너**에 목록으로 표시됩니다.
4. **새 미디어 파트너 연결** 대화 상자에서 해당 미디어 파트너를 선택합니다.
5. 연결 이름을 입력합니다.
6. 자격 증명으로 미디어 파트너 계정에 로그인하고 해당 지침에 따라 앱스플라이어 액세스를 활성화합니다.
7. **계정 ID 선택**을 클릭하고 이 연결에 해당하는 계정을 선택하세요.
8. **저장**을 클릭하세요. 새 연결이 파트너 목록에 추가됩니다.

오디언스 빌더에서 직접 미디어 파트너 연결을 생성할 수도 있습니다. 자세한 지침은 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-build-and-activate-audiences">오디언스 생성 및 활성화</Anchor>를 참고하세요.

</Accordion>

<div id="create-data-identity-connections" />

<Accordion title="데이터 및 ID 연결 생성">

데이터 및 식별자 연결은 파편화된 사용자 데이터를 통합하여 활성화 파트너와의 매칭률을 향상시킵니다. 이를 통해 파트너 측 오디언스 규모를 확대하고 캠페인 성과를 더욱 극대화할 수 있습니다.

#### ID5

파편화된 사용자 데이터를 통합하고, 활성화 파트너와의 매칭률을 개선하며, 파트너 측 오디언스 규모를 확대하려면 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-enrich-sources-with-id5">ID5 식별자로 퍼스트 파티 데이터를 보강하세요</Anchor>.

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">DCP - 클라우드 서비스 설정</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-build-and-activate-audiences">DCP - 오디언스 구축 및 활성화</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-media-partner-connections">DCP - 미디어 파트너 연결</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-enrich-sources-with-id5">DCP - ID5를 활용한 소스 보강</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-guide">데이터 협업 플랫폼(DCP) 가이드</Anchor>

</Accordion>

<div data-zendesk-anchors="about-dcp-connections=dcp-%EC%97%B0%EA%B2%B0%EC%97%90-%EA%B4%80%ED%95%98%EC%97%AC h_01KXX80P91T92MH8KEGHVG3QP1=dcp-%EC%97%B0%EA%B2%B0%EC%97%90-%EA%B4%80%ED%95%98%EC%97%AC h_01KXX80P913HRREW60M6S316PP=create-source-connections h_01KY4HCGBBCD5FZD9RYNNVDYRC=%EC%B0%B8%EA%B3%A0 source-cloud-service-connections=%EC%86%8C%EC%8A%A4-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%97%90-%EB%8C%80%ED%95%9C-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%97%B0%EA%B2%B0 cloud-service-connections-for-source-data=%EC%86%8C%EC%8A%A4-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%97%90-%EB%8C%80%ED%95%9C-%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C-%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%97%B0%EA%B2%B0 h_01KXX80P914VFMH1T6FQF9KC31=%EC%A4%91%EC%9A%94 local-file-connection=%EB%A1%9C%EC%BB%AC-%ED%8C%8C%EC%9D%BC-%EC%97%B0%EA%B2%B0 h_01KXX80P91EFCGH3MYV729TGTH=%EB%A1%9C%EC%BB%AC-%ED%8C%8C%EC%9D%BC-%EC%97%B0%EA%B2%B0 h_01KXX80P91HG17YTWE15ZWTBZ8=set-up-a-local-file-connection h_01KXX80P91F8TG9FR1XQ7QVNCY=create-cloud-storage-connections h_01KYEP2MX3KQ3BAP7VRSGYTFBB=understand-export-path h_01KYEP2MX3SHFCECTSTHV9RMS4=%EC%B0%B8%EA%B3%A0-1 h_01KXX80P91BMB45ETZQSKWJWZB=create-media-partner-connections h_01KXX80P91PS35EG5P5YJB9EHC=create-data-identity-connections h_01KXX80P92BXD3B7ZVT1FC5HCF=id5 h_01KXX80P92WMPPRGD7321TBS7Y=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
