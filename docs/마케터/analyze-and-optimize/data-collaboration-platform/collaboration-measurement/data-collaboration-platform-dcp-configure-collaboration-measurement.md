---
title: 데이터 협업 플랫폼(DCP, data collaboration platform) - 협업 측정 - 개요
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
  created_at: '2025-01-27T09:58:46Z'
  edited_at: '2026-10-14T10:40:53Z'
  id: 32147174933905
  locale: ko
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/ko/articles/32147174933905
---
**한눈에 보기:** DCP를 구성하여 전환, 참여 및 캠페인 매핑 데이터를 기반으로 SKU 수준의 귀속을 수행하는 방법을 배우십시오.

<div id="overview" />

## 개요

전환, 참여 및 캠페인 매핑 데이터를 준비한 후, DCP를 구성하여 이를 측정 및 귀속에 사용할 수 있습니다:

1. 캠페인 유형 정의 – 온사이트, 오프사이트 또는 결합을 선택하십시오. 이는 DCP가 데이터를 처리하는 방식과 필요한 구성 작업을 설정하는 방법을 결정합니다.
2. 작업 할당 – 소유자는 각 구성 작업을 관련 데이터에 접근할 수 있는 협력자에게 할당합니다.
3. 작업 구성 – 협력자는 전환, 참여 및 캠페인 매핑을 구성합니다. 여기에는 모든 데이터가 연결되고 매핑되어 귀속을 위해 준비되도록 온사이트 및 오프사이트 캠페인을 설정하는 것이 포함됩니다.
4. 측정 실행 및 관리 - 실시간 또는 과거 측정을 실행하고, 복제하고, 다시 실행하거나 범위를 변경하십시오.

<div id="start-the-measurement-setup" />

## 측정 설정을 시작하십시오.

측정 설정을 시작하려면 다음 단계를 따르십시오:

1. AppsFlyer에서 사이드 메뉴에서 **협업** > **데이터 클린룸**으로 이동하십시오.
2. **데이터 협업 플랫폼** 페이지에서 설정하려는 협업을 선택하십시오.
3. 협업 페이지에서 다음 단계 중 **하나**를 수행하십시오:
   * 이 협업에서 첫 번째 측정을 설정하는 경우, **측정 설정.** 을 클릭하십시오. **측정 생성** 페이지가 표시됩니다.
   * 이미 협업에 측정 세트가 있는 경우, 측정 선택 패널에서 더하기 기호를 클릭하십시오. **측정 생성** 페이지가 표시됩니다.

[![start-measurement.png](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)

<div id="select-campaign-type-on-site-off-site-or-both" />

## 캠페인 유형 선택: 온사이트, 오프사이트 또는 둘 다

온사이트 및 오프사이트 캠페인 유형은 전환이 발생하는 위치와 귀속 처리 방식이 다르므로, 협업 소유자는 협업 측정을 구성하기 전에 캠페인 유형을 지정해야 합니다. 자세한 내용은 다음을 참조하세요. 온사이트 대. 오프사이트 캠페인 측정.

캠페인 유형을 선택하려면 다음 단계를 따르십시오:

1. [측정 설정 시작](#측정-설정을-시작하십시오).
2. **측정 만들기** 페이지에서 <Image alt="온사이트 아이콘.png" src="https://files.readme.io/c9ff0bb1e2c31527ee38a9403a6180e3ecd4c3ad105935fb59ed14c2474f6039-32148924980113.png" width="3.27%" /> **온사이트, <Image alt="오프사이트 아이콘.png" src="https://files.readme.io/6de5841985237de221c74d427ad06f719572000aafe8077c7cef64e53ee8caf5-32156666763921.png" width="3.3%" /> 오프사이트** 또는 둘 다 선택하십시오. 다음 중 **하나**를 계속하십시오:
   * [온사이트 캠페인 구성](#온사이트-및-오프사이트-캠페인-측정),
   * [오프사이트 캠페인 구성](#configure-offsite-campaign-measurement),
   * [온사이트 및 오프사이트 캠페인 결합 구성](#configure-combined-onsite-and-offsite-campaign-measurement).

<div id="assign-configuration-task" />

## 구성 작업 할당

측정 설정 페이지에는 다섯 가지 주요 작업이 포함됩니다: 전환, 참여, 캠페인 매핑, 미디어 파트너 및 회상 기간 구성.

DCP 계정 소유자는 데이터 프라이버시를 보장하고 책임 분담을 반영하기 위해 협력자에게 작업을 할당할 수 있습니다. 예를 들어, 한 협력자는 참여 데이터를 처리하고 다른 협력자는 전환을 처리할 수 있습니다. 협력자는 할당된 작업에만 접근할 수 있습니다.

<div id="assign-a-configuration-task-to-a-collaborator" />

<Accordion title="협력자에게 구성 작업을 할당하십시오.">

위의 작업 중 하나를 할당하려면 아래 단계를 따르십시오:

1. 측정 설정
2. 위의 네 가지 작업 각각에서 **수신자** 목록에서 작업을 처리할 협력자를 선택하십시오.
   * **전환 작업:** 전환을 호스팅하는 플랫폼의 협력자에게 할당하십시오.
   * **캠페인 작업:** 전환을 호스팅하는 플랫폼의 협력자에게 할당하십시오.
   * **참여 작업:** 사용자 참여가 발생하는 협력자에게 할당하십시오.
   * **미디어 파트너 작업:** 오프사이트 캠페인에 사용되는 미디어 파트너 계정이 있는 협력자에게 할당하십시오.
   * **회고 기간 작업**– 협력 소유자에게 자동으로 할당됩니다. 다른 협력자에게 선택적으로 할당할 수 있습니다.

</Accordion>

<div id="remove-the-configuration-task-assignment-from-a-collaborator" />

<Accordion title="협력자로부터 구성 작업 할당을 제거하십시오.">

경우에 따라 협력자로부터 구성 작업 할당을 철회해야 할 수도 있습니다. 협력 소유자가 할당을 제거하면 다음과 같은 일이 발생합니다:

* 협력자는 즉시 할당되지 않은 작업에 대한 접근 권한을 잃습니다.
* 해당 작업에 대해 협력자가 이전에 제공한 모든 구성은 폐기됩니다.
* 협력 측정이 중단됩니다.

구성 작업 할당을 제거하려면 아래 단계를 따르십시오:

1. 협력 측정으로 이동하여 측정 설정 열기를 확인하십시오.
2. 관련 구성 단계에서 **할당자** 목록에서 할당된 협력자를 제거하십시오.

</Accordion>

<div id="configure-on-site-and-off-site-campaign-measurement" />

## 온사이트 및 오프사이트 캠페인 측정

측정 설정에서 캠페인 측정 설정을 구성하십시오. 측정이 온사이트, 오프사이트 또는 결합된 온사이트 및 오프사이트 설정인지에 따라 아래 단계를 사용하십시오.

<div id="configure-onsite-campaign-measurement::4f9b35af" />

<Accordion title="온사이트 캠페인 측정 구성">

<Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-campaigns">온사이트 캠페인</Anchor>을 설정하려면 다음 단계를 따르십시오:

1. [측정 설정 시작](#측정-설정을-시작하십시오).
2. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-campaigns-task">캠페인 작업 설정</Anchor>
3. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-conversions-task">전환 작업 설정</Anchor>
4. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-engagements-task">참여 작업 설정</Anchor>
5. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-lookback-windows-task">회고 기간 작업 설정</Anchor>

</Accordion>

<div id="configure-offsite-campaign-measurement" />

<Accordion title="오프사이트 캠페인 측정 구성">

<Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">오프사이트 캠페인</Anchor>을 설정하려면 다음 단계를 따르십시오:

1. [측정 설정 시작](#측정-설정을-시작하십시오).
2. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-campaigns-task">캠페인 작업 설정</Anchor>
3. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-conversions-task">전환 작업 설정</Anchor>
4. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-media-partners-task">미디어 파트너 작업 설정</Anchor>
5. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-lookback-windows-task">회고 기간 작업 설정</Anchor>

</Accordion>

<div id="configure-combined-onsite-and-offsite-campaign-measurement" />

<Accordion title="온사이트 및 오프사이트 캠페인 측정 통합 구성">

<Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">온사이트 및 오프사이트 캠페인</Anchor>을 설정하려면 다음 단계를 따르십시오:

1. [측정 설정 시작](#측정-설정을-시작하십시오).
2. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-campaigns-task">캠페인 작업 설정</Anchor>
3. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-conversions-task">전환 작업 설정</Anchor>
4. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-engagements-task">참여 작업 설정</Anchor>
5. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-media-partners-task">미디어 파트너 작업 설정</Anchor>
6. <Anchor target="_blank" href="/marketers/ko/docs/set-up-the-lookback-windows-task">회고 기간 작업 설정</Anchor>

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01K3EHANCCZ703MMMM5PTEF68B=%EA%B0%9C%EC%9A%94 open-measurement-settings=%EC%B8%A1%EC%A0%95-%EC%84%A4%EC%A0%95%EC%9D%84-%EC%8B%9C%EC%9E%91%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01JJKK3CQ8F9Q7VM7MM9AFKNN5=%EC%B8%A1%EC%A0%95-%EC%84%A4%EC%A0%95%EC%9D%84-%EC%8B%9C%EC%9E%91%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 select-campaign-type-onsite-offsite-or-both=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%9C%A0%ED%98%95-%EC%84%A0%ED%83%9D-%EC%98%A8%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%98%A4%ED%94%84%EC%82%AC%EC%9D%B4%ED%8A%B8-%EB%98%90%EB%8A%94-%EB%91%98-%EB%8B%A4 h_01K3EHANCCW8PQ8NWC6ZHWCMGT=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%9C%A0%ED%98%95-%EC%84%A0%ED%83%9D-%EC%98%A8%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%98%A4%ED%94%84%EC%82%AC%EC%9D%B4%ED%8A%B8-%EB%98%90%EB%8A%94-%EB%91%98-%EB%8B%A4 assign-configuration-task=%EA%B5%AC%EC%84%B1-%EC%9E%91%EC%97%85-%ED%95%A0%EB%8B%B9 h_01K3EHANCCW97TV88ECVMQKF2N=%EA%B5%AC%EC%84%B1-%EC%9E%91%EC%97%85-%ED%95%A0%EB%8B%B9 h_01K3EHANCD71R47V88DR61CTMV=assign-a-configuration-task-to-a-collaborator h_01K3EHANCDF1HMTV8X35Q1RHTS=remove-the-configuration-task-assignment-from-a-collaborator configure-onsite-campaign-measurement=%EC%98%A8%EC%82%AC%EC%9D%B4%ED%8A%B8-%EB%B0%8F-%EC%98%A4%ED%94%84%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%B8%A1%EC%A0%95 h_01K3EHANCD936QN2MKFY5QSDBZ=%EC%98%A8%EC%82%AC%EC%9D%B4%ED%8A%B8-%EB%B0%8F-%EC%98%A4%ED%94%84%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%B8%A1%EC%A0%95 h_01KJWCMN3XRTS3361N08RT1SD6=configure-onsite-campaign-measurement::4f9b35af h_01KJWCMN3XRXW6A71P5678AHH1=configure-offsite-campaign-measurement h_01KJWCMN3XKD8YJVPQEZ53K819=configure-combined-onsite-and-offsite-campaign-measurement" />
