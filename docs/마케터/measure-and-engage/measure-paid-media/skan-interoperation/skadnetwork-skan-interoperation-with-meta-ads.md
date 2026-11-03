---
title: Meta Ads와 SKAdNetwork(SKAN) 상호 운용
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-01-17T10:08:28Z'
  edited_at: '2026-10-14T10:32:32Z'
  id: 360017095198
  locale: ko
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/ko/articles/360017095198
---
> **요약:** 상호 운용성을 통해 Meta Ads는 디코딩된 SKAN 데이터를 앱스플라이어와 공유할 수 있으며, 앱스플라이어는 귀사의 전환 값 측정 비트(매핑)를 Meta Ads와 공유할 수 있습니다.

<Embed title="Meta Ads와 SKAdNetwork(SKAN) 상호 운용" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/15jnbml3h7" providerUrl="https://fast.wistia.com" />

## SKAN 상호 운용성: 앱스플라이어 &lt;-> Meta Ads

여러 애드 네트워크 파트너와 협력하는 경우, 앱스플라이어에서 설정하는 것이 가장 좋습니다. 이렇게 하면 비용 등의 다른 지표로 강화된 SKAN 성과 지표를 앱스플라이어 플랫폼에서 확인할 수 있습니다.

#### Meta Ads와 SKAN 상호 운용성 범위

Meta Ads와의 상호 운용을 통해 다음이 가능합니다:

* 앱스플라이어와 Meta Ads는 SKAN 전환 값(CV) 스키마를 공유하여 두 소스 모두 성과 지표를 제공할 수 있습니다.
* 앱스플라이어는 캠페인 최적화를 가능하게 하는 모든 Meta Ads 캠페인 목표를 지원합니다:
  * 모바일 앱 설치 (MAI)
  * 모바일 앱 인게이지먼트 (MAE)
  * 가치 최적화(VO)
* SKAN 연동을 활성화하면 다음이 발생합니다:
  * 페이스북 SDK가 SKAN 전환 값 업데이트를 중단합니다(*킬 스위치*).
  * 앱스플라이어 SDK가 전환 값을 업데이트합니다.
  * Meta Ads는 SKAN 대시보드 및 데이터 집약형 보고서에 포함할 SKAN 포스트백 데이터를 공유합니다.

기타 고려 사항:

* SKAN 파트너 연동을 활성화하지 않으면, SKAN 대시보드에서 Meta Ads로 유입된 인스톨은 오가닉 설치로 처리됩니다.
* 앱스플라이어 어트리뷰션의 맥락에서(개요 대시보드):
  * Meta Ads를 통해 발생한 사용자 동의 인스톨은 올바르게 어트리뷰션 됩니다.
  * 동의하지 않은 사용자는 오가닉으로 간주됩니다.
* <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#ios-145-srn-attribution">iOS 14.5가 SRN 리포팅에 미치는 영향</Anchor>
* Meta Ads와의 MMP 연동 과정에서 앱스플라이어는 *Advertiser Tracking Enabled* 플래그를 상시 구현하고 있습니다. (본 정보는 2021년 2월 기준 Meta Ads 앱 가이드 iOS 14 체크리스트에 따라 제공됩니다).

#### 고려 사항

* 측정 설정을 변경할 때마다 상호 운용성이 활성화되면, 이 문서에 나와 있는 MMP 연동 절차를 반복할 필요가 없습니다. 즉, MMP 연결 URL을 다시 복사할 필요가 없습니다.
* 앱스플라이어에서 SKAN 측정을 끄면 Meta Ads에서 CV 매핑을 받을 수 없습니다.
* 앱스플라이어 SDK vs. 페이스북 SDK: 페이스북 SDK는 Meta Ads로만 캠페인을 실행하는 경우에 적합합니다. 여러 파트너와 캠페인을 실행하는 경우 앱스플라이어 SDK를 사용하면 모든 파트너의 데이터를 볼 수 있습니다.
* 이 문서의 [불일치](/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq) 섹션을 검토하세요.

#### Meta Ads 앱 설치 광고 안내

Meta ads iOS 14 앱 설치 캠페인을 설정할 때 다음 <Anchor target="_blank" href="https://developers.facebook.com/blog/post/2020/10/29/preparing-our-partners-ios-14-latest-guidance-on-skadnetwork/">Meta ads 가이드</Anchor>를 참고하시기 바랍니다:

* 앱당 최대 18개의 캠페인을 진행할 수 있으며, 각 캠페인에는 5개의 광고 세트가 허용됩니다.
* iOS 14 캠페인에는 별도의 계정이 필요하지 않습니다. 기존 계정에서 iOS 14 캠페인을 실행할 수 있습니다.
* Meta ads 최적화 방법과 앱스플라이어에서 선택한 측정 유형 간에는 다음과 같은 관계가 있습니다.
  * **수익 측정**: VO 및 AEO
  * **전환 측정**: AEO— Meta Ads 표준 이벤트와 구매 이벤트를 포함합니다. 앱스플라이어의 앱 이벤트를 관련 Meta Ads 이벤트에 매핑해야 합니다.

## 상호운용 절차

상호운용성을 활성화하려면 다음 절차를 완료하세요.

앱 설치 어트리뷰션의 경우:

<div id="allow-facebook-to-share-skadnetwork-data-with-appsflyer" />

<Accordion title="Meta Ads가 앱스플라이어와 SKAN 데이터를 공유하도록 허용">

Meta Ads가 앱스플라이어와 SKAN 데이터를 공유하도록 허용합니다. 그렇지 않으면 앱스플라이어 SKAN 대시보드에서 Meta Ads에 기인한 SKAN 인스톨이 표시되지 않습니다.

이 절차는 앱마다 한 번씩 수행해야 합니다.

**Meta Ads에 앱스플라이어와 SKAN 데이터를 공유할 수 있는 권한을 부여하려면:**

1. 앱스플라이어에서 **협업** > **활성화된 연동**으로 이동합니다.
2. Meta Ads를 검색하여 선택합니다.
3. **SKAN** 탭으로 이동합니다.

   ![skan_repprtiing_-_connected_accounts.png](https://files.readme.io/41514c220de398871292c990e448e2bc8ce450a17512649842cdb2bc4fd78846-40032591356817.png)
4. **f 로그인**을 클릭하세요. 계정은 <Anchor target="_blank" href="https://www.facebook.com/business/help/155909647811305?id=829106167281625">다음 권한이 있는</Anchor> 관리자 또는 광고주 계정이어야 합니다.
   * Ads\_read 권한. [광고 읽기 권한이 있는지 확인](/docs/skadnetwork-skan-interoperation-with-meta-ads#verifying-the-ads_read-permission) 하세요.
   * Meta Business Partner 설정에서 광고된 앱 ID에 액세스합니다.
5. 사용자 인터페이스에서 지시를 따르세요.  
   Meta가 앱스플라이어와의 데이터 공유를 허용하는 <Anchor target="_blank" href="https://developers.facebook.com/docs/facebook-login/guides/access-tokens/get-long-lived/">액세스 토큰</Anchor>을 생성합니다. 과정을 완료한 후 앱스플라이어로 돌아갑니다.
6. 처음으로 이 연동을 설정하는 경우, 계정 상태가 **동기화 대기 중**으로 표시되는지 확인하세요.  
   이 메시지는 Meta Ads에서 데이터를 받을 때까지 유지됩니다.
7. 다음 날 02:00 UTC 이후까지 기다린 후, 상태가 **데이터를 성공적으로 가져왔습니다**로 변경되는지 확인하세요.  
   SKAN 대시보드의 데이터는 매일 08:00 UTC에 업데이트됩니다.
8. [측정 차이](/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook)에 대한 섹션을 읽어보세요.

</Accordion>

인앱 이벤트 어트리뷰션:

<div id="share-cv-schema-with-facebook" />

<Accordion title="CV 스키마를 Meta Ads와 공유">

![SKAdNetwork-Facebook-AppsFlyer_integration__5_.png](https://files.readme.io/f5965dc535a47b3d665a3cf1ae1df564a176ff9be76d5fb4a9f01d80b0e58994-40032652599953.png)

#### Meta Ads와 앱스플라이어 SKAN 연동 활성화

<Table>
  <thead>
    <tr>
      <th>
        단계
      </th>
      <th>
        작업
      </th>
      <th>
        세부 사항
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="1"></span>
        1
      </td>
      <td>
        앱 필수 조건
      </td>
      <td>
        * 앱에 최신 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">SDK</Anchor>를 도입하세요.
      </td>
    </tr>
    <tr>
      <td><span id="2"></span>
        2
      </td>
      <td>
        SKAN 설정 검토
      </td>
      <td>
        앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAN 솔루션</Anchor>이 설정되고 켜져 있는지 확인하세요. 이렇게 하면 앱스플라이어 SDK가 SKAN API를 호출하고 CV를 설정할 수 있습니다.

        **SKAN 설정 보기**:

        1. 앱스플라이어에서 **설정** > **SKAN 컨버전 스튜디오**로 이동합니다.
        2. 옵션: 아이콘을 클릭한 후, **SKAN 측정이** 켜져 있는지 확인하세요.  
           [![Measurement_mode_on_facebook_ads.png](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)
        3. 선호하는 측정 모드를 선택하세요.  
           <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">SKAN 컨버전 스튜디오</Anchor>에 대해 더 보기.
        4. 정확한 이벤트 이름을 기록해 두세요. 다음 단계에서 필요합니다. **참고:** 이름은 대소문자를 구분합니다.
      </td>
    </tr>
    <tr>
      <td><span id="in-app-event-mapping"></span>
        3
      </td>
      <td>
        인앱 이벤트 매핑
      </td>
      <td>
        귀사의 인앱 이벤트 매핑을 검토하고 필요시 변경하세요.

        **인앱 이벤트 매핑 보기 및 설정**:

        1. 앱스플라이어에서 **협업** > **활성화된 연동**으로 이동합니다.
        2. **Meta Ads**를 선택하세요.
        3. [필수] **연동** 탭에서 **인앱 이벤트 포스트백**을 켭니다.
           * 현재 선택된 SKAN 측정 유형을 매핑해야 합니다. 기본 측정 유형은 수익입니다.  
             ![in-app_events_fb_en-us.png](https://files.readme.io/98e2c8048444331c5d24343e683605e8388ee93bbfcb70aa5e8dad183c995859-40032591364241.png)
           * SKAN 측정에서 설정한 인앱 이벤트(**앱스플라이어 이벤트**)가 Meta Ads 이벤트 식별자(**파트너 이벤트에 매핑됨**)와 매핑되었는지 확인하세요. 이벤트를 매핑하지 않으면 Meta ads가 최적화를 진행할 수 없어 설치 수만 집계하게 됩니다.

             > 📘 **참고**
             >
             > SKAN 컨버전 스튜디오에서 전환 값(CV)을 추가, 변경 또는 제거할 때, 해당 이벤트가 **인앱 이벤트 포스트백**에 매핑되어 있는지 확인하세요. 그렇지 않으면 전환 값이 Meta Ads에 업데이트되지 않습니다.
             >
             > #### 인앱 이벤트 매핑 가이드


        | 측정 유형 | 매핑 요구 사항 |
        | --- | --- |
        | <span id="custom"></span><Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio#custom">사용자 지정</Anchor> | 커스텀에서 설정한 인앱 이벤트를 해당 Meta Ads 이벤트에 매핑합니다.<br /><br />포스트백으로 수익을 리포트하려면 **수익 발송**을 **값 및 수익**으로 설정해야 합니다.<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue*는 전체 수익에 사용되며 보통 *fb\_mobile\_purchase*인 Meta Ads 수익 이벤트에 매핑됩니다.<br /><br />노트! 두 개 이상의 이벤트를 *fb\_mobile\_purchase*에 매핑해도 문제없습니다. |
        | <span id="revenue"></span>수익 | 광고 네트워크에 포스트백으로 수익을 리포트하는 경우, 귀사의 인앱 이벤트 포스트백 매핑에 설정한 인앱 수익 이벤트를 포함하고 있는지 확인하세요.<br /><br />*af\_skad\_revenue*는 전체 수익에 사용되며 보통 *fb\_mobile\_purchase*인 Meta Ads 수익 이벤트에 매핑됩니다.<br /><br />노트! 두 개 이상의 이벤트를 *fb\_mobile\_purchase*에 매핑해도 문제없습니다. |
        | <span id="conversion"></span>전환 | 1&#126;6개의 전환 이벤트를 해당 Meta Ads 이벤트에 매핑합니다. |

        4. **연동 저장**을 클릭합니다.
        5. **SKAN 구성**으로 스크롤하여 **MMP 연결 URL**을 클릭하여 복사합니다. 다음 섹션에서는 Meta에 URL을 붙여넣을 위치를 알려드립니다.

           ![meta_ads_skan_configuration_mmp_url.png](https://files.readme.io/341918a757014d51a240898d157a6576b50cb269ad3bd0a574e4e6aef9d504ef-40032652607377.png)
      </td>
    </tr>
    <tr>
      <td><span id="4"></span>
        4
      </td>
      <td>
        앱스플라이어를 Meta Ads에 연결하기
      </td>
      <td>
        1. Meta Ads에서 이벤트 관리자 열고 **설정** 탭으로 이동합니다.

           [<Image alt="FacebookSkadNetworkSetup.jpg" src="https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg" width="503px" />](https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg)
        2. 설정에서 **이벤트 구성**을 클릭합니다.

           [<Image alt="mceclip0.jpg" src="https://files.readme.io/208040fdd63fcd80ddc2cac6d0f49ff6b78f5f788f85a5022f5e3c747f268ef9-40032591379217.jpg" width="503px" />](https://files.readme.io/208040fdd63fcd80ddc2cac6d0f49ff6b78f5f788f85a5022f5e3c747f268ef9-40032591379217.jpg)
        3. 이벤트 관리자에서 **파트너 앱에서 가져오기를 선택합니다.**

           [<Image alt="mceclip1.png" src="https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png" width="503px" />](https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png)
        4. **MMP 연결 URL**을 붙여넣을 필드가 표시됩니다.   
           이 업데이트는 Meta를 CV 매핑과 함께 갱신하고, 귀사의 앱에 있는 페이스북 SDK에 CV 설정 중지를 지시합니다. 파트너 앱에서 가져오기가 비활성화된 경우—[문제 해결](/docs/skadnetwork-skan-interoperation-with-meta-ads#import-from-partner-app-is-disabled).
        5. Meta ads 사용자 인터페이스의 지침을 따르세요. 다음 중 하나가 발생합니다:
           1. Meta ads 사용자 인터페이스에 **MMP 연결 URL**을 성공적으로 붙여넣었습니다. 축하합니다! 연동을 완료했습니다. 다음 참고사항을 읽어보세요.
           2. Meta ads 사용자 인터페이스에 **MMP 연결 URL**을 붙여넣는 데 실패했고 오류 메시지가 표시됩니다. 만약 그렇다면:  
              - 24시간 기다린 후, 이 절차를 반복하세요.  
              - 오류가 지속되면(24시간 이상 경과), 앱스플라이어 지원에 문의하세요.

        참고

        * 이 절차는 한 번만 수행하면 됩니다. 즉, 앱스플라이어에서 측정 설정을 변경한 후 연결 URL을 다시 복사할 필요가 없습니다. 예를 들어, 수익 측정에서 전환 측정으로 전환해도 Meta ads는 기존 URL을 사용해 현재 스키마를 가져옵니다.
        * 절차를 완료하면 Meta ads가 자체 개발한 무작위 구조를 사용해 앱스플라이어에서 CV 스키마를 가져올 수 있습니다. 이 설정을 직접 구성할 방법은 없습니다.
        * 업데이트된 측정 설정이 Meta ads에 반영되려면 최대 24시간이 걸립니다.
      </td>
    </tr>
    <tr>
      <td><span id="5"></span>
        5
      </td>
      <td>
        iOS 14 캠페인 설정
      </td>
      <td>
        Meta ads에서 iOS 14 캠페인 설정이 활성화되어 있는지 확인하세요.

        이 설정은 **New 앱 인스톨 캠페인** 설정 페이지에서 찾을 수 있습니다.

        [![FBiOS14.png](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

## 추가 정보

<div id="turning-off-the-skan-integration" />

<Accordion title="SKAN 연동 해제">

Meta Ads 연동을 해제할 때 **활성 파트너** 토글을 끄는 것만으로는 부족하며, SKAN 데이터 수집을 중단하려면 SKAN 연결을 별도로 제거해야 합니다.

**SKAN 연동을 끄려면:**

1. 앱스플라이어에서 **협업** > **활성화된** **연동**으로 이동하세요.
2. Meta Ads를 검색하여 선택합니다.
3. **SKAN** 탭으로 이동합니다.
4. 제거하려는 계정의 삭제 아이콘을 클릭하세요.

</Accordion>

<div id="measurement-and-timing-differences-between-appsflyer-and-facebook" />

<Accordion title="앱스플라이어와 Meta ads 간의 측정 및 타이밍 차이">

| 항목 | 세부 사항 |
| --- | --- |
| 인앱 이벤트 이름 | 2021년 8월 15일까지 대시보드의 이벤트 이름은 Meta ads 이벤트 이름을 사용했습니다. 앞으로는 더 이상 해당 사항이 없습니다. |
| 수익 모드 전환 유저 메트릭 | [2021년 8월 16일 삭제됨]<br /><br />~~수익 모드에서 전환된 사용자(결제 사용자) 지표는 이전 섹션(앱 내 이벤트 이름)에서 언급된 매출 명명 규칙으로 인해 Meta Ads 캠페인을 통해 매출을 발생하는 사용자 수를 반영하지 않습니다.~~ |
| 데이터 가용성 시작 시점 | 연동 후 첫 데이터 동기화 시점은 물론 이후 동기화에서도, 앱스플라이어는 최대 소급 7일까지의 Meta Ads 데이터를 수신합니다. |
| 인스톨 날짜 | 앱스플라이어와 Meta Ads는 인스톨 날짜를 판단하는 방식이 다릅니다. 다음 사항을 고려하세요:<ul><li>iOS SKAN 포스트백에는 실제 인스톨 타임스탬프가 포함되어 있지 않습니다.</li><li>Meta Ads는 포스트백 도착 시간을 인스톨 시간으로 간주하며, Meta Ads의 앱 시간대를 고려하여 날짜를 설정합니다.</li><li>앱스플라이어는 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio#activity-window">활동 기간 설정</Anchor>에 따라 설치 시간을 집계합니다. 앱 시간대나 Meta Ads 광고 계정 시간대는 계산에 고려되지 않습니다.</li></ul> |
| 데이터 최신성 | <ul><li>우리는 01:00 UTC에 Meta Ads에서 SKAN 데이터를 수집합니다.</li><li>대시보드와 집계 데이터는 7시간 후에 업데이트됩니다.</li></ul> |

</Accordion>

<div id="verifying-the-ads_read-permission" />

<Accordion title="ads_read 권한 확인">

ads\_read 권한은 Meta Ads 고객에게 커스텀 대시보드 및 데이터 분석에 사용할 수 있는 광고 성과 데이터에 대한 API 액세스를 제공합니다.

**Meta Ads 계정에 ads\_read 권한이 있는지 확인하려면:**

1. <Anchor target="_blank" href="https://developers.facebook.com/apps">Meta Ads 개발자 계정</Anchor>으로 이동합니다.
2. Facebook 앱 ID를 선택합니다.
3. **사용 사례 > 권한 및 기능**으로 이동합니다.
4. `ads_read`을(를) 검색합니다.
5. `ads_read`(이)가 사용 준비 상태인지 확인합니다. 그렇다면 추가적인 조치가 필요하지 않습니다.
6. `ads_read`(이)가 사용 준비 상태가 아니면 권한을 요청하고 요청을 제출하십시오.
7. Meta에서 요청을 승인한 후, 앱스플라이어의 Meta Ads 연동 페이지로 돌아와 **연결**을 클릭하세요.  
   **참고:** Meta는 최근에 이 섹션의 이름을 변경하고 재구성했습니다. **앱 검토**가 보이지 않으면 이는 예상된 상태입니다. 권한을 요청하는 올바른 위치는 **사용 사례 > 권한 및 기능**입니다.

</Accordion>

<div id="troubleshooting-discrepancies-and-faq" />

<Accordion title="문제 해결, 불일치 및 FAQ">

| 작업 | 세부 사항 |
| --- | --- |
| <span id="not-seeing-skan-inapp-events-from-meta"></span>Meta의 SKAN 인앱 이벤트가 보이지 않나요? | Meta SKAN 캠페인에서 설치 수는 집계되지만 앱 내 이벤트가 확인되지 않는 경우, 이 체크리스트를 통해 누락된 항목을 정확히 파악할 수 있습니다.<br /><br />참고: 설치가 집계되지 않는 경우, 먼저 설치 체크리스트를 확인해 보세요.<br /><br />**<span id="quick-fix-checklist"></span>Quick Fix 체크리스트**<br /><br />**1단계**<ol><li>앱스플라이어에서 SKAN 이벤트 매핑을 확인하세요.</li><li>**설정** > **SKAN Conversion Studio**로 이동합니다.</li><li>측정하고자 하는 앱 내 이벤트가 올바르게 매핑되어 있는지 확인하세요.</li></ol>**2단계**<ol><li>Meta Ads 연동 이벤트 매핑을 확인하세요.</li><li>앱스플라이어에서 **협업** > **활성 연동**으로 이동하여 **Meta Ads를** 선택합니다.</li></ol><ul><li>SKAN Conversion Studio의 동일한 이벤트 이름(대소문자 구분)이 Meta 전송용 In-app Event Postbacks 아래에 매핑되어 있는지 확인하세요.</li><li>매출을 측정하는 경우 af\_skad\_revenue가 포함되어 있으며 fb\_mobile\_purchase에 매핑되어 있는지 확인하세요.</li></ul>**<span id="still-not-working"></span>아직도 작동하지 않나요?**<br /><br />**>최소 설치 볼륨 점검**<ul><li>SKAN 설치 후 데이터가 표시되려면 Meta 캠페인당 일일 최소 설치 수가 확보되어야 합니다.</li><li>이 임계값 미만의 설치는 Conversion Values(CVs)가 null로 표시되어 이벤트 데이터를 해독할 수 없습니다.</li></ul>이 임계값은 Meta에서 공개하지 않지만, SKAN 대시보드에서 캠페인의 Null Conversion Value 비율을 확인할 수 있습니다. 이 수치가 100%에 가깝다면 설치 수를 늘려야 합니다. 타깃 사용자 기반의 필터를 조정하거나 캠페인 설치 수를 늘리세요. |
| <span id="facebook-cant-connect"></span>Meta Ads가 연결되지 않습니다 | **증상**<br /><br />Meta Ads에서 *연결할 수 없습니다. 라는 메시지가 표시될 경우 올바른 URL을 사용하고 있는지 확인하세요. 문제가 계속되면 귀사의 파트너 앱에 문의하여 도움을 받으세요.*<br /><br />**시정 조치**<br /><br />앱스플라이어에서 인앱 이벤트 매핑이 켜져 있고, 귀사의 앱스플라이어 이벤트가 Meta Ads 이벤트와 매핑되었는지 확인하세요. (이전 섹션에 설명된 인앱 이벤트 매핑에 설명되어 있음)<br /><br />[2021년 4월 20일 업데이트된 지침] |
| <span id="event-priority"></span>이벤트 우선순위 | Q: Meta Ads에서 이벤트 우선순위를 어떻게 설정하나요?<br /><br />A: Meta Ads에서는 우선순위를 설정할 필요가 없습니다. 이 우선순위 기능은 Facebook SDK를 사용하여 CV를 설정하는 앱과 관련이 있습니다. 귀사의 경우, 앱스플라이어 SDK가 CV를 설정합니다. Meta Ads의 우선순위 옵션은 무시하세요. 앱스플라이어는 우선순위 없이 전환 이벤트 6개를 측정합니다.<br /><br />[2021년 4월 20일 업데이트된 지침] |
| <span id="event-occurrences"></span>이벤트 발생 | Q: 앱스플라이어에 Meta Ads보다 더 많은 이벤트 발생이 표시되는 이유는 무엇입니까?<br /><br />A: Meta Ads는 0&#126;1개의 이벤트 발생만 계산합니다. 따라서 특정 범위 내에서 발생 횟수를 추가로 정의하더라도, 해당 추가 발생 건수는 앱스플라이어에서만 집계됩니다. |
| <span id="import-from-partner-app-is-disabled"></span>파트너 앱에서 가져오기가 비활성화되었습니다. | ![ImportFromPartnerApp.png](https://files.readme.io/c124696c4a8bca7c0d95d812f5390e9672adbfd6fc510a6fa573972f5441cd02-40032591386129.png)<br /><br />**증상**<br /><br />Meta Ads에서 **파트너 앱에서 가져오기**가 비활성화된 경우, 앱은 MMP SDK를 사용하여 Meta Ads에 이벤트를 발송한 적이 없습니다.<br /><br />**시정 조치**<br /><br />다음 중 하나를 수행하세요.<ul><li>MMP SDK를 사용하여 가능한 한 빨리 Meta Ads에 이벤트를 발송하세요.</li><li>Facebook SDK 또는 앱 이벤트 API를 사용하여 Meta Ads에 이벤트를 발송하고, 다른 방법으로 전환 스키마를 설정하세요.</li></ul>이 작업을 마친 후 Meta Ads에 첫 이벤트가 기록되면 앱스플라이어와의 연동을 설정하세요.<br /><br />[2021년 4월 25일 업데이트된 지침] |
| <span id="ranges-cant-overlap-and-must-be-in-consecutive-order"></span>범위는 겹칠 수 없으며 연속된 순서여야 합니다. | **증상**<br /><br />앱스플라이어 SKAN 커스텀 측정 모드를 사용합니다. 측정 스키마를 Meta Ads로 가져올 때 다음 메시지가 표시됩니다. *범위는 겹칠 수 없으며 연속된 순서여야 합니다.*<br /><br />**시정 조치**<br /><br />커스텀 전환 스키마의 수익 값은 연속된 오름차순이어야 합니다.<br /><br />[2021년 4월 26일 업데이트된 지침] |
| <span id="sending-events-to-facebook"></span>Meta Ads에 이벤트 발송하기 | **질문**: CV 측정 옵션에서 선택하지 않은 이벤트에 대한 추가 이벤트 포스트백을 Meta Ads로 발송하는 것이 합리적일까요?<br /><br />**답변**: 동의한 사용자에 대해서는 Meta Ads의 최적화 기능을 극대화하기 위해 모든 이벤트 범위를 발송하세요. |
| <span id="map-multiple-events-to-the-same-facebook-event"></span>여러 이벤트를 동일한 Meta Ads 이벤트에 매핑 | **질문**: 여러 개의 앱 내 이벤트를 하나의 Meta Ads 이벤트에 매핑할 수 있나요?<br /><br />**답변**: 여러 이벤트가 하나의 Meta Ads 표준 이벤트에 매핑되는 경우, Meta Ads는 이벤트를 구별할 수 없습니다. 따라서 Meta Ads는 자체적으로 인식하는 단일 이벤트를 기준으로 최적화를 진행하게 됩니다. |
| <span id="no-data-to-pull"></span>가져올 데이터가 없습니다 | **질문:** 연동 상태에 "가져올 데이터 없음"으로 표시되는 이유는 무엇인가요? Meta의 데이터 공유 권한을 확인하세요.<br /><br />**답변**: 아직 SKAN 데이터가 없거나, 해당 계정의 관리자 권한을 가진 사용자 계정으로 Meta Ads에 로그인해야 합니다.<br /><br />**질문:** "가져올 데이터 없음"이라는 메시지가 표시됩니다. 귀사의 Meta 데이터 공유 권한을 확인하세요. Meta Ads 세부 정보가 보이지만 조건이 문제가 없는가요?<br /><br />**답변**: 예. 이 오류 메시지가 나타나더라도 모든 것이 정상이며, 데이터를 추출할 수 있습니다. |
| <span id="facebook-data-is-not-in-the-dashboard"></span>Meta Ads 데이터가 대시보드에 없습니다. | **증상**<br /><br />SKAN 연동 탭에서 *데이터를 가져오지 못했습니다*라는 메시지가 나타납니다.<br /><br />![FacebookSKAdIntegration.png](https://files.readme.io/42538a59d27815b95b71ec136ebc45b8d918eebf6a2235c90fef59c467128fb2-40032591388177.png)<br /><br />**시정 조치**<br /><br />연동된 계정이 Facebook 관리자 계정이거나 ads\_read 권한을 가진 Meta ads 광고주 계정인지 확인하세요. |
| <span id="there-is-an-error-in-facebook-when-you-try-to-run-ios-14-campaigns"></span>iOS 14 캠페인을 실행하려고 할 때 Meta Ads에 오류가 발생합니다. | **증상**<br /><br />다음 사항은 모두 사실입니다.<ul><li>iOS 14 캠페인을 실행하려고 할 때 Meta Ads에서 오류 메시지가 표시됩니다.</li><li>최근 애플 앱 스토어에 새로운 앱이나 아동 대상 앱을 추가했습니다.</li></ul>이는 Meta Ads가 SKAN 지원이 포함된 SDK를 사용하고 있다는 사실을 인식하지 못해서 발생합니다. 즉, 앱스플라이어 SDK를 의미합니다.<br /><br />**시정 조치**<ol><li>앱스플라이어에서 **협업** > **활성화된 연동**으로 이동합니다.</li><li>**Meta Ads**를 검색하여 선택합니다.</li><li>**연동** 탭에서 **파트너 활성화**를 끕니다.</li><li>**연동 저장**을 클릭합니다.</li><li>15초간 기다리세요.</li><li>**파트너 활성화**를 켜세요.</li><li>**연동 저장**을 클릭합니다.</li><li>Meta Ads가 신호를 받을 때까지 최대 24시간 기다리세요.</li></ol> |
| <span id="revenue-reported-by-facebook"></span>Meta Ads에서 보고된 수익 | [2021년 7월 12일 업데이트]<br /><br />Meta Ads는 귀사의 SKAN 설정을 사용하여 CV에서 수익을 창출합니다. 하지만 이는 직접적인 계산이 아니며, Meta Ads는 알고리즘을 사용하여 수익을 결정합니다.<br /><br />이로 인한 증상은 수익을 완전한 달러로 측정하더라도 수익 값이 반올림되지 않는 것입니다. |
| <span id="retroactive-data-backfill"></span>소급적 데이터 보충 | [2021년 12월 23일 업데이트]<br /><br />예를 들어, 로그인 실패로 인해 Meta Ads에 연결하여 데이터를 가져올 수 없는 경우가 있습니다. 걱정하실 필요 없습니다. 다음에 로그인 가능해지면 지난 7일간의 리포팅을 보완할 것입니다. |
| <span id="appsflyer-is-showing-significantly-more-installseventsrevenue-than-facebook"></span>앱스플라이어가 Meta Ads보다 훨씬 더 많은 인스톨/이벤트/수익을 보여줍니다. | 많은 경우, 이러한 데이터 격차는 Meta Ads 대시보드가 기본적으로 클릭-쓰루 인스톨이나 이벤트만 표시하는 반면, 앱스플라이어 대시보드는 클릭-쓰루와 뷰-쓰루(view-through) 인스톨 및 이벤트를 모두 표시하기 때문에 발생합니다. |
| <span id="agency-integration"></span>에이전시 연동 | 대행사가 광고주의 Meta Ads 계정에서 관리자 권한을 가지고 있다면, 광고주를 대신해 이 문서의 절차에 따라 SKAN 연동을 활성화할 수 있습니다. 광고주는 Meta Ads 계정에 로그인할 필요가 없습니다. 에이전시 로그인이 광고주의 계정에 표시됩니다. |
| <span id="an-updated-cv-doesnt-appear-on-facebook"></span>업데이트된 이력서가 Meta Ads에 표시되지 않습니다. | SKAN 컨버전 스튜디오에서 전환 값(CV)을 추가, 변경 또는 제거할 때, 해당 이벤트가 **인앱 이벤트 포스트백**에 매핑되어 있는지 확인하세요. 그렇지 않으면 전환 값이 Meta Ads에 업데이트되지 않습니다. |
| <span id="modeled-data-differences-in-appsflyer-and-facebook-ads-manager"></span>앱스플라이어와 Meta Ads Manager의 모델링된 데이터 차이 | 앱스플라이어는 기본 SKAN 리포팅에서 제공할 수 없는 집계 데이터를 모델링합니다. <Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data">더 알아보기</Anchor><br /><br />앱스플라이어가 데이터를 모델링할 때, Meta Ads에서 모델링된 데이터는 고려되지 않습니다. 앱스플라이어는 확인되고 공정한 데이터에만 의존하기 때문입니다. 따라서 Meta ads Manager 보고서와 앱스플라이어 보고서 사이에 데이터 및 세부성 차이가 있을 수 있습니다. |

</Accordion>

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">앱스플라이어 SKANetwork 솔루션 가이드</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-facebook=skan-%EC%83%81%ED%98%B8-%EC%9A%B4%EC%9A%A9%EC%84%B1-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4---meta-ads h_01H8XRMVR4JK6ZCGPQJE4D3T26=skan-%EC%83%81%ED%98%B8-%EC%9A%B4%EC%9A%A9%EC%84%B1-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4---meta-ads scope-of-skan-interoperability-with-meta-ads=meta-ads%EC%99%80-skan-%EC%83%81%ED%98%B8-%EC%9A%B4%EC%9A%A9%EC%84%B1-%EB%B2%94%EC%9C%84 h_01H8XRMVR4Q7HAJV0B7QB5MDPH=meta-ads%EC%99%80-skan-%EC%83%81%ED%98%B8-%EC%9A%B4%EC%9A%A9%EC%84%B1-%EB%B2%94%EC%9C%84 considerations=%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD h_01H8XRMVR43KEGWARYMD45S0VY=%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD facebook-app-install-ads-guidance=meta-ads-%EC%95%B1-%EC%84%A4%EC%B9%98-%EA%B4%91%EA%B3%A0-%EC%95%88%EB%82%B4 h_01H8XRMVR48NWM47043YWT63HK=meta-ads-%EC%95%B1-%EC%84%A4%EC%B9%98-%EA%B4%91%EA%B3%A0-%EC%95%88%EB%82%B4 interoperation-procedures=%EC%83%81%ED%98%B8%EC%9A%B4%EC%9A%A9-%EC%A0%88%EC%B0%A8 h_01H8XRMVR4NVDZ23572F6KJTA9=%EC%83%81%ED%98%B8%EC%9A%B4%EC%9A%A9-%EC%A0%88%EC%B0%A8 h_01H8XRMVR4D07SWXS1TWK42DS3=allow-facebook-to-share-skadnetwork-data-with-appsflyer h_01H8XRMVR5HKXWYB3XN11V48Y0=share-cv-schema-with-facebook enabling-appsflyer-skadnetwork-interoperation-with-facebook=meta-ads%EC%99%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-skan-%EC%97%B0%EB%8F%99-%ED%99%9C%EC%84%B1%ED%99%94 h_01H8XRMVR56T3X9MJ6KVJF0Z8W=meta-ads%EC%99%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-skan-%EC%97%B0%EB%8F%99-%ED%99%9C%EC%84%B1%ED%99%94 h_01H8XRMVR5GY77K7GJ4TXGWEHS=%EC%B0%B8%EA%B3%A0 inapp-event-mapping-guide=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91-%EA%B0%80%EC%9D%B4%EB%93%9C h_01H8XRMVR5T28Q0E8KP6BZ6CGH=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91-%EA%B0%80%EC%9D%B4%EB%93%9C additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01H8XRMVR5WXZ88676PAW9BKC9=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01H8XRMVR5AW2HZD6JFDYJRNFJ=turning-off-the-skan-integration h_01H8XRMVR5HZ2BBP4XXDEFYT34=measurement-and-timing-differences-between-appsflyer-and-facebook h_01H8XRMVR58DFA2SX20ZEKZRC3=verifying-the-ads_read-permission h_01H8XRMVR5Z9H83X0TAYS50CJ9=troubleshooting-discrepancies-and-faq h_01K7P24YAYSPB84PV0ZGBJ0QB0=quick-fix-checklist h_01K7P2811MRTVRC0D6YGVSXY4C=still-not-working h_01HE7SMBXBCEQM7KF2RG3V16KV=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
