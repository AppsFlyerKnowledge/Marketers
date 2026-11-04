---
title: 비용 ETL—세분화된 캠페인 비용이 버킷에 저장됩니다
metadata:
  keywords:
    - Campaign
    - eCPI
    - clicks
    - Impressions
    - ROI
    - cost
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2020-05-17T15:36:41Z'
  edited_at: '2026-10-14T10:32:03Z'
  id: 360008849238
  locale: ko
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ko/articles/360008849238
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** <span id="cost-etl-principles"></span>앱스플라이어 ROI360의 일환으로 제공되는 비용 ETL은 광고주에게 미디어 소스별 최고의 세밀도를 가진 캠페인 비용 데이터를 제공합니다.

![5896_CostETL_graphic__2_.png](https://files.readme.io/3c9b8721fa4aba170c1ed7b7b365b4a5fe1cd74080469b3020d395352cede674-11178721788817.png)


앱스플라이어 ROI360의 일환으로 제공되는 비용 ETL은 광고주에게 미디어 소스별 최고의 세밀도를 가진 캠페인 비용 데이터를 제공합니다.

캠페인 비용 데이터는 다음과 같이 처리됩니다:

* 현재 날짜와 지난 6일(본문에서는 7일로 언급)뿐만 아니라 14일, 29일, 88일치 데이터가 포함되어 있습니다. 데이터 로딩 과정에서 이 점을 감안하세요.
  * 예시:
  * 이전 날짜에 대한 데이터는 비용 데이터 리포팅의 수정과 업데이트를 허용합니다.
* 어트리뷰션, 클릭 또는 노출과 매칭된 비용에 대해 처리됩니다.  
  **참고**:
  * 최근 7일 간의 데이터는 미디어 소스에서 새로 추출됩니다. 14일, 29일, 88일 데이터는 재처리되고 있습니다.
  * 비용 데이터만 소급하여 업데이트되며, 어트리뷰션 데이터는 그렇지 않습니다.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRqyHRTiLq8KUtELHqdaF6yVTfNE22X5UmUqXX89oOK5ZpS6lksXD0401G8MFmsaEzg2Csvf-d3y08Z/pub?output=xlsx">샘플 파일 확인하기</Anchor>.

**참고**:

* 귀사 비즈니스의 요구사항에 가장 잘 맞는 차원과 지표를 사용하시기 바랍니다. 이것은 미디어 소스에 따라 달라질 수 있습니다.


<div id="report-details" />

<div id="directory-and-filename-structure" />

<Accordion title="디렉터리 및 파일 이름 구조">

* *비용 ETL 작업이 디렉터리에 기록을 완료하면, 성공 파일을 생성하여 플래그가 설정됩니다. 이는 해당 디렉토리에서 가장 최신의 타임스탬프를 나타냅니다.*
* 폴더/파일의 갯수는 다음과 같습니다:
  * 요약
    * 각 배치 폴더에는 7일치 데이터가 담긴 파켓 파일이 들어 있습니다.
  * * 각 배치 폴더는 1부터 시작하는 번호를 가진 데이터가 포함된 파켓 파일을 포함합니다.
  * [마감된 베타]모든 비용:


`///t=/dt=/v=<1/2/3/4>/`

| **변수** | **콘텐츠** |
| --- | --- |
|  |  |
| DL-generated-partition |  |
| 연결 이름을 입력합니다. |  |
| t | 다음 중 하나:<ul><li>cost\_etl\_summary</li><li>cost\_etl\_geo</li><li>cost\_etl\_channel</li></ul> |
| dt: | <ul><li>YYYY-MM-DD</li></ul> |
| v |  |
| Parquet 파일 번호 부여 | <ul><li>00000부터 시작하는 숫자 부여</li><li>예: `part-`</li></ul> |


`/cost_etl/version/dt=/b=//`

| **변수** | **콘텐츠** |
| --- | --- |
| advertiser\_bucket\_name | 비용 ETL 설정에 정의된 바에 따름: 것처럼 을 참조하면: af-xpend-cost-etl-&lt;af-account-id>-[버킷 이름 접미사] |
| cost\_etl | 항상 cost\_etl 사용 |
| 버전 | 비용 ETL 버전 정보 |
| 날짜 | 비용 발생 일자<br /><br />형식: yyyy-mm-dd |
| 배치 처리됨 | 1부터 4 사이의 숫자 |
| 데이터 차원 | 데이터 차원 설명:<ul><li>지역</li><li>채널</li></ul> |
| file\_name | <ul><li>요약</li><li>총 비용</li></ul> |
| Parquet 파일 번호 부여 | <ul><li>00000부터 시작하는 숫자 부여</li><li>예: `part-`</li></ul> |

**예: 2020년 6월 23일 첫 데이터 추출 시 디렉토리 및 파일명 구조는 아래와 같습니다:**

</Accordion>

<div id="file-fields" />

<Accordion title="파일 필드">

<div id="fieldsdimensions" />

#### 필드 및 차원

| **필드** | **설명** | **기본적으로 채워짐** | **형식** | **요약 파일에 포함** |
| --- | --- | --- | --- | --- |
| date | 미디어 소스가 보고한 비용 발생일 | 예 | yyyy-mm-dd 형식의 문자열 | ✓ |
| app\_id | 앱스플라이어 플랫폼에서의 앱 ID | 예 | 문자열 | ✓ |
| media\_source | 광고를 게재한 미디어 소스 | 예 | 문자열 | ✓ |
| os | 디바이스의 운영체제 가능한 값:<ul><li>안드로이드</li><li>Windows Phone</li><li>iOS</li></ul> | 예 | 문자열 | - |
| agency | 광고 배치를 담당하는 대행사 | 아니요 | 문자열 | - |
| campaign | 광고 계층의 구성 요소 | 아니요 | 문자열 | - |
| campaign\_id | 광고 계층의 구성 요소 | 아니요 | 문자열 | - |
| 광고 세트 | 광고 계층의 구성 요소 | 아니요 | 문자열 | - |
| adset\_id | 광고 계층의 구성 요소 | 아니요 | 문자열 | - |
| 광고 | 광고 계층의 구성 요소 | 아니요 | 문자열 | - |
| ad\_id | 광고 계층의 구성 요소 | 아니요 | 문자열 | - |
| ad\_account | <ul><li>비용 데이터를 추출한 광고 계정 정보</li><li>예를 들어, Google 또는 Meta 광고에서 사용자의 자격 증명으로 연결되는 네트워크에 관련</li></ul> | 아니요 | 문자열 | - |
| 통화 | 앱스플라이어에 정의된 앱의 광고 지출 화폐 단위 | 예 | ISO-4217에 따른 3자리 코드 | ✓ |
| original\_currency | 네트워크에 의해 보고된 원본 비용의 통화 | 예 | ISO-4217에 따른 3자리 코드 | - |
| 시간대 | <ul><li>앱스플라이어에 저장된 데이터의 시간대 정보</li><li>가끔 네트워크가 앱스플라이어에서 정의된 것과 다른 시간대의 데이터를 보고하기도 합니다. 이 데이터 포인트는 앱스플라이어와 네트워크 간의 비용 차이를 설명해 줍니다</li></ul> | 예 | 문자열 | - |
| geo | 광고 계층 구조 내의 차원 | 아니요 | ISO 3166에 따른 2자리 국가 코드 | ✓ |
| channe | 광고 계층 구조 내의 차원 | 아니요 | 문자열 | - |
| keyword\_term | 사용자가 온라인 검색을 위해 입력한 단어 | 예 | 문자열 | - |
| keyword\_id | ASA 키워드 조건의 ID | 예 | 문자열 | - |
| site\_id | 퍼블리셔 ID | 아니요 | 문자열 | - |
| 캠페인 목표 | 캠페인 속성에서 중요한 구성 요소입니다. <Anchor target="_blank" href="/marketers/ko/docs/campaign-properties-in-cost-etl-reports">더 알아보기</Anchor> | 아니요 | 문자열 | - |
| cost\_model | 캠페인 속성에서 중요한 구성 요소입니다. <Anchor target="_blank" href="/marketers/ko/docs/campaign-properties-in-cost-etl-reports">더 알아보기</Anchor> | 아니요 | 문자열 | - |
| af\_cost\_model | 앱스플라이어에 의해 매핑되고 측정 기간 대비 구간별 비율로 변환된 비용 모델입니다. 캠페인 속성에서 중요한 구성 요소입니다. <Anchor target="_blank" href="/marketers/ko/docs/campaign-properties-in-cost-etl-reports">더 알아보기</Anchor> | 아니요 | 문자열 | - |
| bid\_strategy | 캠페인 속성에서 중요한 구성 요소입니다. <Anchor target="_blank" href="/marketers/ko/docs/campaign-properties-in-cost-etl-reports">더 알아보기</Anchor> | 아니요 | 문자열 | - |
| af\_bid\_strategy | 앱스플라이어에 의해 매핑되고 측정 기간 대비 구간별 비율로 변환된 입찰 전략. 캠페인 속성에서 중요한 구성 요소입니다. <Anchor target="_blank" href="/marketers/ko/docs/campaign-properties-in-cost-etl-reports">더 알아보기</Anchor> | 아니요 | 문자열 | - |
| bid\_amount | 캠페인 속성에서 중요한 구성 요소입니다. <Anchor target="_blank" href="/marketers/ko/docs/campaign-properties-in-cost-etl-reports">더 알아보기</Anchor> | 아니요 | 정수 | - |
| original\_bid\_amount | 캠페인 속성에서 중요한 구성 요소입니다. <Anchor target="_blank" href="/marketers/ko/docs/campaign-properties-in-cost-etl-reports">더 알아보기</Anchor> | 아니요 | 정수 | - |

<div id="metrics" />

#### 측정 지표

<table><thead><tr><th><strong>필드</strong></th><th><strong>설명</strong></th><th><strong>기본적으로 채워짐</strong></th><th><strong>형식</strong></th><th><strong>요약 파일에 포함</strong></th></tr></thead><tbody><tr><td>노출</td><td><ul><li>앱스플라이어로 계산됩니다.</li><li>UA 및 리타겟팅 작업을 모두 포함합니다.</li><li> </li></ul></td><td rowspan="13"><p>네.</p><p>특정 지표에 대한 값이 없으면 0으로 채워집니다.</p></td><td>정수</td><td><span>✓</span></td></tr><tr><td>클릭</td><td><ul><li>앱스플라이어로 계산됩니다.</li><li>UA 및 리타겟팅 작업을 모두 포함합니다.</li><li> </li></ul></td><td>정수</td><td><span>✓</span></td></tr><tr><td>reported_impressions</td><td>미디어 소스로 계산됩니다</td><td>정수</td><td><span>✓</span></td></tr><tr><td>reported_clicks</td><td>미디어 소스로 계산됩니다</td><td>정수</td><td><span>✓</span></td></tr><tr><td>설치</td><td>앱스플라이어로 집계됩니다</td><td>정수</td><td><span>✓</span></td></tr><tr><td>reported_conversions</td><td>미디어 소스로 계산됩니다</td><td>정수</td><td> </td></tr><tr><td>re_engagements</td><td>앱스플라이어로 집계됩니다</td><td>정수</td><td><span>✓</span></td></tr><tr><td>re_attributions</td><td>앱스플라이어로 집계됩니다</td><td>정수</td><td><span>✓</span></td></tr><tr><td>비용</td><td>해당되는 경우 에이전시 수수료를 포함한 총 지출액</td><td>값</td><td><span>✓</span></td></tr><tr><td>original_cost</td><td>네트워크가 보고한 통화단위로, 화폐 변환 전의 네트워크 비용(해당되는 경우 앱스플라이어가 계산한 대행사 수수료 포함)</td><td>값 </td><td><span>-</span></td></tr><tr><td>impressions_discrepancy</td><td><ul><li>애드 네트워크와 앱스플라이어가 집계한 수치의 차이</li><li>다음의 경우 이 지표는 고려하지 않아도 됩니다:<ul><li>비용과 어트리뷰션 데이터가 일치하지 않을 때</li><li>애드 네트워크가 노출 수를 지원하지 않는 경우 </li></ul></li></ul></td><td>정수</td><td><span>-</span></td></tr><tr><td>clicks_discrepancy</td><td><ul><li>애드 네트워크와 앱스플라이어가 집계한 수치의 차이</li><li>다음의 경우 이 지표는 고려하지 않아도 됩니다:<ul><li>비용과 어트리뷰션 데이터가 일치하지 않을 때</li><li>애드 네트워크가 클릭 수를 지원하지 않는 경우 </li></ul></li></ul></td><td>정수</td><td><span>-</span></td></tr><tr><td>installs_discrepancy</td><td><ul><li>애드 네트워크와 앱스플라이어가 집계한 수치의 차이</li><li>다음의 경우 이 지표는 고려하지 않아도 됩니다:<ul><li>비용과 어트리뷰션 데이터가 일치하지 않을 때</li><li>애드 네트..트워크가 전환 수를 지원하지 않는 경우 </li></ul></li></ul></td><td>정수</td><td><span>-</span></td></tr><tr><td>수수료</td><td>대행사가 일반적인 광고 비용 이외에 부과하는 추가 수수료입니다. 앱스플라이어가 집계함</td><td>예</td><td>정수</td><td><span>-</span></td></tr><tr><td>cost_without_fees</td><td>대행사 수수료를 제외한 순수 비용. 앱스플라이어로 집계됩니다</td><td>예</td><td>정수</td><td><span>-</span></td></tr><tr><td>original_cost_without_fees</td><td>대행사 수수료를 제외하고 애드 네트워크가 보고한 초기 비용</td><td>예</td><td>정수</td><td><span>-</span></td></tr><tr><td>CTR</td><td><ul><li>클릭률 앱스플라이어로 집계됩니다</li><li>공식: 클릭 수 / 노출 수</li></ul></td><td rowspan="12"><p>아니요</p></td><td>정수</td><td><span>-</span></td></tr><tr><td>CVR</td><td><ul><li>전환율 앱스플라이어로 집계됩니다</li><li>공식: 설치 수 / 클릭 수</li></ul></td><td>정수 </td><td><span>-</span></td></tr><tr><td>ecpm</td><td><ul><li>앱스플라이어로 집계됩니다</li><li>공식: (비용 \/ 노출) \* 1000 </li></ul></td><td>정수</td><td><span>- </span></td></tr><tr><td>cpi</td><td><ul><li>앱스플라이어로 집계됩니다</li><li>공식: 비용 / 설치 수</li></ul></td><td>정수</td><td><span>- </span></td></tr><tr><td>ccvr</td><td><ul><li>전환당 비용</li><li><span>공식: 비용 / (설치 수 + 재어트리뷰션 수 + 재참여 수)</span></li></ul></td><td>정수</td><td><span>- </span></td></tr><tr><td>반응형 비디오 시청률(CVVR)</td><td><ul><li>완료된 비디오 시청 비율. 앱스플라이어로 집계됩니다</li><li>공식: 비디오 완료 수 / 노출 수</li></ul></td><td>정수</td><td><span>-</span></td></tr><tr><td>reported_cvr</td><td><ul><li>리포트된 전환율</li><li>공식: 보고된 전환 수 / 보고된 클릭 수</li></ul></td><td>정수</td><td><span>- </span></td></tr><tr><td>ecpc</td><td><ul><li>앱스플라이어로 집계됩니다</li><li>공식: 비용 \/ 클릭</li></ul></td><td>정수</td><td><span>-</span></td></tr><tr><td>25% 비디오 시청</td><td>비디오 75% 재생됨. 애드 네트워크 보고</td><td>정수</td><td><span>- </span></td></tr><tr><td>video_50p_views</td><td>비디오 75% 재생됨. 애드 네트워크 보고</td><td>정수</td><td><span>- </span></td></tr><tr><td>video_75p_views</td><td>비디오 75% 재생됨. 애드 네트워크 보고</td><td>정수</td><td><span>- </span></td></tr><tr><td>비디오 재생 완료</td><td>애드 네트워크 보고</td><td>정수</td><td><span>- </span></td></tr></tbody></table>

</Accordion>

<div id="change-from-cost-etl-to-data-locker-connection" />

<div id="change-data-locker-connection" />

<div id="edit-connection" />

<div id="procedures" />

## 절차

이 설정 절차는 관리자만 수행해야 합니다.

**시작하기 전에**:

* * <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor> 버킷
  * <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor> bucket
  * [베타] <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor> Blob
  * [베타] <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor> 버킷
  * <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor> 데이터 웨어하우스
  * <Anchor target="_blank" href="/marketers/ko/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor> 웨어하우스

[**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) **To set up Cost ETL:**

2. * [<Image alt="" src="https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png" width="700px" />](https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png)
   * [<Image alt="" src="https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png" width="700px" />](https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png)
     1. 연결 이름을 지정합니다.  
        [<Image alt="" src="https://files.readme.io/734060321cf14a4ebbce66fe2abc71ff299218f7c52cb64dc5b8e71c42d3632d-31233921530001.png" width="2100px" />](https://files.readme.io/734060321cf14a4ebbce66fe2abc71ff299218f7c52cb64dc5b8e71c42d3632d-31233921530001.png)
     2. **클라우드 서비스 데이터 목적지 선택**. 다음 중 하나를 선택하세요.
        * **S3**을 선택합니다.  
          [<Image alt="" src="https://files.readme.io/1a78090f00407d44a5b74f3cb3b94e3a28064bc9b991b1cecf506fa0b9053842-31233961351441.png" width="945px" />](https://files.readme.io/1a78090f00407d44a5b74f3cb3b94e3a28064bc9b991b1cecf506fa0b9053842-31233961351441.png)
          1. AWS S3 버킷 이름을 입력하십시오. `af-`af-af- 접두사는 필수이며 수동으로 입력해야 합니다.
          2. **연결 테스트**를 클릭하세요.
          3. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
          4. **이 연결을 Adobe Experience Platform과 호환할지**여부를 선택합니다.
          5. **저장**을 클릭하세요.
        * **GCS**를 선택합니다.  
          [<Image alt="" src="https://files.readme.io/6da526f43131887270136e9fcfa9434ad88c2ce8cebdb896c07dac4a0652d683-31233921536913.png" width="944px" />](https://files.readme.io/6da526f43131887270136e9fcfa9434ad88c2ce8cebdb896c07dac4a0652d683-31233921536913.png)
          1. 사용자의 GCS 버킷 이름을 입력합니다.
          2. **연결 테스트**를 클릭하세요.
          3. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
          4. **이 연결을 Adobe Experience Platform과 호환할지**여부를 선택합니다.
          5. **저장**을 클릭하세요.
        * [베타] **Azure**를 선택합니다.  
          [<Image alt="" src="https://files.readme.io/cd718eeebc5965d24a2d38457d4fa22c5691d6a186464187bea12199fb96671b-31233921550481.png" width="943px" />](https://files.readme.io/cd718eeebc5965d24a2d38457d4fa22c5691d6a186464187bea12199fb96671b-31233921550481.png)
          1. **연결** 이름, **스토리지 계정 이름** 및 **키를** 입력합니다.
          2. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
          3. **이 연결을 Adobe Experience Platform과 호환할지**여부를 선택합니다.
          4. **저장**을 클릭하세요.
        * [베타] **Yandex**를 선택합니다.  
          [<Image alt="" src="https://files.readme.io/230e0d9c0b56b4c9f85da8c97f1ab91818c16ecfbabbf81ecb35f12d41716888-31233961360273.png" width="944px" />](https://files.readme.io/230e0d9c0b56b4c9f85da8c97f1ab91818c16ecfbabbf81ecb35f12d41716888-31233961360273.png)
          1. **버킷 이름**, **액세스 키** 및 **비밀 키**를 입력합니다.
          2. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
          3. **이 연결을 Adobe Experience Platform과 호환할지**여부를 선택합니다.
          4. **저장**을 클릭하세요.
        * **BigQuery**를 선택합니다.  
          [<Image alt="" src="https://files.readme.io/6989fa8c869c08440da757b3ebb385754a4f23dbe4e2d38c50837448c08ab03b-31233921555857.png" width="945px" />](https://files.readme.io/6989fa8c869c08440da757b3ebb385754a4f23dbe4e2d38c50837448c08ab03b-31233921555857.png)
          1. BigQuery 프로젝트 ID와 데이터세트 이름을 입력합니다.
          2. **연결 테스트**를 클릭하세요.
          3. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
          4. **저장**을 클릭하세요.
        * Snowflake를 선택합니다.  
          [<Image alt="" src="https://files.readme.io/b0e5f5ece797f46006d6e29a6afd01bc120b035590bd2ee87a54daa8c36bb0ed-31233961363985.png" width="944px" />](https://files.readme.io/b0e5f5ece797f46006d6e29a6afd01bc120b035590bd2ee87a54daa8c36bb0ed-31233961363985.png)
          1. Snowflake 영역과 계정 ID를 입력합니다.
          2. **연결 테스트**를 클릭하세요.
          3. 버킷 경로가 잘못되었다는 오류 메시지가 표시되지 않는지 확인하십시오.
          4. **저장**을 클릭하세요.
3. **다음**을 클릭합니다.  
   [<Image alt="" src="https://files.readme.io/4237ca8e7e70e0c04e924b61839d47d88e42075b4c257fcdf5e78870712d3582-31233921563153.png" width="746px" />](https://files.readme.io/4237ca8e7e70e0c04e924b61839d47d88e42075b4c257fcdf5e78870712d3582-31233921563153.png)
4. [<Image alt="" src="https://files.readme.io/427b18043c0ab53ea559d53094efb6f04ad7505659c08ba7345b3a647f78d64d-31233961369105.png" width="607px" />](https://files.readme.io/427b18043c0ab53ea559d53094efb6f04ad7505659c08ba7345b3a647f78d64d-31233961369105.png)

   2. [더 알아보기](/docs/set-up-and-use-roi360-cost-etl-reports#report-schedule)
   3. **다음**을 클릭합니다.
5. 1. [<Image alt="" src="https://files.readme.io/a5d453f40a7c5318f6a4c6cdfc5cf4d645c540c4b684362a796cda41d3c058c6-31233961373585.png" width="566px" />](https://files.readme.io/a5d453f40a7c5318f6a4c6cdfc5cf4d645c540c4b684362a796cda41d3c058c6-31233961373585.png)
   2. [<Image alt="" src="https://files.readme.io/3662c55c71f3390ac651c9269eac519f846b53ad675dab224b62fb09f81d4578-31233921571345.png" width="1921px" />](https://files.readme.io/3662c55c71f3390ac651c9269eac519f846b53ad675dab224b62fb09f81d4578-31233921571345.png)
      * 요약
      * 지역
      * channe
      * **[베타 단계] 모든 광고 비용 리포트: 지역 차원을 바탕으로 합니다. 앱스플라이어에 추가되지 않은 앱/플랫폼을 포함해 모든 마케팅 활동의 비용 데이터가 포함됩니다(이 경우 앱 ID는 알 수 없음으로 표시됩니다.**
   3. **참고**:    
      [<Image alt="" src="https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png" width="1921px" />](https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png)
   4. [<Image alt="" src="https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg" width="1863px" />](https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg)
6. **Apply(적용)** 을 클릭합니다.


**참고**:


2. * [<Image alt="" src="https://files.readme.io/95c76d3bfc4a4db4bb9b4e67e4460680e0039e91dd930903515771e52c00ac7a-31233961377937.png" width="695px" />](https://files.readme.io/95c76d3bfc4a4db4bb9b4e67e4460680e0039e91dd930903515771e52c00ac7a-31233961377937.png)
   * [<Image alt="" src="https://files.readme.io/67a1fb2ce45a49fc75d12eba4d1c3e67875b83883b0fc05307c080c6050be0f2-31233961380369.png" width="651px" />](https://files.readme.io/67a1fb2ce45a49fc75d12eba4d1c3e67875b83883b0fc05307c080c6050be0f2-31233961380369.png)


2. * [<Image alt="" src="https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png" width="700px" />](https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png)
   * [<Image alt="" src="https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png" width="700px" />](https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png)
3. **변경 사항 저장**을 클릭합니다.


**시작하기 전**:

2. [<Image alt="" src="https://files.readme.io/2608d88368579c9fd3aa7648905484a56a7f0d989a96582cee51303409ce427c-31233961382289.png" width="631px" />](https://files.readme.io/2608d88368579c9fd3aa7648905484a56a7f0d989a96582cee51303409ce427c-31233961382289.png)
3. * [<Image alt="" src="https://files.readme.io/da486f6399e92c49923527da3348f4535691768cebd7a776ec84f7a2a739c204-31233961385617.png" width="501px" />](https://files.readme.io/da486f6399e92c49923527da3348f4535691768cebd7a776ec84f7a2a739c204-31233961385617.png)
   * [<Image alt="" src="https://files.readme.io/0d48f83f30954f5f68efecf7e6c4cf2b39b295e0b893711bd2e2756406c42461-31233921587985.png" width="631px" />](https://files.readme.io/0d48f83f30954f5f68efecf7e6c4cf2b39b295e0b893711bd2e2756406c42461-31233921587985.png)
4. **변경 사항 저장**을 클릭합니다.


AWS에서 앱스플라이어가 귀하의 버킷에 객체를 작성할 기본 설정으로, 객체의 소유자는 앱스플라이어가 됩니다. 데이터 로딩 과정에 따라 기본 소유자를 버킷 소유자인 귀사로 변경해야 할 필요가 있을 수 있습니다.

버킷 내 객체의 소유권을 변경하는 방법:

1. AWS 관리 콘솔에 로그인한 후 <Anchor target="_blank" href="https://console.aws.amazon.com/s3/">https://console.aws.amazon.com/s3/</Anchor><Anchor target="_blank" href="https://console.aws.amazon.com/s3/">에서 Amazon S3 콘솔을 열어 주세요.</Anchor>
2. **버킷** 목록에서 S3 객체 소유권을 설정하고자 하는 버킷의 이름을 선택하세요.
3. **권한** 탭으로 이동합니다.
4. **객체 소유권** 섹션에서 **편집** 버튼을 클릭하세요.
5. **버킷 소유자 우선.** 옵션을 선택하세요.
6. **저장**을 클릭합니다.


<div id="best-practices" />

## 모범 활용 사례

<div id="override-data" />

<Accordion title="데이터 덮어쓰기">

데이터를 추출해서 분석할 때, 특정 날짜와 배치에 대한 데이터를 선택하거나 해당 배치가 제공하는 날짜에 대한 기존 데이터를 모두 덮어쓰는 것을 권장합니다. 그렇지 않을 경우 동일한 데이터가 반복되어 보일 수 있습니다.

예를 들어, 2월 20일 배치 1은 2월 14일부터 20일까지의 데이터를 포함합니다. 하지만, 2월 19일에 작성된 배치는 2월 14일부터 19일까지의 데이터를 포함하고 있었습니다. 2월 19일에 받은 이전 날짜의 데이터를 가장 최근에 받은 2월 20일 배치 데이터로 덮어쓰세요.

</Accordion>

<div id="geo-versus-channel" />

<Accordion title="지역 대 채널">

모든 네트워크가 모든 차원의 데이터를 제공하는 것은 아닙니다. Meta 광고에서 볼 수 있는 지역과 채널 데이터가 대표적인 예입니다. 이것이 서로 다른 두 데이터 세트를 제공하는 이유입니다. 지역 데이터 세트는 지역 정보를, 채널 데이터 세트는 채널 정보를 갖고 있음을 보장합니다.

많은 경우와 다양한 미디어 소스에 대해, 지역 및 채널 세트의 데이터가 서로 일치할 수 있습니다. 그러므로, 귀하의 필요에 가장 적합한 데이터 세트(지역 또는 채널)를 선택하여 사용하세요.

특정 미디어 소스와의 통합 협약에 채널 정보가 포함되지 않아 채널 항목이 비어 있더라도, 해당 데이터가 채널 정보를 포함한다고 간주합니다.

</Accordion>

<div id="aggregate-data" />

<Accordion title="데이터 집계">

비용 ETL은 광고 네트워크에서 추출할 수 있는 만큼 깊이 있는 유연하고 세밀한 데이터를 제공합니다. 엄청난 양의 데이터에서 실행 가능한 통찰을 얻고자 한다면, 귀사의 비즈니스 요구를 가장 잘 충족시키는 방향으로 데이터를 요약하는 것이 바람직합니다. 예를 들어, 캠페인 및 국가 수준에서 비용 데이터를 분석해야 한다면, 그에 맞는 차원을 활용하세요.

</Accordion>

<div id="standardization-across-networks" />

<Accordion title="네트워크 간의 표준화">

모든 네트워크가 같은 수준의 세부 데이터를 제공하는 것은 아닙니다. 예를 들어, Meta 광고는 사이트 ID에 관한 비용 데이터를 제공하지 않고, X 광고는 지역에 따른 비용 데이터를 제공하지 않습니다. Cost ETL 데이터를 집계할 때 이러한 사항을 주의 깊게 살펴보고, 네트워크를 비교할 때는 유사한 데이터를 검토해야 합니다.

</Accordion>

<div id="compare-data" />

<Accordion title="데이터 비교">

Cost ETL은 귀사의 모든 비용 데이터에 관한 정보를 제공합니다. Cost ETL에 제공된 일부 캠페인은 앱스플라이어 대시보드에서 보이지 않는 경우가 있습니다(예: 비활성 캠페인 데이터, 즉 기록된 인스톨이 없는 캠페인). 데이터를 비교하고자 할 때는 개요 대시보드에서 특정 캠페인 ID를 찾아 Cost ETL의 비용 데이터와 비교하세요. 비용 데이터 가용성에 대해 자세히 알아보기

</Accordion>

<div id="combine-cost-etl-and-cohort-reports" />

<Accordion title="Cost ETL과 코호트 보고서 병합">

<Anchor target="_blank" href="/marketers/ko/docs/combine-cost-etl-and-cohort-reports-via-data-locker">더 알아보기</Anchor>

</Accordion>

<div id="additional-information" />

## 추가 정보

<div id="traits-and-limitations" />

<Accordion title="특성 및 한계">

| 특징 | 설명 |
| --- | --- |
| 시간대 | 표준 시간대가 변경되면 비용 데이터는 변경 당일과 익일에 중복됩니다. <Anchor target="_blank" href="/marketers/ko/docs/changing-app-time-zone-settings">더 알아보기</Anchor> |
| 데이터 최신성 | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">일중</Anchor>. Cost ETL을 설정할 때는 보고서를 받고자 하는 시간, 즉 보고서 스케줄을 정합니다.</li></ul>**참고**: 귀사의 버킷에 비용 데이터가 도착하면, 리포트 및 parquet 파일의 크기에 따라 귀사의 BI 시스템으로의 데이터 전송 속도가 크게 달라질 수 있으며, 이는 수 KB에서 수 GB에 이르는 다양한 크기를 가질 수 있습니다. |
|  |  |

</Accordion>

<div data-zendesk-anchors="h_01HA29GW8PVZJ8MP23K7QVR40J=cost-etl-principles 01JCZDREEY73373HQCFJK8D163=report-details h_01HA29GW8PWN30BCQCK29V0FTA=directory-and-filename-structure h_01HA29GW8P0B1JJTGYDW863D7Z=file-fields fieldsdimensions=%ED%95%84%EB%93%9C-%EB%B0%8F-%EC%B0%A8%EC%9B%90 h_01HA29GW8PQATB4K5VJP1HD4NW=%ED%95%84%EB%93%9C-%EB%B0%8F-%EC%B0%A8%EC%9B%90 metrics=%EC%B8%A1%EC%A0%95-%EC%A7%80%ED%91%9C h_01HA29GW8PZTS7XDWGYWXFZPYG=%EC%B8%A1%EC%A0%95-%EC%A7%80%ED%91%9C procedures=%EC%A0%88%EC%B0%A8 01JCZDRERADNNX04RT752793PG=%EC%A0%88%EC%B0%A8 edit-connection=%EC%A0%88%EC%B0%A8 change-data-locker-connections=%EC%A0%88%EC%B0%A8 h_01JCZMGC8J41Y7H4JGZDVWYDJS=%EC%A0%88%EC%B0%A8 h_01JCZNQF3QE7P8PBQPKXZK1SA2=%EC%A0%88%EC%B0%A8 change-from-cost-etl-to-data-locker-connection=%EC%A0%88%EC%B0%A8 h_01JKWMF6V70W9FA90SSKJ77R2Z=%EC%A0%88%EC%B0%A8 best-practices=%EB%AA%A8%EB%B2%94-%ED%99%9C%EC%9A%A9-%EC%82%AC%EB%A1%80 h_01HA29GW8QKPQXE4GHECAC5R5X=%EB%AA%A8%EB%B2%94-%ED%99%9C%EC%9A%A9-%EC%82%AC%EB%A1%80 h_01HA29GW8QHX8AMK4T7E85H7RS=override-data h_01HA29GW8QT5FNNYSWHCT99D68=geo-versus-channel h_01HA29GW8QA3FP46EMZVYDEZF3=aggregate-data h_01HA29GW8QPW0NXEMF1WGJMKSF=standardization-across-networks h_01HA29GW8Q3FNS0W7SKTG7S9R1=compare-data h_01J582E5JNR5DJ9T8HKDG2XSRR=combine-cost-etl-and-cohort-reports additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HA286GA6WPYVNN7KCXK7DGFM=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HA282W8WHHNDG75XZNSV2QQF=traits-and-limitations" />
