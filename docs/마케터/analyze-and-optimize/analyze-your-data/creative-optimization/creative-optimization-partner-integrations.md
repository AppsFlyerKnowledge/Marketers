---
title: 광고 크리에이티브 최적화 파트너 연동
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-09-14T13:52:36Z'
  edited_at: '2026-10-14T10:31:17Z'
  id: 18565403047569
  locale: ko
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/ko/articles/18565403047569
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 파트너 연동을 설정하여 모든 광고 크리에이티브 데이터를 광고 크리에이티브 최적화로 자동으로 가져옵니다.

![Creative integrations New.jpg](https://files.readme.io/2bfead93dbaac902956ea4379e3f360120d59e7454be354c567b2f182382ab2d-20130430776337.jpg)

## 파트너 연동에 대하여

파트너 연동은 파트너를 통해 운영되고 있는 캠페인의 크리에이티브를 <Anchor target="_blank" href="/marketers/ko/docs/creative-optimization-guide">크리에이티브 최적화</Anchor>로 지속적으로 원활하게 가져오도록 합니다.

### 데이터 가용성

파트너 연동이 추가되면:

* 시스템은 지난 90일 동안의 광고 크리에이티브 데이터 및 앱스플라이어 성과 데이터를 백필합니다. 해당 데이터는 일반적으로 24시간 이내에 광고 크리에이티브 최적화에서 사용할 수 있습니다.
* 광고 크리에이티브 데이터는 매일 하루에 두 번씩 연동 파트너로부터 수집됩니다. 데이터는 통합되어, 앱스플라이어에서 제공하는 다른 성과 데이터 포인트(예: 어트리뷰션, 지출, 클릭, 노출, 수익 등)와 매칭됩니다. (앱스플라이어 성과 데이터는 매 시간 마다 업데이트 됩니다.) **크리에이티브 최적화 대시보드에는 위의 모든 프로세스를 통해 결합된 데이터가 표시되며 하루 한 번  UTC + 10에 업데이트됩니다.** (지난 90일 동안의 모든 광고 크리에이티브 데이터가 업데이트됨).

> 📘 **참고**
>
> <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview">참고:</Anchor> 앱스플라이어 비용 데이터(예: ROAS)를 보려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview">ROI360 구독</Anchor> 이 필요합니다.

## 미디어 파트너 연동

이 섹션에서는 각 파트너와의 연동을 설정하는 방법을 설명합니다.

<div id="adikteev" />

<Accordion title="Adikteev">

**선행 조건:**

* 연동을 위한 자격 증명:
  * 이메일(Adikteev 사용자 이름)
  * Adikteev 암호
  * **참고:** Adikteev 대시보드에 액세스하는 데 사용되는 것과 동일한 자격 증명을 사용합니다.
* Adikteev에서 모든 비용 데이터를 가져오려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview">ROI360</Anchor> 을 연동한 동일한 사용자가 크리에이티브 최적화도 연동해야 합니다.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있는 경우, 대시보드의 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Adikteev**를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. 이메일과 비밀번호를 입력합니다.
6. **저장**을 클릭합니다.

**참고:** Adikteev는 Trademob(trademob\_int)으로도 불립니다.

</Accordion>

<div id="adjoe" />

<Accordion title="Adjoe">

**전제 조건:**

* 연동을 위한 자격 증명:
  * 토큰  
    Adjoe 계정 관리자에게 연락하여 토큰을 받으세요. 자세한 내용은 <Anchor target="_blank" href="https://drive.google.com/file/d/16zMpKbRLmTLU-plnodELGAHZVe0CuC_F/view">Adjoe 문서</Anchor>를 확인하세요.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Adjoe GmbH**를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. 토큰을 입력합니다.
6. **저장**을 클릭합니다.

</Accordion>

<div id="applovin" />

<Accordion title="AppLovin">

**선행 조건:**

* 연동하려는 앱에 대한 광고 계정 권한이 필요합니다. **참고**: AppLovin에 대한 인증은 광고 계정 관리자가 수행해야 합니다.
* AppLovin **계정 ID**, **캠페인 관리 API 키**, 및 **보고 API 키**가 필요합니다. 이 정보는 AppLovin Axon 대시보드에서 얻을 수 있습니다 (오른쪽 상단에서 계정을 클릭하고 키를 선택하세요).

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.

   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.

   ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. + **새 연동**을 클릭합니다.
3. **파트너** 목록에서 **AppLovin**을 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. **앱러빈 계정 ID, 캠페인 관리 API 키, 리포팅 API** **키를 입력합니다.**
6. 그런 다음 **저장**을 클릭하세요.

> 📘 **참고**
>
> AppLovin의 자산 수준 리포팅 API는 전날의 데이터만 반환합니다. 역사적 룩백을 지원하지 않습니다. 따라서 연동을 활성화하면 앱스플라이어는 활성화일 이후에만 자산 수준 데이터 수집을 시작할 수 있습니다. 결과적으로 전체 데이터 적용 범위가 점차 확대되며 일반적으로 활성화 후 30일 이내에 완료됩니다.

</Accordion>

<div id="google-ads" />

<Accordion title="Google Ads">

**선행 조건:**

* 연동하려는 앱에 대한 광고 계정 관리자 권한이 필요합니다.
* Adikteev에서 모든 비용 데이터를 가져올 수 있으려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview">ROI360</Anchor> 을 연동한 동일한 사용자가 크리에이브 최적화를 연동해야 합니다. ROI360 구독이 없는 경우 Google AdWords의 모든 관련 앱 및 광고 계정에 대한 관리자 권한이 있어야 합니다.

**참고:**

* Google Ads와의 연동은 유저 단위로 이루어지므로 여러 사용자가 동시에 활성 연동을 수행할 수 있습니다.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. + **새 연동**을 클릭합니다.
3. **파트너** 목록을 클릭하고 **Google Ads(AdWords)** 를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. **Google에 로그인**을 클릭합니다. **Google 로그인 창**이 열립니다.
6. Google 로그인을 완료하고 권한을 제공합니다. 앱스플라이어가 전체 데이터를 가져오려면 전체 권한을 허용하는 것을 권장합니다.
7. **저장**을 클릭합니다.

**참고:** UAC 캠페인(ACi, ACe, ACpre) 광고 유형만 지원됩니다. 지원되지 않는 광고 유형의 데이터는 광고 크리에이티브 수준이 아닌 광고 수준에서만 크리에이티브 최적화에 제공됩니다.

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

**선행 조건:**

* 연동을 위한 ironSource 자격 증명:
  * Secret Key
  * 새로 고침 토큰
  * 자격 증명을 찾을 수 있는 위치를 <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/ios/authentication/#step-1">확인하세요</Anchor>.
* ironSource의 관리자 또는 기여 사용자 역할이 필요합니다. <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/air/user-management/#step-1">사용자 역할을 설정하는 방법을 알아보세요</Anchor>.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **ironSource**를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. 비밀 키와 새로 고침 토큰을 입력합니다.
6. **저장**을 클릭합니다.

**참고:** 특정 광고 유형은 지원되지 않으며, 이는 광고 크리에이티브 최적화의 데이터를 광고 크리에이티브 수준이 아닌 광고 수준에서만 사용할 수 있음을 의미합니다. 지원되지 않는 광고 유형에는 오퍼월 광고가 포함됩니다.

</Accordion>

<div id="liftoff" />

<Accordion title="Liftoff">

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Liftoff**를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. Liftoff CSM에 문의하여 Liftoff 보고 API 사용자 이름과 암호를 받으십시오.
6. **저장**을 클릭합니다.

</Accordion>

<div id="facebook-ads" />

<Accordion title="Meta ads">

**선행 조건:**

* 연동하려는 앱에 대한 광고 계정 권한이 필요합니다. **참고**: Meta 광고와의 연동은 사용자별로 이루어지므로 여러 사용자가 동시에 활성 연동을 수행할 수 있습니다.
* Facebook 페이지 내부 및/또는 외부에 표시되는 광고 크리에이티브를 가져오려면, Facebook 비즈니스 센터 관리자가 광고 크리에이티브와의 연동을 설정하는 사용자에게 관련 권한을 제공해야 합니다.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 리스트에서 **Meta ads**를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. **Meta ads 로그인**을 클릭합니다.
6. 로그인을 완료하고 권한을 제공합니다.  **참고**: 앱스플라이어가 전체 데이터를 가져오려면 전체 권한을 허용하는 것을 권장합니다.
7. **저장**을 클릭합니다.

**참고:**

* Meta Flexible Ads는 보고를 위해 하나의 자산만 제공하므로, 가장 성과가 좋은 자산(광고)의 성과 데이터만 표시됩니다.
* 특정 광고 유형은 지원되지 않으며, 이는 광고 크리에이티브 최적화의 데이터를 광고 크리에이티브 수준이 아닌 광고 수준에서만 사용할 수 있음을 의미합니다. 지원되지 않는 광고 유형은 다음과 같습니다. 카탈로그/DPA

</Accordion>

<div id="mintegral" />

<Accordion title="Mintegral">

**선행 조건:**

* 통합을 위한 Mintegral 자격 증명:
  * API key
  * 액세스 키
  * 자격 증명을 찾을 수 있는 위치를 <Anchor target="_blank" href="https://adv-new.mintegral.com/doc/en/guide/introduction/register.html">확인하세요</Anchor>.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Mintegral**을 선택하세요.
4. 홍보 중인 앱을 선택합니다.
5. **API 키와** **시크릿 키를 입력합니다.**
6. **저장**을 클릭합니다.

</Accordion>

<div id="moloco" />

<Accordion title="Moloco">

**선행 조건:**

* 광고 소재를 가져오려면 Moloco의 ' <Anchor target="_blank" href="https://help.moloco.com/hc/en-us/articles/360050566173-Invite-and-manage-users">Workplace 소유자' 또는 '광고 계정 소유자'</Anchor> 역할이 필요합니다.
* Moloco API 키에 대한 액세스.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있는 경우, ⋮ 아이콘을 클릭하여 **크리에이티브 연동**으로 이동합니다. ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Moloco**를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. Moloco API 키를 입력하세요.
6. **저장**을 클릭합니다.

**참고**:

* 특정 광고 유형은 지원되지 않으며, 이는 광고 크리에이티브 최적화의 데이터를 광고 크리에이티브 수준이 아닌 광고 수준에서만 사용할 수 있음을 의미합니다. 지원되지 않는 광고 유형에는 CTV 광고가 포함됩니다.

</Accordion>

<div id="personaly" />

<Accordion title="페르소나.ly">

**선행 조건:**

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Persona.ly를** 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. Persona.ly **API 키를** 입력합니다 (Persona.ly 계정에서 가져옴).
6. **저장**을 클릭합니다.

</Accordion>

<div id="reddit" />

<Accordion title="Reddit">

**선행 조건:**

* 광고 크리에이티브를 가져오려면 Reddit "Creator" 또는 "관리자" 역할이 필요합니다.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Reddit**을 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. **Snap으로 로그인**을 클릭합니다.
6. 로그인을 완료하고 권한을 제공합니다.  **참고**: 앱스플라이어가 전체 데이터를 가져오려면 전체 권한을 허용하는 것을 권장합니다.
7. **저장**을 클릭합니다.

</Accordion>

<div id="remerge" />

<Accordion title="Remerge">

**선행 조건:**

* 연동을 위한 자격 증명(**참고**: Remerge 대시보드에 액세스하는 데 사용되는 자격 증명과 동일한 자격 증명을 사용합니다. 자세한 내용은 <Anchor target="_blank" href="https://help.remerge.io/hc/en-us/articles/115003440434-Remerge-Reporting-API">Remerge 문서</Anchor>를 확인하세요):
  * 사용자 이메일
  * 비밀번호

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있는 경우, ⋮ 아이콘을 클릭하여 **크리에이티브 연동**으로 이동합니다. ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Remerge**를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. 이메일과 비밀번호를 입력합니다.
6. **저장**을 클릭합니다.

</Accordion>

<div id="revx" />

<Accordion title="RevX">

**선행 조건:**

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Reddit**을 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. RevX **API 키를** 입력합니다 (API 키를 받으려면 RevX 계정 관리자에게 직접 문의하십시오).
6. **저장**을 클릭합니다.

</Accordion>

<div id="smadex" />

<Accordion title="Smadex">

**선행 조건:**

* 연동을 위한 Smadex 자격 증명 (**참고**: Moloco 대시보드에 액세스하는 데 사용하는 자격 증명과 동일한 자격 증명을 사용합니다):
  * 이메일
  * 비밀번호

**연동을 추가하려면 다음을 수행합니다.**

1. 1. **광고 크리에이티브 최적화** 에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있는 경우, ⋮ 아이콘을 클릭하여 **크리에이티브 연동**으로 이동합니다. ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Moloco**를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. 필요한 자격 증명을 입력합니다..
6. **저장**을 클릭합니다.

</Accordion>

<div id="snap" />

<Accordion title="Snapchat">

**선행 조건:** 연동하려는 앱에 대한 광고 계정 권한이 필요합니다. **참고**: Snap과의 연동은 사용자별로 이루어지므로 여러 사용자가 동시에 활성 연동을 수행할 수 있습니다.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Snapchat**을 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. **Snapchat 로그인**을 클릭합니다. 창이 열립니다.
6. 로그인을 완료하고 권한을 제공합니다.  앱스플라이어가 전체 데이터를 가져오려면 전체 권한을 허용하는 것을 권장합니다.
7. **저장**을 클릭합니다.

**참고:** 특정 광고 유형은 지원되지 않으며, 이는 광고 크리에이티브 최적화의 데이터를 광고 크리에이티브 수준이 아닌 광고 수준에서만 사용할 수 있음을 의미합니다. 지원되지 않는 광고 유형에는 컬렉션 광고(Collection Ads)가 포함됩니다.

</Accordion>

<div id="tiktok" />

<Accordion title="TikTok">

**선행 조건:**

* 연동하려는 앱에 대한 광고 계정 권한이 필요합니다. **참고**: TikTok과의 통합은 사용자별로 이루어지므로 여러 사용자가 동시에 활성 연동을 수행할 수 있습니다.
* Spark Ads에서 크리에이티브 데이터를 가져오려면 TikTok 비즈니스 센터 관리자가 크리에이티브와의 연동을 설정하는 사용자에게 관련 권한을 제공해야 합니다.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **TikTok**을 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. **TikTok으로 로그인**을 클릭합니다. 창이 열립니다.
6. 로그인을 완료하고 권한을 제공합니다.  앱스플라이어가 전체 데이터를 가져오려면 전체 권한을 허용하는 것을 권장합니다.
7. **저장**을 클릭합니다.

> 📘 **참고 사항**
>
> * 2023년 1월 30일에 새로운 **TikTok for Business —고급 SRN** 연동 `tiktokglobal_int`이 추가되었으며, **레거시 TikTok for Business** 연동`bytedanceglobal_int`은 단계적으로 중단되어 2024년 3월부터 종료됩니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/bulletin-tiktok-for-business-advanced-srn">업데이트 알림</Anchor>을 확인하세요.
>   * 새롭게 연동(tiktokglobal\_int)이 된 후에도 기존 연동(bytedanceglobal\_int)이 계속 활성 상태인 경우, 두 네트워크 모두에서 성과 데이터를 가져오므로 크리에이티브 최적화에 성과 데이터가 중복됩니다.
>   * AI가 실제 애셋을 식별하기 때문에 광고 크리에이티브는 중복되지 않습니다.
>   * 레거시 연동을 제거해도 제품에서 기록 데이터가 삭제되지 않습니다.
>   * 필요한 모든 데이터를 가져오려면 TikTok SRN을 연결하는 사람에게 관련 권한이 있어야 합니다.(광고 계정 관리자 권장)
> * 특정 광고 유형은 지원되지 않으며, 이는 광고 크리에이티브 최적화의 데이터를 광고 크리에이티브 수준이 아닌 광고 수준에서만 사용할 수 있음을 의미합니다. 지원되지 않는 광고 유형에는 컬렉션 광고와 쇼핑 광고가 포함됩니다.

</Accordion>

<div id="unity-ads" />

<Accordion title="Unity Ads">

**선행 조건:**

* 연동을 위한 Unity 서비스 계정 자격 증명:
  * Key ID
  * Secret key
  * Organization core ID

[자격 증명 검색에 대한 지침을 참조하세요.](/docs/creative-optimization-partner-integrations#자격-증명-검색-지침)

* 다음의 service account (organization) roles 을 Unity 내에서 선택:
  * 광고 API 관리자 역할은 크리에이티브를 가져오는 데 필요합니다.
  * **광고주 API 통계 뷰어** 역할은 크리에이티브 외에 Unity 메트릭을 가져오려면 필요합니다. <Anchor target="_blank" href="https://services.docs.unity.com/statistics/#section/Migrating-from-the-previous-version-of-the-API/Query-parameters">더 알아보기</Anchor>

**참고:** 이 역할이 제공되지 않는 경우, Unity Ads CSM에 문의하세요.

#### 자격 증명 검색 지침

**Key ID 및 Secret Key를 검색하려면 다음을 수행합니다.**

1. Unity Ads에 로그인합니다.
2. 메인 메뉴 측면 패널에서 **Administration**를 클릭한 다음 **Service Accounts**을 클릭합니다.
3. 필요한 서비스 계정을 클릭합니다.
4. **+ Add key**를 클릭합니다.  
   클릭 후, Key ID와 Secret key가 표시됩니다.
5. **Key ID**와 **Secret key**를 복사합니다.  
   ![Unity get Key ID & Secret key image.jpg](https://files.readme.io/9c4d1b1e0e476546b8f8be3a7375c610c48db6f94344a3dbe48277a6d115f52e-20344146224401.jpg)

<Anchor target="_blank" href="https://services.docs.unity.com/advertise/v1/index.html#section/General-Information/Resource-IDs-Used-in-the-API-Calls">**Organization core ID**</Anchor>**를** **받으려면:**

1. Unity Ads의 사이드 메뉴에서 **Products**를 클릭합니다.
2. **Grow**를 클릭하세요.  
   ![Unity Org ID step 1 cropped.jpg](https://files.readme.io/5e8d2f54f5999c58b2e2b3591ae889f5051cae4073aa6c5ef17e16da6a60131f-22859368875153.jpg)
3. **Unity Ads User Acquisition**을 클릭합니다.  
   <Image alt="Unity Org ID step 2 cropped.jpg" src="https://files.readme.io/07a1c8e878a9ed7b6832012b3261866477b825d3b23e4973b8c5dadd675973e2-22859368883473.jpg" width="347px" />
4. **Settings**을 클릭하세요.  
   ![Get Organization core ID instructions 2 arrows.jpg](https://files.readme.io/aff97bcb1c255771fc46483d8d94a2f13c7ef26c45a7fc884b1c03c83da91ae5-20344868139153.jpg)
5. **Organization core ID**를 복사합니다.

#### **서비스 계정(organization) 역할을 선택하려면:**

1. Unity 대시보드에서 **Administration**을 클릭합니다.   
   **<Image alt="Org roles step 1.jpg" src="https://files.readme.io/b9a9258cf324cdf0c73ab9be8d1646c43d2211d23cebafa3624582e6e964851f-20347001525777.jpg" width="372px" />**
2. **서비스 계정**을 클릭합니다.
3. 관련 서비스 계정을 클릭한 다음 **+ Manage organization roles**를 클릭합니다.  
   **![Org roles step 2.jpg](https://files.readme.io/f72334c392a89084c22fc6c6d97cedb051b4a53de9bad1eb3722c2e0f31852de-20347023191697.jpg)**
4. **Growth** 드롭다운 메뉴에서 다음 서비스 계정 조직 역할을 선택합니다.
   * 광고주 API 통계 뷰어 - Unity 지표를 가져옵니다.
   * 아래의 역할 중 하나를 사용하여 광고 크리에이티브를 가져옵니다.
     * 광고 API 관리자
     * 광고 API 뷰어
     * 광고 API 광고 크리에이티브 팩 에디터  
       <Image alt="Org roles step 3 without role names.jpg" src="https://files.readme.io/7b46417e6389f7c3675cc6f72b33e9b2833d5c561ef1d79122ed24605533b265-20347535827217.jpg" width="471px" />
5. **저장**을 클릭합니다.

**참고:** 해당 역할에 액세스할 수 없는 경우, Unity 고객 성공 관리자에게 문의하거나 [unityads-support@unity3d.com](mailto:unityads-support@unity3d.com)로 이메일을 보내 필요한 권한을 요청하세요.

#### **광고 크리에이티브 대시보드에 Unity 연동을 추가하는 방법은 다음과 같습니다.**

1. **광고 크리에이티브 최적화** 대시보드에서 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **Unity Ads**를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. 키 ID, 비밀 키, 조직 코어 ID를 입력합니다.
6. <Anchor target="_blank" href="/marketers/ko/docs/creative-optimization-guide#partner-metrics::e592ecd3">파트너 지표</Anchor> 정보를 입력하여 Unity Ads에서 보고한 지표도 가져옵니다.(선택 사항)
7. **저장**을 클릭하세요.

</Accordion>

<div id="x-ads" />

<Accordion title="X Ads(이전의 Twitter Ads)">

**선행 조건:**

* 광고 크리에이티브를 가져오려면 X Ads의 '계정 관리자' 또는 '광고 관리자' 역할이 필요합니다.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **X Ads**를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. **X Ads로 로그인**을 클릭합니다.
6. 로그인을 완료하고 권한을 제공합니다.  **참고**: 앱스플라이어가 전체 데이터를 가져오려면 전체 권한을 허용하는 것을 권장합니다.
7. **저장**을 클릭하세요.

</Accordion>

<div id="youappi" />

<Accordion title="YouAppi">

**전제 조건:**

연동을 위한 YouAppi 자격 증명:

* 토큰  
  **참고**: YouAppi의 계정 관리자에게 연락하여 토큰을 받을 수 있습니다. 자세한 내용은 <Anchor target="_blank" href="https://support.youappi.com/knowledgebase/reporting-api-for-re-engagement/">YouAppi 문서</Anchor>를 참조하세요.

**연동을 추가하려면 다음을 수행합니다.**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 파트너 연동이 있으면, 오른쪽 상단에 있는  ⋮  아이콘을 클릭하여 **광고 크리에이티브 연동**으로 이동합니다.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. **+ 새 연동**을 클릭합니다.
3. **파트너** 목록에서 **YouAppi**를 선택합니다.
4. 홍보 중인 앱을 선택합니다.
5. 토큰을 입력합니다.
6. **저장**을 클릭하세요.

</Accordion>

## 추가 정보

<div id="creative-integrations-dashboard" />

<Accordion title="크리에이티브 연동 대시보드">

크리에이티브 연동 대시보드에서는 새 미디어 파트너 연동을 추가할 수 있습니다. 새 연동을 추가하려면, [파트너별 세부 지침](/docs/creative-optimization-partner-integrations#데이터-가용성)을 따르십시오.

새 연동이 추가되면, 대시보드에 모든 현재 연동의 상태가 다음 열과 함께 표시됩니다.

| 열 | 설명 |
| --- | --- |
| 파트너 | 연동 파트너의 이름(예: Meta 광고 또는 ironsource\_int) 파트너 열을 확장하면 파트너에 대한 다른 연결 상태를 모두 확인할 수 있습니다. 예를 들어 각 사용자는 고유하게 연결될 수 있습니다. |
| 앱 | 연동 파트너 및 특정 사용자 연결별 앱 목록입니다. |
| 연동 업데이트 | 파트너 연동 설정이 마지막으로 업데이트된 날짜입니다. |
| 커버리지 상태 | 크리에이티브 최적화 대시보드 및 리포트에서 사용할 수 있는, 파트너 연동으로부터의 크리에이티브 성과 데이터량:<ul><li>**Low(낮음)**: 이 연동에 포함된 모든 앱에서 데이터가 누락되어 있습니다.</li><li>**Partial(일부)**: 이 연동에 포함된 일부 앱에는 데이터가 누락되어 있습니다.</li><li>**High(높음)**: 이 연동에 포함된 모든 앱에 데이터가 있습니다.</li><li>**In progress(진행 중)**: 상태 업데이트를 위해 최대 24시간 동안 대기합니다.</li><li>**No data(데이터 없음)**: 이 파트너의 데이터가 지난 90일 동안 누락되어 있습니다.</li></ul>상태를 클릭하면 앱별 커버리지 상태 분석을 볼 수 있습니다. ROI360 구독자 여부에 따라 앱별 상태가 나타내는 의미가 다릅니다.<br /><br />**ROI360 비구독자:**<ul><li>**High(높음)**: 앱에 많은 크리에이티브 데이터가 있습니다. 이는 파트너로부터 가져온 크리에이티브 데이터가 지난 90일 동안 기록된 앱 인스톨의 총 85% 이상(앱스플라이어가 측정한 인스톨 기준)을 커버한다는 의미입니다.</li><li>**Low(낮음)**: 앱에 크리에이티브 데이터가 누락되어 있습니다. 이는 파트너로부터 가져온 크리에이티브 데이터가 지난 90일 동안 기록된 앱 인스톨의 총 85% 미만(앱스플라이어가 측정한 인스톨 기준)을 커버한다는 의미입니다.</li></ul>**ROI360 구독자:**<ul><li>**High(높음)**: 지난 90일 동안 앱스플라이어 ROI360을 통해 측정된 비용 데이터의 85% 이상을 파트너로부터 가져온 크리에이티브 데이터가 커버한다는 의미입니다.</li><li>**Low(낮음)**: 지난 90일 동안 앱스플라이어 ROI360을 통해 측정된 비용 데이터의 85% 미만을 파트너로부터 가져온 크리에이티브 데이터가 커버한다는 의미입니다.<br />**예시**:<ul><li>앱스플라이어가 총 광고 지출액이 $100인 “네트워크 A” 미디어 소스에 대한 데이터를 가져옵니다.</li><li>크리에이티브 1에서는 85달러, 크리에이티브 2에서는 15달러의 광고 지출이 발생했습니다.</li><li>만약 앱스플라이어가 크리에이티브 1 데이터를 가져올 경우, 크리에이티브 1은 비용의 85%를 차지합니다. 그러므로 이는 “High(높음)” 커버리지에 해당합니다.</li><li>만약 앱스플라이어가 크리에이티브 2 데이터만 가져올 경우, 크리에이티브 2의 비용은 15%에 불과하므로 커버리지가 “Low(낮음)”으로 표시됩니다.</li></ul></li></ul>**ROI360 구독자 및 비구독자 모두 해당:**<ul><li>**In progress(진행 중)**: 상태 업데이트를 위해 최대 24시간 동안 대기합니다.</li><li>**Low data(데이터 낮음)**: [파트너별 지침](/docs/creative-optimization-partner-integrations#데이터-가용성)에 따라 파트너가 올바르게 연동되었는지 확인합니다.</li><li>**No data(데이터 없음)**: 지난 90일 동안 이 앱의 데이터가 없습니다.<ul><li>(크리에이티브와 상관없이) 일반적인 앱스플라이어 설정이 완료되어있고 잘 작동하는지 확인하십시오.</li><li>앱이 활성 상태이고 트래픽이 있는지 확인합니다.<br />에이전시에서 연동을 관리하는 경우, [에이전시 지침](/docs/creative-optimization-partner-integrations#agencies)에 따라 올바르게 연동이 설정돼 있는지 확인합니다.</li></ul></li></ul> |

</Accordion>

<div id="agencies" />

<Accordion title="에이전시 연동">

#### 에이전시 연동 추가하기:

에이전시 파트너와 연동하여 해당 데이터를 광고 크리에이티브 대시보드로 가져올 수 있습니다.

**에이전시 연동 추가하기:**

1. **광고 크리에이티브 최적화**에 로그인하고 다음 중 하나를 수행합니다.
   * 파트너 연동이 없는 경우 + **새 연동 추가**를 클릭합니다.
   * 그렇지 않으면 대시보드의 오른쪽 상단에 있는  ⋮ 아이콘을 클릭하여 광고 소재 연동으로 이동합니다.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. **+ 새 연동**을 클릭합니다.
3. 파트너 연동 창에서 파트너 및 앱을 선택한 후 **에이전시** 토글을 클릭합니다. 에이전시 드롭다운에서 관련 에이전시를 선택하세요.  

   <Image alt="크리에이티브 에이전시.png" src="https://files.readme.io/74f0dc492bc530278687becdd0061e9c06081653b69ed525f237b97a9568e413-38395601553169.png" width="288px" />
4. **저장**을 클릭하세요.  
   이제 에이전시 연동이 추가되었습니다.

**참고:**

* 각각의 에이전시가 운영하는 크리에이티브에 대한 데이터를 대시보드에서 보고자 하는 경우, "에이전시" 체크박스를 선택한 상태에서 별도의 파트너 연동을 진행해야 합니다.
* 에이전시 투명성이 설정돼 있는 에이전시의 데이터만 사용할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/view-agency-data">더 알아보기</Anchor>
* 광고 크리에이티브 데이터는 에이전시에서만 가져옵니다. 위의 예시는 에이전시가 운영하는 Google Ads 캠페인이 있을 경우에 해당되는 예시이나, 직접 운영 중인 Google Ads 캠페인도 있는 경우 Google Ads를 위한 추가 파트너 연동을 진행해야 합니다.

#### 에이전시에 대시보드 액세스 권한 부여

에이전시가 AppsFlyer <Anchor target="_blank" href="/partners/ko/docs/about-agency-accounts">에이전시 계정</Anchor>을 가지고 있다면, 크리에이티브 최적화 대시보드에서 자신의 크리에이티브 성과 데이터를 볼 수 있는 액세스 권한을 부여할 수 있습니다. 이는 투명성과 협업을 향상시키는 데 도움이 될 수 있습니다.

**액세스를 활성화하려면:**

1. 앱스플라이어 사이드 메뉴에서 **협업** > **파트너 마켓플레이스**를 클릭하세요.  

   **<Image alt="콜라보레이트에서 파트너 Marketplace.png 를 클릭합니다." src="https://files.readme.io/96485cefae79412a680915810c16b23619f73d9109212bfc45d1c0d42c2e529a-39258887136785.png" width="33.9%" />**
2. 페이지 상단의 검색창에서 관련 파트너 에이전시를 검색한 후, 파트너를 클릭하세요.

   <Image alt="검색창.png" src="https://files.readme.io/f1ff34a547af45eec73e7abd41105bbab9ff12d4a2636ed4b99634985ec58044-39258887138449.png" width="1210px" />
3. 파트너 페이지에서 **권한 탭으로 이동하여** 에이전시 권한을**** 활성화합니다.

   에이전시 권한
4. 그런 다음 **크리에이티브 최적화 대시보드 접근** 을 활성화하세요.  

   이제 에이전시는 대시보드에서 공유된 크리에이티브를 볼 수 있습니다. 아직 앱스플라이어 에이전시 계정을 설정하지 않은 에이전시는 <Anchor target="_blank" href="/partners/ko/docs/getting-started-agency-onboarding">여기에서.</Anchor> 더 많은 정보를 얻을 수 있습니다.

</Accordion>

<div id="update-credentials" />

<Accordion title="자격 증명 업데이트">

특정 파트너 연동이 설정되면 계정 수준 자격 증명을 변경할 수 없습니다(Meta 광고, Google Ads, TikTok 및 AppLovin에는 적용되지 않음). 파트너에 대한 자격 증명을 업데이트해야 하는 경우:

1. **크리에이티브 연동** 페이지에서 파트너 왼쪽에 있는 확장 메뉴를 선택하여 파트너 연결을 엽니다.
2. <Image alt="3 dots icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="7px" /> 메뉴 아이콘을 클릭한 다음 **연동 삭제**를 선택하세요. ![partner-integration-side-menu.png](https://files.readme.io/43ba588af05ffb8dafa165cf5d760010d36bd8b6409f6f9f4ef131d695989ed2-18565371542033.png)
3. 업데이트된 자격 증명을 사용하여 파트너에 대한 새 연동을 생성합니다.

</Accordion>

<div data-zendesk-anchors="about-creative-partner-integrations=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EB%8F%99%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HAP6JQEFKAFK96WDBN0MERB6=%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EB%8F%99%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC media-partner-integrations=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01HEQ2QR21MZB57S6MQ5ZWZ7ZQ=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01K4M4JF53A3J1R5VACNVN4X8A=%EC%B0%B8%EA%B3%A0 h_01HC7W736NDRRAJ95Z28JS2J46=%EB%AF%B8%EB%94%94%EC%96%B4-%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EB%8F%99 h_01HBAZ8724YYFVQWYV5F8F4F5S=adikteev 01H7SZ8RA055S4M11TTX1J0E55=adjoe 01H7SZ8RA0A52YQEMYX0GV44AB=applovin h_01KY4CAH2MKX650JS1R0N8X6B4=%EC%B0%B8%EA%B3%A0-1 01H7SZ8RA0980TH09EP2ED9WSF=google-ads 01H7SZ8RA0DRWC76119ED96KHP=ironsource 01H7SZ8RA0428ZPRYD99GWRMK0=liftoff 01H7SZ8RA06V5BR4ABV0ZVK82Z=facebook-ads h_01JXCRAESXDAHGGJ71EB32NAPD=mintegral 01H7SZ8RA06G1W04NSEHSPSV2D=moloco h_01KRGPVZH0Z0DHEEJNP4ST5CD9=personaly 01J9V2ZJR6KYJERPR2Y2XNCREP=reddit 01H7SZ8RA0CDR1M5V2F177TG84=remerge h_01KRGPVZH00WKJ4VJN8QHAW3YS=revx h_01HZEP4F6M2W5HC76WVFP5Z5C0=smadex 01H7SZ8RA1H0Q47N1W3NST4PZW=snap 01H7SZ8RA1E221TK8VRWEF1FA4=tiktok 01H8VVCC8GW5AZ3M475XFZY9JW=%EC%B0%B8%EA%B3%A0-%EC%82%AC%ED%95%AD 01H7SZ8RA1YTA3MGVJMXVTP78Y=unity-ads instructions-for-retrieving-the-credentials=%EC%9E%90%EA%B2%A9-%EC%A6%9D%EB%AA%85-%EA%B2%80%EC%83%89-%EC%A7%80%EC%B9%A8 h_01GT6Z998RCBQWKDC9YGPJQGN6=%EC%9E%90%EA%B2%A9-%EC%A6%9D%EB%AA%85-%EA%B2%80%EC%83%89-%EC%A7%80%EC%B9%A8 to-select-a-service-account-organization-role=%EC%84%9C%EB%B9%84%EC%8A%A4-%EA%B3%84%EC%A0%95organization-%EC%97%AD%ED%95%A0%EC%9D%84-%EC%84%A0%ED%83%9D%ED%95%98%EB%A0%A4%EB%A9%B4 h_01GT6ZFTGKMR18DTNVX706DH1R=%EC%84%9C%EB%B9%84%EC%8A%A4-%EA%B3%84%EC%A0%95organization-%EC%97%AD%ED%95%A0%EC%9D%84-%EC%84%A0%ED%83%9D%ED%95%98%EB%A0%A4%EB%A9%B4 to-add-a-unity-connection-to-the-creative-dashboard=%EA%B4%91%EA%B3%A0-%ED%81%AC%EB%A6%AC%EC%97%90%EC%9D%B4%ED%8B%B0%EB%B8%8C-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90-unity-%EC%97%B0%EB%8F%99%EC%9D%84-%EC%B6%94%EA%B0%80%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%8B%A4%EC%9D%8C%EA%B3%BC-%EA%B0%99%EC%8A%B5%EB%8B%88%EB%8B%A4 h_01GT6ZS52ZWY47BCT2NJVCFFEP=%EA%B4%91%EA%B3%A0-%ED%81%AC%EB%A6%AC%EC%97%90%EC%9D%B4%ED%8B%B0%EB%B8%8C-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90-unity-%EC%97%B0%EB%8F%99%EC%9D%84-%EC%B6%94%EA%B0%80%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%8B%A4%EC%9D%8C%EA%B3%BC-%EA%B0%99%EC%8A%B5%EB%8B%88%EB%8B%A4 01J9V2ZJSKN37WSGKA6D12MYBH=x-ads 01H7SZ8RA1E37649AAH1DNRXA9=youappi agency-integrations=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HC7WCZ143S29PGTVNFEX962Y=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01J9WK9A78RP6BKX6860MAABFM=creative-integrations-dashboard h_01HC7WCE9EJK3NDJQE88RZ3T0Z=agencies add-an-agency-integration=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%97%B0%EB%8F%99-%EC%B6%94%EA%B0%80%ED%95%98%EA%B8%B0 h_01K5PE1K1G75KEF9HXMAW9YP2F=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%97%B0%EB%8F%99-%EC%B6%94%EA%B0%80%ED%95%98%EA%B8%B0 grant-dashboard-access=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C%EC%97%90-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%95%A1%EC%84%B8%EC%8A%A4-%EA%B6%8C%ED%95%9C-%EB%B6%80%EC%97%AC h_01K5PE1WK5AE2MX235B8FA4YJ0=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C%EC%97%90-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%95%A1%EC%84%B8%EC%8A%A4-%EA%B6%8C%ED%95%9C-%EB%B6%80%EC%97%AC 01J9WKGYM1D04ZT14EPZ13VE4P=update-credentials" />
