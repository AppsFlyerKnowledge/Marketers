---
title: SKAN 로데이터 리포트
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T20:54:55Z'
  edited_at: '2026-10-14T10:38:44Z'
  id: 360014261518
  locale: ko
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ko/articles/360014261518
---
> **한눈에 보기:** SKAN 로데이터 리포트는 SKAN 포스트백뿐만 아니라 앱스플라이어가 iOS로부터 수신한 포스트백을 해석하고 디코딩한 후 생성하는 정보도 포함합니다. 세션 로데이터는 **데이터 락커**를 통해 사용 가능합니다.

<div id="skan-raw-data-reports" />

## SKAN 로데이터 리포트

원리:

* **데이터는 다음에서 제공합니다.**
  * **데이터 락커**
    * **참고**! 일러두기! 로데이터 구독을 가진 계정에서 사용 가능합니다. 즉, 데이터 락커 구독이 필요하지 않다는 뜻입니다. 현재 데이터 락커를 사용하지 않는 경우 관리자는 데이터 락커를 설정하고 SKAN 리포트를 활성화해야 합니다. 이렇게 하려면 **보고서** > **데이터 락커**로 이동합니다. SKAN 리포트를 선택합니다.
    * 데이터 최신성 비율 일별. 데이터는 앱스플라이어가 포스트백을 받은 날짜의 h=23 폴더에 포함됩니다.
  * **Push API**
    * 데이터 최신성:
* 설치 날짜 인스톨 날짜: 다음과 같이 앱스플라이어의 포스트백 도착 시간에서 파생됩니다.
  * 포스트백이 SKAN V4인 경우 설치 날짜 공식은 다음과 같습니다. 설치 날짜 = 포스트백 도착 시간 - [누적 윈도우 길이] - [평균 포스트백 지연].
    * 포스트백 1: 설치 날짜 = 포스트백 도착 시간 - 48시간 - 36시간
    * 포스트백 2: 설치 날짜 = 포스트백 도착 시간 - 168시간 - 84시간
    * 포스트백 3: 설치 날짜 = 포스트백 도착 시간 - 840시간 - 84시간
  * 포스트백이 SKAN V3인 경우 설치 날짜 공식은 다음과 같습니다. 설치 날짜 = 포스트백 도착 시간 - 36시간 - [평균 최종 활성 범위]. 
    * 기본값 [평균 최종 활성 범위]는 12시간입니다.
    * 전환 값이 0인 경우 평균 최종 활성 범위는 0으로 설정됩니다.
  * 구글은 자체적으로 설치 시간을 추정하고 앱스플라이어는 해당 설치 시간을 사용합니다. **참고**: Google에서 인스톨을 리포트하는 데 최대 13일이 소요될 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/get-skan-postback-data-from-google-ads#google-ads에서-skan-포스트백-데이터-가져오기">더 알아보기</Anchor>

사용할 수 있는 리포트 유형은 다음과 같습니다.

* **디바이스 포스트백**: iOS 기기에서 받은 인스톨 또는 재다운로드당 디바이스 포스트백 1개.
* **SKAN 로데이터**:
  * 앱스플라이어는 기기 포스트백을 디코딩하고 로데이터 기록으로 변환합니다.
  * 각 포스트백은 인스톨 또는 재다운로드 기록 및 인앱 이벤트 기록을 생성합니다.
  * 인앱 이벤트 기록의 개수는 다음과 같은 전환 값(CV)에 따라 달라집니다.
    * CV = 0, 공백 또는 null 인앱 기록이 생성되지 않습니다.
    * CV 범위:
      * 1-63: 1-63: SKAN 3 및 SKAN 4 기간 1 fine 값의 경우, 이는 측정 설정에 따라 인앱 레코드의 수입니다.
      * 낮음, 중간, 높음 낮음, 중간 또는 높음: SKAN 4 coarse 값의 경우, 이는 측정 설정에 따라 인앱 레코드의 수입니다.

**일부 필드가 비어 있는 이유는 무엇입니까?** 다음 이유들로 인해 발생합니다.

* 광고 네트워크가 제공하지 않는 campaign\_name, ad\_network\_campaign\_id, ip 등의 임의 보강 필드.
* 애플의 개인정보보호 기준(privacy threshold)에 따라 데이터를 공개하지 않았습니다. source\_app\_id, skad\_campaign\_id, skad\_conversion\_value 등의 필드.

<div id="skan-raw-data-report-format-and-content" />

## SKAN 로데이터 리포트 형식 및 콘텐츠

<div id="raw-data-report-types" />

<Accordion title="로데이터 리포트 형식">

<Table>
  <thead>
    <tr>
      <th>
        리포트 유형
      </th>
      <th>
        리포트 이름
      </th>
      <th>
        설명
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="postback"></span>
        포스트백
      </td>
      <td>
        포스트백
      </td>
      <td>
        iOS에서 광고 네트워크로 포스트백을 보냈습니다. 포스트백은 광고 네트워크에 의해 보강된 후 앱스플라이어로 보냅니다. [포스트백 예시 다운로드](https://docs.google.com/spreadsheets/d/e/2PACX-1vRfFFmj1YV1c73Wbar2VOiKWml6VmsyFvQuydXTPUOO4zXVKmwtw6nup9vKNtNwou2z8IqNpcF4yP6c/pub?gid=1225544365&single=true&output=csv) (CSV).

        참고: 참고: did\_win=false인 경우 포스트백이 포함되지 않습니다.

        **데이터 락커의 주제 이름**: skad\_postbacks
      </td>
    </tr>
    <tr>
      <td><span id="postback::315d5a62"></span>
        포스트백
      </td>
      <td>
        포스트백 복사(Apple에서 직접)
      </td>
      <td>
        포스트백은 iOS에서 앱스플라이어로 직접 보냈습니다.

        iOS 15 이상에서 사용 가능하며 앱스플라이어로 <Anchor target="_blank" href="/marketers/ko/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">당첨 포스트백을 보내려면</Anchor> 광고주가 앱을 설정해야 합니다. [포스트백 복사 다운로드 예시](https://docs.google.com/spreadsheets/d/e/2PACX-1vSu0c3gYoIHe2k6_M3cngSFzc-txQvEN38X7Ig7qhXYPg8uBUzyyPqlSwDMugvZS_tUrFjtY8AGYKrh/pub?gid=1225544365&single=true&output=csv) (CSV).

        참고: 일러두기: 이 주제에는 당첨 포스트백만 포함되어 있습니다.

        **데이터 락커의 주제 이름**: skad\_postbacksskad\_postbacks\_copy
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event"></span>
        해독한 이벤트
      </td>
      <td>
        인스톨
      </td>
      <td>
        **첫 앱 인스톨**

        SKAN *redownload=false*를 리포트했습니다. 즉, Apple ID로 대표되는 사용자가 앱을 다운로드한 첫 번째 기회라는 뜻입니다.  
        [인스톨 다운로드 예시](https://docs.google.com/spreadsheets/d/e/2PACX-1vS4rNJAio8Ub2cffUEiYhzdavVfXaJAD6OpjhRBjVpGQsAlibOWCkZpfLl29n1OCDBZ2eToO4_gOvbl/pub?gid=1472391837&single=true&output=csv) (CSV).

        **데이터 락커의 주제 이름**: skad\_installs
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5c7e459f"></span>
        해독한 이벤트
      </td>
      <td>
        재다운로드
      </td>
      <td>
        **처음 인스톨이 아닌 앱 인스톨**

        SKAN *redownload=true*를 리포트했습니다. 즉, Apple ID로 대표되는 사용자가 앱을 다운로드한 첫 번째 기회가 아니라는 뜻입니다. 이 리포트는 인스톨과 동일한 구조를 가집니다.

        **데이터 락커의 주제 이름**: skad\_redownloads
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::b8f2b4a4"></span>
        해독한 이벤트
      </td>
      <td>
        인앱 이벤트
      </td>
      <td>
        **인앱 이벤트**

        2021년 7월 21일부터 시작하여 표에 자세히 나와 있는 것처럼 인앱 이벤트 로데이터를 제공하는 방법이 변경되었습니다.

        인앱 이벤트 기록의 횟수는 측정 설정에 따라 다릅니다.

        [인앱 이벤트 다운로드 예시](https://docs.google.com/spreadsheets/d/e/2PACX-1vRwhxOmZwTkOr9uNFN0d4Rk2jFpipONoB8KzIZI5Tw12IvoLirj07QUdI9RJoL9rZYFSN1PvT-W6vP0/pub?gid=1454741057&single=true&output=csv) (CSV).

        **데이터 락커의 주제 이름**: skad\_inapps

        2021년 7월 21일부터 받은 iOS 포스트백에 대해 유효합니다.

        | 측정 유형 | 설명 |
        | --- | --- |
        | 수익 | * 해당 사용자의 수익. 수익이 0 이상이면, skad\_revenue 및 event\_name 필드를 포함하는 기록.<br />* min\_revenue 및 max\_revenue 필드는 사용자정의 전환 범위 값으로 채워집니다. |
        | 인앱 전환 및 퍼널 이벤트 | * 고유한 각 전환 이벤트에 대한 기록이 수행되었습니다. 그러면 event\_name 필드가 채워집니다. 수행한 이벤트가 없는 경우 기록이 없습니다.<br />* 전환 이벤트는 min\_event\_counter = 0이고 max\_event\_counter = 1입니다. |
        | 인앱 인게이지먼트 |  |

        2021년 7월 20일까지 받은 iOS 포스트백에 대해 유효합니다.

        | 측정 유형 | 기록의 개수 | 설명 |
        | --- | --- | --- |
        | 수익 | 0-1 | 수익이 0 이상이면, skad\_revenue 및 event\_name 필드를 포함하는 기록. |
        | 전환 | 0-6 | 고유한 각 전환 이벤트에 대한 기록이 수행되었습니다. 그러면 event\_name 필드가 채워집니다. 수행한 이벤트가 없는 경우 기록이 없습니다. |
        | 인게이지먼트 | 0-63 | 기록의 개수는 사용자가 인게이지먼트 이벤트를 수행한 횟수를 표시합니다. 사용자가 인게이지를 수행하지 않는 경우 인게이지먼트 기록이 없습니다. |
        | 커스텀 | 0 - 무제한 | 사용자정의 전환 스키마에 따릅니다. |
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5dac9cbb"></span>
        해독한 이벤트
      </td>
      <td>
        SRN 광고 차원
      </td>
      <td>
        * 리포트에는 캠페인, 광고 세트 및 광고 세분화가 포함된 메타 광고 이벤트가 포함되어 있습니다. 리포트의 각 행은 인스톨 또는 인앱이벤트일 수 있습니다.
        * 리포트는 스키마리스입니다. 데이터 락커 필드 선택 옵션이 적용되지 않습니다.
        * 모범 사례:
        * <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTZjIpqZJxHY9WpIdf9OeDCVQYzM_fLmrpB1oAt3S-MbJTKueOJODwwl6Pz3M0SCAbCFIdMlshOayrw/pub?output=xlsx">SRN 광고 기준 예시를 다운로드합니다</Anchor> (CSV).

        **데이터 락커의 주제 이름** : skad\_srn\_advertising\_dimensions
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-field-format-types" />

<Accordion title="로데이터 필드 형식 유형">

<div id="field-formats" />

#### 필드 형식

| 필드 이름 | 설명 |
| --- | --- |
| 문자열 [n] | 문자열의 최대 길이. 일반적으로 데이터 수신 시에는 필드 길이 제한 사항을 적용하지 않지만 수신 이후에 데이터가 잘릴 수 있습니다. |
| 시간 문자열 | 예를 들어: |
| Enum [n] | 열거형 필드는 특정 값만 포함할 수 있습니다. 예를 들어, 비용 통화는 3자이며 지정된 통화 코드만 포함할 수 있습니다. |
| 타임스탬프 | 10자리 UNIX 타임 스탬프. 예시:<br /><br />2020년 8월 4일 07:25 UTC는 다음과 같이 변환됩니다. |
| Boolean | 필드의 값은 또는 중 하나일 수 있습니다. |
| 정수 | 정수 |
| Float | 소수점과 소수점 뒤의 값을 가질 수 있는 실제 부동소수입니다. |

</Accordion>

<div id="fields-available-in-postback-and-postback-copy-reports" />

<Accordion title="포스트백 및 포스트백 사본 리포트에서 사용 가능한 필드">

<table><thead><tr><th>필드 이름</th><th>소스 또는 iOS SKAN 시작 버전</th><th>설명</th><th>형식</th><th>포스트백 복사본에서 사용 가능  </th></tr></thead><tbody><tr><td>애드 네트워크 캠페인 ID</td><td>애드 네트워크</td><td>애드 네트워크가 앱스플라이어에 보고한 캠페인 ID</td><td>문자열</td><td>아니요</td></tr><tr><td><p>ad_network_campaign</p><p>_name</p></td><td>애드 네트워크</td><td><p>애드 네트워크가 앱스플라이어에 리포트한 캠페인 이름.</p></td><td>문자열</td><td>아니요</td></tr><tr><td>ad_network_timestamp</td><td>애드 네트워크</td><td><p>광고 네트워크가 포스트백을 받은 시간.</p><p>Google Ads의 경우 시간은 Google에서 리포트한 라스트 클릭에서 추출합니다.</p></td><td>타임스탬프</td><td>아니요</td></tr><tr><td>app_id</td><td>앱스플라이어</td><td>접두사 ID를 가진 앱 ID(광고주 앱).</td><td>문자열</td><td>예</td></tr><tr><td>도시</td><td>앱스플라이어</td><td>2021년 8월 30일부터 항상 null입니다.  </td><td>문자열</td><td>아니요</td></tr><tr><td>country_code</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>dma</td><td> </td><td>2021년 8월 30일부터 항상 null입니다.  </td><td>문자열</td><td>아니요</td></tr><tr><td>postal_code</td><td> </td><td>2021년 8월 30일부터 항상 null입니다.   </td><td>문자열</td><td>아니요</td></tr><tr><td>지역</td><td>앱스플라이어</td><td>리포트된 country_code에 따라</td><td>문자열</td><td>아니요</td></tr><tr><td>skad_ad_network_id</td><td>1.0 </td><td>일부 SRN은 ID를 공유하지 않으며 필드가 비어 있습니다. 예를 들어, X 광고.  </td><td>문자열</td><td>예 </td></tr><tr><td>skad_attribution_signature</td><td>1.0</td><td> </td><td>문자열</td><td>예</td></tr><tr><td>skad_campaign_id</td><td>1.0</td><td>광고를 게시하는 데 사용되는 캠페인 ID 범위 0-100</td><td>문자열</td><td>예</td></tr><tr><td>skad_전환_가치</td><td>2.0 </td><td><p>iOS 에서 보고된 전환 값입니다. 범위 0-63.</p><p>null인 경우 iOS는 필드\*\*를 채우지 않습니다. </p></td><td>정수</td><td>예</td></tr><tr><td>skad_redownload</td><td>2.0</td><td>true인 경우 앱은 다시 다운로드되었습니다</td><td>Boolean</td><td>예</td></tr><tr><td>skad_source_app_id</td><td>2.0</td><td><p>사이트 ID. 광고를 게재하는 앱입니다. 이 필드는source_app_id와 동일합니다.</p><p>필드 채우기는 프라이버시 임계값에 따라 달라집니다\*\*</p></td><td>문자열</td><td>예</td></tr><tr><td>skad_transaction_id</td><td>1.0</td><td> </td><td>문자열</td><td>예</td></tr><tr><td>skad_version</td><td>2.0</td><td> </td><td>문자열</td><td>예</td></tr><tr><td>타임스탬프</td><td>애드 네트워크</td><td>앱스플라이어가 SKAN 포스트백을 받은 시간. </td><td>시간문자열</td><td>예</td></tr><tr><td>애드 네트워크 이름</td><td>애드 네트워크</td><td>애드 네트워크가 앱스플라이어에 보고한 애드 네트워크 이름입니다. <ul><li>이 필드가 비어 있으면 애드 네트워크가 해당 정보를 제공하지 않았거나 제공할 수 없습니다.</li><li>skad_ad_network_id를 사용하여 애드 네트워크 이름을 확인할 수 있습니다. 이를 위해 <a href="./skan-integrated-partners-list#apple-skadnetwork-ids-of-ad-networks" target="_blank">이 표</a>를 사용하세요. </li></ul></td><td>문자열</td><td>아니요</td></tr><tr><td>ip</td><td> </td><td><p>포스트백을 보내는 iOS 장치의 HTTP 메시지에 포함된 IP 주소.</p><p>광고 네트워크가 이 주소를 제공하면 이 필드가 채워집니다.</p><p>참고! SDK는 주소를 가져오는 데 관여하지 않습니다.</p></td><td>문자열</td><td>아니요</td></tr><tr><td>skad_app_id</td><td>1.0</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>source_app_id</td><td>앱스플라이어</td><td>사이트 ID. 광고를 게재하는 앱입니다. 이 필드는 skad_source_app_id와 동일합니다.</td><td>문자열</td><td>아니요</td></tr><tr><td>애드 네트워크 광고 세트 ID</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>애드 네트워크 광고 세트 이름</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>애드 네트워크 광고 이름</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>애드 네트워크 광고 ID</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>did_win</td><td>3.0(iOS 14.6)</td><td>캠페인이 인스톨에 <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">기여했거나 어트리뷰션된</a> 경우를 구별하는 데 사용됩니다. <ul><li>진실이라면, 캠페인은 인스톨을 가져온 것으로 간주됩니다.</li><li>false인 경우, 캠페인이 인스톨에 기여한 것으로 인식되지만 SKAN 대시보드나 보고서에는 포함되지 않습니다.</li><li>null인 경우 <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">레거시 iOS 또는 SKAdNetwork 버전</a>으로 인해 iOS가 필드를 채우지 않습니다.</li></ul></td><td>Boolean</td><td>예</td></tr><tr><td>fidelity_type</td><td>2.2(iOS 14.5)</td><td><p>어트리뷰션에 영향을 주는 <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">광고 프레젠테이션</a> 옵션 차이를 식별합니다. 다음과 같이 0과 1의 값으로 표시됩니다. </p><ul><li>시청 기반 광고 (0)</li><li>StoreKit 광고 (1)</li></ul><p>SKAN 버전이 2.2 이전인 경우 필드 값을 무시하세요.</p></td><td>정수</td><td>예</td></tr><tr><td>ad_network_source_app_id</td><td>애드 네트워크</td><td><span>애드 네트워크가 보고한 퍼블리셔 앱 ID입니다. 비용 조정 시 사용되며 애드 네트워크에 의해 보고됩니다. 퍼블리셔 앱은 이 데이터의 기반을 제공합니다. </span></td><td>문자열</td><td>아니요</td></tr><tr><td>애드 네트워크 채널</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>af_prt</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>skad_포스트백_서열_인덱스</td><td>4.0 (iOS 16.2)</td><td><ul><li>값은 SKAN 기간, 즉 0, 1 또는 2를 나타냅니다.</li><li>SKAN 3의 경우 값은 0 </li></ul></td><td>정수</td><td>예</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0 (iOS 16.2)</p></td><td><ul><li> </li><li>SKAN 3의 경우 값은 0</li></ul></td><td>문자열</td><td>예</td></tr><tr><td>skad_source_identifier</td><td>4.0 (iOS 16.2)</td><td><ul><li>값은 최대 4자리까지 가능합니다.</li><li>SKAN 3의 경우 값은 0 </li></ul></td><td>문자열</td><td>예</td></tr><tr><td>skad_source_domain</td><td>4.0 (iOS 16.2)</td><td><ul><li>값은 어트리뷰션이 가능한 웹 광고의 소스를 나타냅니다.</li><li>SKAN 3의 경우 값은 0</li></ul></td><td>문자열</td><td>예</td></tr><tr><td>애드 네트워크 크리에이티브</td><td>애드 네트워크</td><td><ul><li>값은 애드 네트워크에서 수신한 데이터 보강에 기반합니다.</li><li>SKAN 3의 경우 값은 0</li></ul></td><td>문자열</td><td>아니요</td></tr><tr><td colspan="4">\*\* Apple은 프라이버시 임계값 메커니즘을 사용하여 필드를 채우는지 여부를 판별합니다. </td><td> </td></tr></tbody></table>

</Accordion>

<div id="fields-available-in-decoded-event-reports" />

<Accordion title="디코딩된 이벤트 리포트에서 사용 가능한 필드">

<table><thead><tr><th>필드 이름</th><th>소스</th><th>설명</th><th>형식</th><th>SRN 광고 기준 리포트에 포함됨</th></tr></thead><tbody><tr><td>애드 네트워크 캠페인 ID</td><td>애드 네트워크</td><td>애드 네트워크가 앱스플라이어에 보고한 캠페인 ID</td><td>문자열</td><td>예</td></tr><tr><td>ad_network_campaign<br/>_name</td><td>애드 네트워크</td><td>애드 네트워크가 앱스플라이어에 보고한 캠페인 이름</td><td>문자열</td><td>예</td></tr><tr><td>ad_network_timestamp</td><td>애드 네트워크</td><td><p>광고 네트워크에서 포스트백을 받은 시간</p><p>Google Ads의 경우 이 필드는 채워지지 않습니다. </p></td><td><p>타임스탬프</p><p>(SRN 광고 기준 리포트의 시간 문자열)</p></td><td>예</td></tr><tr><td>app_id</td><td>iOS</td><td>앱 ID(광고주 앱)</td><td>문자열</td><td>예</td></tr><tr><td>도시</td><td> </td><td>2021년 8월 30일부터 항상 null입니다.  </td><td>문자열</td><td>아니요</td></tr><tr><td>country_code</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>dma</td><td> </td><td>2021년 8월 30일부터 항상 null입니다.  </td><td>문자열</td><td>아니요</td></tr><tr><td>event_name</td><td>앱스플라이어</td><td><p>앱스플라이어에 설정된 인앱이벤트 이름.</p><p>SRN ___report의 경우 Meta 광고에 구성된 인앱 이벤트 이름입니다.</p></td><td>문자열</td><td>예</td></tr><tr><td>event_uuid</td><td>앱스플라이어</td><td>파트너가 중복된 포스트백을 식별할 수 있도록 하는 고유한 임의 식별자</td><td>문자열</td><td>아니요</td></tr><tr><td>설치 날짜</td><td>iOS</td><td>앱스플라이어가 포스트백 도착 시간을 기준으로 추정한 날짜입니다.</td><td>시간 문자열</td><td>아니요</td></tr><tr><td>install_type</td><td>iOS</td><td>New 인스톨</td><td>문자열</td><td>아니요</td></tr><tr><td>ip</td><td>iOS</td><td><p>포스트백을 보내는 iOS 장치의 HTTP 메시지에 포함된 IP 주소.</p><p>광고 네트워크가 이 주소를 제공하면 이 필드가 채워집니다.</p><p>참고! SDK는 주소를 가져오는 데 관여하지 않습니다. </p></td><td>문자열</td><td>아니요</td></tr><tr><td>media_source</td><td>iOS</td><td>앱스플라이어 네트워크 이름을 사용하여 어트리뷰트된 광고 네트워크</td><td>문자열</td><td>예</td></tr><tr><td>postal_code</td><td> </td><td>2021년 8월 30일부터 항상 null입니다.  </td><td>문자열</td><td>아니요</td></tr><tr><td>지역</td><td>앱스플라이어</td><td>country_code에 따라 결정합니다.</td><td>문자열</td><td>아니요</td></tr><tr><td>skad_ad_network_id</td><td>iOS</td><td>포스트백이 전송된 애드 네트워크의 ID</td><td>문자열</td><td>아니요</td></tr><tr><td></td><td>앱스플라이어</td><td>true인 경우, 광고주가 대시보드에서 SKAN 설정을 변경한 후 첫 72시간 동안 iOS 포스트백 수신됨. SKAN에서 다양한 타이머 사용으로 인해, 앱스플라이어가 이벤트를 정확히 매핑할 수 없음.<ul><li></li></ul></td><td>Boolean</td><td>아니요</td></tr><tr><td>skad_attribution_signature</td><td>iOS</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>skad_campaign_id</td><td>iOS</td><td>광고를 게시하는 데 사용되는 캠페인 ID 범위 0-100</td><td>정수</td><td>아니요</td></tr><tr><td>skad_전환_가치</td><td>iOS</td><td><p>iOS 에서 보고된 전환 값입니다. 범위 0-63.</p><p>null인 경우 iOS는 필드\*\*를 채우지 않습니다.</p></td><td>정수</td><td>아니요</td></tr><tr><td>skad_mode</td><td>앱스플라이어</td><td>iOS 포스트백을 디코딩하는 데 사용되는 전환 측정 모드입니다. 옵션:<ul><li>커스텀 디코딩</li><li>수익</li><li>이벤트</li><li>skan4</li><li>커스텀 인코딩</li><li>인게이지먼트</li></ul></td><td>문자열</td><td>아니요</td></tr><tr><td>skad_redownload</td><td>iOS</td><td>사실이라면, 앱이 재다운로드되었습니다.</td><td>Boolean</td><td>아니요</td></tr><tr><td>skad_수익</td><td>iOS</td><td>이벤트 수익 금액 (USD)</td><td>Float</td><td>아니요</td></tr><tr><td>skad_source_app_id</td><td>iOS</td><td><p>사이트 ID - 광고를 게시하는 앱입니다.</p><p>필드 채우기는 프라이버시 임계값에 따라 달라집니다\*\*</p></td><td>문자열</td><td>아니요</td></tr><tr><td>skad_transaction_id</td><td>iOS</td><td>-</td><td>문자열</td><td>아니요</td></tr><tr><td>skad_version</td><td>iOS</td><td>-</td><td>문자열</td><td>아니요</td></tr><tr><td>타임스탬프</td><td>iOS</td><td><p>앱스플라이어가 SKAN 포스트백을 받은 시간.</p><p>Google Ads 및 Meta Ads의 경우, 이는 앱스플라이어가 각각 Google과 Meta Ads API로부터 데이터를 받는 시간입니다.</p></td><td><p>타임스탬프</p><p>(SRN 광고 기준 리포트의 시간 문자열)</p></td><td>예</td></tr><tr><td>event_value</td><td>S2S</td><td><p>기본값: null</p><p>사용자정의 디코딩을 구현하는 앱에서 설정한 문자열을 포함합니다.</p><p>광고주는 이를 자신의 시스템에서 사용합니다. 앱스플라이어는 이를 활용하지 않습니다. </p></td><td>문자열(JSON)</td><td>아니요</td></tr><tr><td>애드 네트워크 광고 세트 ID</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>예</td></tr><tr><td>애드 네트워크 광고 세트 이름</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>예</td></tr><tr><td>애드 네트워크 광고 이름</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>예</td></tr><tr><td>애드 네트워크 광고 ID</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>예</td></tr><tr><td>skad_did_win(1)</td><td>3.0(iOS 14.6)</td><td>캠페인이 인스톨에 <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">기여했거나 어트리뷰션된</a> 경우를 구별하는 데 사용됩니다. <ul><li>진실이라면, 캠페인은 인스톨을 가져온 것으로 간주됩니다.</li><li>false인 경우 캠페인이 인스톨에 기여한 것으로 인식되지만 SKAN 대시보드 또는 리포트에는 포함되지 않습니다.</li><li>null인 경우 <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">레거시 iOS 또는 SKAdNetwork 버전</a>으로 인해 iOS가 필드를 채우지 않습니다.</li></ul></td><td>Boolean</td><td>아니요</td></tr><tr><td>skad_fidelity_type(1)</td><td>2.2(iOS 14.5)</td><td><p>어트리뷰션에 영향을 주는 <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">광고 프레젠테이션</a> 옵션 차이를 식별합니다. 다음과 같이 0과 1의 값으로 표시됩니다. </p><ul><li>시청 기반 광고 (0)</li><li>StoreKit 광고 (1)</li></ul><p>SKAN 버전이 2.2 이전인 경우 필드 값을 무시하세요.</p></td><td>정수</td><td>예</td></tr><tr><td>ad_network_source_app_id(1)</td><td>애드 네트워크</td><td><span>애드 네트워크가 보고한 퍼블리셔 앱 ID입니다. 비용 조정 시 사용되며 애드 네트워크에 의해 보고됩니다. 이 데이터의 근거는 퍼블리셔 앱에서 제공합니다.</span></td><td>문자열</td><td>아니요</td></tr><tr><td>ad_network_channel(1)</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>af_prt(1)</td><td>애드 네트워크</td><td> </td><td>문자열</td><td>아니요</td></tr><tr><td>min_revenue </td><td>앱스플라이어</td><td>일러두기 (4)를 참조하십시오.</td><td>실수</td><td>아니요</td></tr><tr><td>max_revenue </td><td>앱스플라이어</td><td>일러두기 (4)를 참조하십시오.</td><td>실수</td><td>아니요</td></tr><tr><td>event_revenue</td><td>앱스플라이어</td><td>공식: [특정 이벤트의 USD 값 합계] \/ [특정 날짜에 발생한 이벤트 수]</td><td>Float</td><td>예</td></tr><tr><td>최소 이벤트 카운터</td><td>앱스플라이어</td><td>유저가 이벤트를 수행하는 횟수를 계산하는 데 사용됩니다. 일러두기 (3)을 참조하십시오.</td><td>정수</td><td>아니요</td></tr><tr><td>최대 이벤트 카운터</td><td>앱스플라이어</td><td>일러두기 (3)을 참조하십시오.</td><td>정수</td><td>아니요</td></tr><tr><td>앱 설치 후 최소 시간</td><td>앱스플라이어</td><td>일러두기 (5)를 참조하십시오.</td><td>정수</td><td>아니요</td></tr><tr><td>앱 설치 후 최대 시간</td><td>앱스플라이어</td><td>일러두기 (5)를 참조하십시오.</td><td>정수</td><td>아니요</td></tr><tr><td>af_attribution_flag</td><td>앱스플라이어</td><td>SSOT (Single Source of Truth) 메커니즘이 활성화된 경우: true인 경우, 인스톨이 앱스플라이어와 SKAN 둘 다에 의해 어트리뷰트됨. false인 경우, 인스톨이 앱스플라이어에 의해 어트리뷰트되지 않음. skad_conversion_value가 null인 경우, 플래그는 true 또는 false입니다(<a href="./skan-modeled-data#null-conversion-values" target="_blank">모델링</a> 기준).</td><td>Boolean</td><td>아니요</td></tr><tr><td>measurement_window</td><td>앱스플라이어</td><td>유저 활동 측정 기간 기본값은 24시간입니다. </td><td>정수</td><td>아니요</td></tr><tr><td>간격</td><td>앱스플라이어</td><td>유저 활동 측정 기간 간격. </td><td>정수</td><td>아니요</td></tr><tr><td>user_agent</td><td>앱스플라이어</td><td>장치 사용자 에이전트</td><td>문자열</td><td>아니요</td></tr><tr><td>skad_포스트백_서열_인덱스</td><td>4.0 (iOS 16.2)</td><td><ul><li>값은 SKAN 기간, 즉 0, 1 또는 2를 나타냅니다.</li><li>SKAN 3의 경우 값은 0 </li></ul></td><td>정수</td><td>예</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0 (iOS 16.2)</p></td><td><ul><li> </li><li>SKAN 3의 경우 값은 0</li></ul></td><td>문자열</td><td>예</td></tr><tr><td>skad_source_identifier</td><td>4.0 (iOS 16.2)</td><td><ul><li>값은 최대 4자리까지 가능합니다.</li><li>SKAN 3의 경우 값은 0 </li></ul></td><td>문자열</td><td>예</td></tr><tr><td>skad_source_domain</td><td>4.0 (iOS 16.2)</td><td><ul><li>값은 어트리뷰션이 가능한 웹 광고의 소스를 나타냅니다.</li><li>SKAN 3의 경우 값은 0</li></ul></td><td>문자열</td><td>예</td></tr><tr><td>애드 네트워크 크리에이티브</td><td>애드 네트워크</td><td><ul><li>값은 애드 네트워크에서 수신한 데이터 보강에 기반합니다.</li><li>SKAN 3의 경우 값은 0</li></ul></td><td>문자열</td><td>아니요</td></tr><tr><td colspan="4"><p>\*\* Apple은 프라이버시 임계값 메커니즘을 사용하여 필드를 채우는지 여부를 판별합니다</p><p>(1) 2021년 6월 2일부터 필드는 리포트에 추가되지만 반드시 채워지지는 않습니다.</p><p> 참고! 가장 가까운 정수로 반올림해야 합니다.<br/>예시:<br/>A. min = 0, max = 1이면 평균은 0.5; 반올림하면 1이 됩니다.<br/>B. min = 5, max = 10이면 평균은 7.5; 반올림하면 8이 됩니다.</p><p> SKAN 4 또는 커스텀 모드를 사용하는 경우, 이벤트와 관련된 버킷 범위는 min_revenue 및 max_revenue로 설명되며 skad_revenue 계산에 사용됩니다.</p><p>(5)</p><ul><li>커스텀 전환에서: 앱스플라이어는 포스트백 도착 시간 - 36시간 - 평균(min_time_post_install + max_time_post_install)으로 인스톨 시간을 계산합니다. 그러나 CV=0일 경우, 평균(min_time_post_install + max_time_post_install)은 0으로 간주됩니다. </li><li>디코드 전환에서: min_time_post_install은 max_time_post_install에 설정된 시간보다 1시간 적으며, 이는 귀사의 디코드 전환 매핑에서 설정한 hours_from_install과 동일합니다. </li></ul></td><td> </td></tr></tbody></table>

</Accordion>

<div id="additional-information" />

## 추가 정보

<div id="traits-and-limitations" />

<Accordion title="특성 및 한계">

| 특징 | 비고 |
| --- | --- |
| 광고 네트워크 액세스 | 광고 네트워크에 포스트백이 제공됩니다. |
| 에이전시 액세스 | 사용 불가 |
| 에이전시 투명성 | 해당 사항 없음 |
| 시간대 | UTC |
| 통화 | USD |
| 오가닉 데이터 | SDK 이벤트 데이터를 기반으로 합니다. 예를 들어, 오가닉 인스톨 지표는 다음과 같이 계산됩니다: SDK에 의해 보고된 모든 인스톨 데이터에서 SKAdNetworks에서 보고한 논오가닉 인스톨을 제외한 값입니다. |
| 논오가닉 데이터 | SKAN 포스트백 기반 |
| 데이터 최신성 | 일별. SKAN 타이밍이란 iOS가 기간 종료 후 24&#126;48시간이 지나 인스톨에 대해 리포트하는 것을 의미합니다. |
| 과거 데이터 | 데이터 락커 가용성 창으로 제한됩니다. |
| 계정 유저 액세스 | 사용 가능. 계정 권한에 따름 |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#reporting-options">사용 가능한 SKAN 리포트 (SKAN 솔루션 가이드)</Anchor>

<div data-zendesk-anchors="skan-raw-data-reports=skan-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8 01H8XHATZB2G6YZ9AJNPRZS59Y=skan-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8 skan-raw-data-report-format-and-content=skan-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%98%95%EC%8B%9D-%EB%B0%8F-%EC%BD%98%ED%85%90%EC%B8%A0 01H8XHATZCJQZTZF0Y5P18XMEA=skan-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%98%95%EC%8B%9D-%EB%B0%8F-%EC%BD%98%ED%85%90%EC%B8%A0 01H8XHATZCR5BC2P5TSQTMDY5Q=raw-data-report-types 01H8XHATZC0MST5ASGWDGGK2R8=raw-data-field-format-types field-formats=%ED%95%84%EB%93%9C-%ED%98%95%EC%8B%9D 01H8XHATZCZMNGK72DDE5HS6E9=%ED%95%84%EB%93%9C-%ED%98%95%EC%8B%9D 01H8XHATZC24DH4AYB2C523JDH=fields-available-in-postback-and-postback-copy-reports 01H8XHATZCNXVG0E3MZ9H68AA1=fields-available-in-decoded-event-reports additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01H8XHATZD9D7JBHTFZ095EBD5=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01H8XHATZDMV0VN4BDTECGF91K=traits-and-limitations h_01HDNYQBVZP0A6SQASGDRFVFGP=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
