---
title: '게시판: Google Marketing Platform(GMP) 연동 전환'
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-12-18T11:43:04Z'
  edited_at: '2026-10-14T10:35:39Z'
  id: 21035061438737
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/21035061438737
---

<Table>
  <tbody>
    <tr>
      <td>
        **새로운 기능은 무엇인가요?**
      </td>
      <td>
        <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">디지털 마케팅법</Anchor> (DMA) 시행 준비의 일환으로 구글은 <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">EU 사용자 동의 정책</Anchor>을 업데이트하고 있습니다. 앱스플라이어는 구글의 정책 요구사항을 지원하기 위해 필요한 변경을 진행하고 있습니다.

        현재 사용할 수 있는 Google Marketing Platform(GMP) 연동은 다음과 같습니다.

        * [레거시] CM360 (DoubleClick) `doubleclick_int`
        * <Anchor target="_blank" href="/marketers/ko/docs/google-marketing-platform-display-video-360-dv360-integration">DV360(신규 연동)</Anchor> `dv360_int`

        2024년 7월 현재, 레거시 doubleclick\_int 통합은 곧 사용 중단 모드에 있으며 곧 사용 중단될 예정입니다(최종 날짜는 발표될 것입니다). 이 연동을 사용하는 경우, 캠페인을 계속 실행하고 GMP를 사용하여 측정하려면 새로운 DV360 연동으로 전환해야 합니다.
      </td>
    </tr>
    <tr>
      <td>
        **필요한 조치**
      </td>
      <td>
        가능한 한 빨리 새로운 DV360 `dv360_int` 연동으로 전환하십시오.
      </td>
    </tr>
    <tr>
      <td>
        **수행해야 할 단계**
      </td>
      <td>
        GMP와 앱스플라이어 두 플랫폼을 모두 구성해야 합니다.

        **GMP에서 구성**

        1. CM360 또는 DV360 계정에 로그인합니다.   
           **참고:** CM360에서 단계를 완료하면 DV360에서 단계를 완료할 필요가 없습니다.
        2. <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/10956727">이 안내</Anchor>에 따라 파트너 어트리뷰션 링크(링크 ID)를 생성하거나 재사용하세요.

        **앱스플라이어에서 설정**

        1. <Anchor target="_blank" href="/marketers/ko/docs/google-marketing-platform-display-video-360-dv360-integration#integration-procedures">이 지침</Anchor>에 따라 앱스플라이어에서 DV360 연동을 완료하십시오.   
           **참고:** 데이터 일관성을 유지하려면 구성이 기존 연동(전환 확인 기간, 인앱이벤트 포스트백 등)과 유사한지 확인하십시오.
        2. **새 연동을 설정합니다.**  
           새 통합 데이터를 확인하려면 하루 정도 기다리세요. 그런 다음 레거시 통합을 비활성화할 수 있습니다.
      </td>
    </tr>
    <tr>
      <td>
        **알아두어야 할 사항**
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <table><thead><tr><th><strong>고려 사항</strong></th><th>사용 가능한 옵션</th></tr></thead><tbody><tr><td colspan="2"><span id="media-source-pid"></span><p><strong>미디어소스 PID</strong></p></td></tr><tr><td><span id="after-completing-the-migration-the-dv360-media-source-pid-changes-from-doubleclick_int-to-dv360_int"></span><p>마이그레이션이 완료되면 DV360 미디어소스 PID가 <kbd>doubleclick_int</kbd>에서 <kbd>dv360_int</kbd>로 변경됩니다.</p></td><td>앱스플라이어에서 BI 또는 제3자 분석 도구로 로데이터를 가져오는 경우 미디어소스 이름의 변경을 고려하십시오.</td></tr><tr><td colspan="2"><span id="outofstore-apps"></span><p><strong>스토어 외 앱</strong></p></td></tr><tr><td><span id="apps-from-unofficial-app-stores-arent-supported-in-the-dv360-integration-the-integration-relies-on-a-link-id-which-is-generated-for-apps-obtained-through-official-app-stores"></span><p>비공식 앱 스토어의 앱은 DV360 통합에서 지원되지 않습니다. 통합은 공식 앱 스토어를 통해 얻은 앱에 대해 생성된 링크 ID에 의존합니다.</p></td><td>공식 앱 스토어 외부의 소스에서 앱을 다운로드한 경우, CSM 또는 hello@appsflyer.com에 문의하십시오.</td></tr><tr><td colspan="2"><span id="attribution-data-duplication"></span><p>귀속 데이터 분배</p></td></tr><tr><td colspan="2"><span id="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span>두 통합이 모두 활성화되어 설치에 대한 귀속을 주장할 때, 귀속은 무작위로 분할되며, 하나는 주요 출처가 되고 다른 하나는 기여자로 작용합니다. 이것은 데이터가 중복되지 않도록 보장합니다. 예를 들어, DV360이 100개의 설치를 책임지는 경우, 레거시 통합에서 70개의 설치가 발생하고 DV360에서 30개의 설치가 발생하거나, DV360에서 80개의 설치가 발생하고 레거시 통합에서 20개의 설치가 발생할 수 있습니다.</td></tr><tr><td colspan="2"><span id="inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span><span>레거시 연동으로 인해 발생한 인스톨/리인게이지먼트에 대한 인앱 이벤트는 그에 따라 크레딧이 유지됩니다.</span></td></tr><tr><td colspan="2"><span id="reengagement-reengagement-attribution-is-supported-in-the-dv360-integration"></span><p><strong>리인게이지먼트</strong></p><p>DV360 통합에서 재참여 귀속이 지원됩니다.</p></td></tr></tbody></table>

        필드 불일치

        레거시 API와 업데이트된 API의 사용 가능한 데이터 필드 간의 차이로 인해, 아래에서 볼 수 있는 것처럼 일부 AppsFlyer 필드에서 차이가 있을 수 있습니다.

        | 앱스플라이어 필드 | 레거시 필드 (doubleclick\_int) | DV360 field (dv360\_int) |
        | --- | --- | --- |
        | 캠페인 이름 | placement\_id | line\_item\_name |
        | 캠페인 ID | placement\_id | line\_item\_id |
        | 광고 세트 이름 | ad\_id | 지원되지 않습니다. |
        | 광고세트 ID | ad\_id | 지원되지 않습니다. |
        | 광고 이름 | creative\_id | 지원되지 않습니다. |
        | 광고 ID | creative\_id | creative\_id |
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected%0Ainapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly=while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly reengagement%0Areengagement-attribution-is-supported-in-the-dv360-integration=reengagement-reengagement-attribution-is-supported-in-the-dv360-integration" />
