---
title: Snapchat과 SKAN 상호 운용
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-02-10T20:20:51Z'
  edited_at: '2026-10-14T10:37:30Z'
  id: 360017604077
  locale: ko
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/ko/articles/360017604077
---
> **한눈에 보기:** Snapchat과 앱스플라이어는 SKAN 데이터가 상호 호환되어 Snapchat은 SKAN 포스트백을 앱스플라이어와 공유할 수 있고, 앱스플라이어는 앱 기업의 전환 값 매핑 정보를 틱톡과 공유할 수 있습니다.

<div id="skan-interoperability-appsflyer---snapchat" />

## SKAN 상호 운용성: 앱스플라이어 &lt;-> Snapchat

다양한 애드 네트워크 파트너와 작업하는 경우 앱스플라이어에서 SKAN 연동을 구성하는 것이 효율적입니다. 이렇게 하면 비용 등의 다른 지표와 함께 향상된 SKAN 성능 지표를 앱스플라이어 플랫폼에서 확인할 수 있습니다.

**Snapchat과의 SKAN 상호 운용성 범위**

이러한 상호 운용을 통해 앱스플라이어와 Snapchat은 SKAN 전환 값 맵을 공유할 수 있으며, 이를 통해 둘 다 성과 지표를 제공할 수 있습니다. 앱스플라이어에서 Snapchat 파트너 연동을 활성화하면 앱스플라이어가 최적화 목적으로 Snapchat에 이벤트를 제공합니다.

**Snapchat 앱 설치 광고 안내**

Snapchat iOS 14 앱 설치 캠페인을 구성할 때 다음 Snapchat 지침을 고려하세요.

*2021년 2월 18일부터 모든 광고주의 Snapchat 광고 관리자에서 SKAdNetwork를 사용할 수 있습니다. Snapchat에서 앱 유입 iOS 14 캠페인의 측정 또는 확장에 지장이 없도록 앱을 구성하고 테스트를 시작하는 것이 좋습니다. 앞으로 SKAdNetwork는 Snapchat에서 iOS 캠페인용 앱 목표 기반 입찰에 액세스하기 위한 필수 요구 사항이 될 것입니다.*

*Snapchat 광고 관리자 내에서 SKAdNetwork 광고 세트를 시작하기 전에 앱스플라이어 MMP 대시보드에서 SKAdNetwork 연동을 완료하고 전환 값 매핑 구성을 완료하시기 바랍니다. Snapchat의 SKAdNetwork 설정 가이드는 [여기](https://businesshelp.snapchat.com/s/article/skadnetwork)에서 확인할 수 있습니다.*

**구현 요구 사항**

Snapchat에서 다음 사항을 고려하세요.

* Snapchat에서 광고하는 각 앱에 대한 [Snap 앱 ID](https://businesshelp.snapchat.com/en-US/a/snap-app-id)를 구성합니다.
* SKAN 측정을 위한 Snapchat 광고 세트를 선택합니다.
* 특정 앱의 경우, 한 번에 최대 10개의 광고 세트만 SKAN 어트리뷰션에 옵트인할 수 있습니다.

<div id="enabling-appsflyer-skan-interoperation-with-snapchat" />

### Snapchat과 앱스플라이어 SKAN 상호 운용 활성화

상호운영성은 앱스플라이어와 Snapchat 대시보드 내의 설정을 통해 이뤄집니다. 앱 자체에서 상호 운용이 필요하지 않습니다. 그러나 최신 앱스플라이어 SDK를 채택해야 합니다.

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
      <td>
        1
      </td>
      <td>
        앱 필수 조건
      </td>
      <td>
        * 귀사의 앱에 최신 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">SDK</Anchor>를 도입하세요.
      </td>
    </tr>
    <tr>
      <td>
        2
      </td>
      <td>
        SKAN 설정 점검
      </td>
      <td>
        앱스플라이어의 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAN 솔루션</Anchor>을 설정하고 킨 다음 확인하세요.

        **SKAN 설정은 여기에서 확인하세요**:

        1. 앱스플라이어에서 **설정** > **SKAN Conversion Studio**로 이동합니다.
        2. 옵션(⋮)을 클릭하고 **SKAN 측정**이 설정되어 있는지 확인합니다.  

           ![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)
        3. 선호하는 측정 모드를 선택해 주세요.  
           <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">SKAN 컨버전 스튜디오</Anchor>에 대해 더 보기.
        4. 정확한 이벤트 이름을 기록해 두세요. 다음 단계에서 필요하게 됩니다.
      </td>
    </tr>
    <tr>
      <td>
        3
      </td>
      <td>
        인앱 이벤트 맵핑하기
      </td>
      <td>
        Snapchat 인앱 이벤트 매핑을 검토하고 필요한 경우 변경합니다.

        **인앱 이벤트 맵핑 설정 및 보기**:

        1. 앱스플라이어에서 **설정** > **활성 연동**으로 이동합니다.
        2. **Snapchat**을 검색하여 선택합니다.
        3. **연동** 탭에서 **파트너 활성화**가 켜져 있지 않으면 켜세요.
        4. 앱스플라이어에 표시되는 Snap 앱 ID를 확인하고 필요한 경우 <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/snap-app-id?language=en_US">Snapchat 대시보드</Anchor>에 표시되는 앱 ID로 업데이트합니다.
        5. 설정되어 있지 않으면 **인앱이벤트 포스트백**을 설정합니다.  

           [<Image alt="mceclip0.png" src="https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png" width="432px" />](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)

           SKAN 측정에서 설정한 인앱이벤트, **SDK 이벤트 이름**이 Snapchat 이벤트 이름을 의미하는 **파트너 이벤트 식별자**에 매핑되는지 확인하십시오. 현재 선택한 SKAN 측정 유형 이벤트 또는 <Anchor target="_blank" href="/marketers/ko/docs/skan-cv-decode-map-your-cv-to-events">사용자 지정 전환 맵</Anchor>의 이벤트를 매핑해야 합니다. **참고**! 기본 측정 유형은 수익입니다.

           <div id="inapp-event-mapping-guide" />

           <div id="in-app-event-mapping-guide" />

           #### 인앱 이벤트 매핑 가이드

        | 측정 타입 | 매핑 요구 사항 |
        | --- | --- |
        | 커스텀 파라미터 | 사용자 지정에서 설정한 인앱 이벤트를 해당 Snap 이벤트에 매핑합니다.<br /><br />수익을 포스트백으로 보고하려면 **수익**을 **값 및 수익으로 보내기**를 설정해야 합니다.<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue*는 전체 수익에 사용되고 Snap 수익 이벤트에 매핑됩니다.<br /><br />**참고**! 두 개 이상의 이벤트를 Snap 수익 이벤트에 매핑해도 됩니다. |
        | 수익 | af\_skad\_revenue를 PURCHASE에 매핑 |
        | 전환 | 1&#126;6개의 전환 이벤트를 해당 Snapchat 이벤트에 매핑합니다. |
        | 인게이지먼트 | 설정한 인게이지먼트 이벤트를 해당 Snapchat 이벤트에 매핑합니다. |

        6. **연동 저장**을 클릭하세요.
      </td>
    </tr>
    <tr>
      <td>
        4
      </td>
      <td>
        Snapchat이 앱스플라이어와 포스트백을 공유하도록 허용
      </td>
      <td>
        1. Snapchat 대시보드로 이동합니다.
        2. **이 MMP와 포스트백을 공유하세요**에서 앱스플라이어를 선택합니다.

           [<Image alt="SnapchatSelectAppsFlyer.png" src="https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png" width="268px" />](https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png)
        3. **업데이트**를 클릭합니다.
      </td>
    </tr>
  </tbody>
</Table>

<div id="additional-information" />

## 추가 정보

<div id="discrepancies-guide" />

<Accordion title="불일치 가이드">

| 차이 | 상세정보 |
| --- | --- |
| 대시보드 필터 | **불일치 원인**<ul><li>앱스플라이어: SKAN 대시보드에는 수신된 iOS 포스트백과 관련된 설치가 포함되어 있습니다.</li><li>Snapchat: 기본적으로, Snapchat 대시보드와 리포트에는 SKAN과 전통적으로 어트리뷰션된 설치(IDFA)가 모두 포함됩니다. Snapchat 리포트를 필터링하여 SKAN 설치만 가져옵니다.</li></ul>**해결 방안**<br /><br />Snapchat 대시보드 필터를 정렬하여 다음 스크린샷에 표시된 대로 SKAN 설치만 표시합니다.<br /><br />[![SnapchatFilter.png](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png)](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png) |
| 설치 날짜 차이 | **불일치 원인**<br /><br />앱스플라이어 및 Snapchat 설치 날짜는 다음과 같이 차이가 있을 수 있습니다.<ul><li>앱스플라이어: 다음 수식을 사용하여 설치 날짜를 도출합니다. 포스트백 도착 시간 - 24시간 - 측정 기간(기본값 24시간) 따라서 기본 조정은 48시간입니다. 모든 시간은 UTC입니다. <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#skan">SKAN 데이터 최신성</Anchor></li><li>Snapchat: 일반적으로 iOS 포스트백 도착 시간을 조정 없이 설치 날짜로 사용합니다.</li></ul>**해결 방안**<br /><br />결과를 비교할 때 위의 사항을 고려하세요. |

</Accordion>

<div id="see-also" />

> 📄 **참조 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">앱스플라이어 SKAN 솔루션 안내서</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-snapchat=skan-%EC%83%81%ED%98%B8-%EC%9A%B4%EC%9A%A9%EC%84%B1-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4---snapchat h_01HDNZ3SP97C331D45AP1F8CM7=skan-%EC%83%81%ED%98%B8-%EC%9A%B4%EC%9A%A9%EC%84%B1-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4---snapchat enabling-appsflyer-skan-interoperation-with-snapchat=snapchat%EA%B3%BC-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-skan-%EC%83%81%ED%98%B8-%EC%9A%B4%EC%9A%A9-%ED%99%9C%EC%84%B1%ED%99%94 h_01HDNZ3SP9FZ3AXCNG185DJQY1=snapchat%EA%B3%BC-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-skan-%EC%83%81%ED%98%B8-%EC%9A%B4%EC%9A%A9-%ED%99%9C%EC%84%B1%ED%99%94 inapp-event-mapping-guide=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91-%EA%B0%80%EC%9D%B4%EB%93%9C h_01HDNZ3SPA742313RAJPYSEHWV=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91-%EA%B0%80%EC%9D%B4%EB%93%9C additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HDNZ3SPASN8P9G5YYQGRFC8F=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HDNZ3SPA99XHVBPXVWB5MN86=discrepancies-guide h_01HDNZ1BW5EBP0JCX84MTYPQ6K=%EC%B0%B8%EC%A1%B0-%ED%95%AD%EB%AA%A9" />
