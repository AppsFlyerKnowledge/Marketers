---
title: Google Play 자동 설치를 사용한 사전 로드 어트리뷰션
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-07-25T11:31:06Z'
  edited_at: '2026-10-14T10:39:05Z'
  id: 4404557237649
  locale: ko
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ko/articles/4404557237649
---
> **한눈에 보기:** 앱스플라이어는 Google Play 자동 설치l(PAI)를 사용하여 마케터가 모바일 통신사 및 앱 검색 파트너와 계약을 맺고 사용자가 기기를 처음 켤 때 앱을 미리 로드하는 프리로드 캠페인에 설치를 어트리뷰션합니다. **참고**: 이 어트리션 방법은 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-factory-preinstall-using-manifest-android">APK 사전 설치 어트리뷰션</Anchor>과 다릅니다.

## PAI 프리로드 어트리뷰션

프리로드 캠페인에서 OEM(주문자 상표 부착 생산), 이동통신사, 앱 검색 파트너는 첫 번째 기기 활성화 시 다운로드되는 기기에 앱을 프리로드합니다.

광고주는 프리로드 캠페인을 통해 온라인 캠페인을 실행하지 않고도 잠재적으로 많은 잠재 고객에게 다가갈 수 있습니다.

Google Play 자동 설치(PAI) (3가지 프리로드 어트리뷰션 방법 중 하나)는 마케터에게 정확하고 개인 정보를 보호하는 메커니즘을 제공하여 사전 로드 캠페인의 성과를 측정할 수 있도록 해줍니다. 이 방법은 마케터에게 결정적 어트리뷰션 결과를 제공하는 동시에 장치 및 사용자 식별자와 관계없이 생성된 Google Play 리퍼러와의 리퍼러 매칭을 통해 어트리뷰션이 수행되므로 사용자 개인 정보가 보호됩니다.

앱스플라이어는 프리로드 어트리뷰션에 가장 높은 우선순위를 부여합니다. 즉, 사용자가 앱을 처음 열기 전에 다른 캠페인에 참여하는 경우 프리로드 캠페인에 여전히 어트리뷰션이 부여됩니다. 다른 인게이지먼트는 인스톨 어시스트로 간주됩니다.

**참고**: 에이전시는 클라이언트에 대해 프리로드 캠페인을 활성화할 수 없습니다.

### 플로우

1. 새 기기가 처음으로 활성화되고 프리로드 파트너가 설정한 규칙에 따라 Google Play에서 사전 정의된 앱이 자동으로 설치됩니다.
2. 사용자가 프리로드된 앱을 처음으로 실행합니다.
3. 앱스플라이어 SDK는 Google Play 리퍼러 API를 쿼리합니다.
4. 앱스플라이어는 검색된 데이터를 기반으로 속성을 지정합니다.

![PAI-attribution-flow_en-us.png](https://files.readme.io/c7f02a0a6637e9c73e9a39f97e71d5d37d8d2712b458735cd87b4b245ad0fccb-small-4404791877649.png)

### 데이터 가용성

Google Play 자동 설치(PAI) 사전 로드 성능 데이터는 다음에서 사용할 수 있습니다.

* 개요 대시보드와 집계 보고서는 사전 로드 파트너(미디어 소스) 및 캠페인 수준에서 집계됩니다.
* 로데이터 보고서에서 사용할 수 있습니다.

로데이터에는 다음 필드가 포함됩니다.

* Media\_source = Partner ID
* Match\_type = preload\_pai
* Campaign\_name = 캠페인 프리로드 기준 `<preloadpartner ID>`

### Google Play 자동 설치(PAI) 프리로드 어트리뷰션 설정

**PAI 프리로드 어트리뷰션을 설정하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성 연동**을 선택합니다.
2. 프리로드 파트너를 선택하십시오.
3. 프리로드 어트리뷰션
4. **프리로드 기여 기간**을 설정합니다. 기간: 1-180일.
5. **연동 저장**을 클릭합니다.
6. 프리로드 파트너에게 캠페인에 기여할 준비가 되었음을 알립니다.

### Google Play 자동 설치(PAI) 사전 로드 캠페인을 지원하는 파트너

<table><thead><tr><th rowspan="2">파트너</th><th rowspan="2">PID</th></tr></thead><tbody><tr><td></td><td><span>xiaomipai_int</span></td></tr><tr><td><p>Transsion</p></td><td><span>shalltrypai_int</span></td></tr><tr><td><p>Oppo</p></td><td><span>oppopaipreinstall_int</span></td></tr><tr><td><p>Vivo</p></td><td><span>vivootapreload_int</span></td></tr><tr><td><p>TCL</p></td><td><span>tclpai_int</span></td></tr><tr><td><p>Motorola</p></td><td><span>motorola_int</span></td></tr><tr><td><p>MITV</p></td><td><span>mitvpai_int</span></td></tr><tr><td><p>ZTE</p></td><td><span>ztepai_int</span></td></tr><tr><td><p>Lenovotab</p></td><td><span>lenovotabpai4p_int</span></td></tr><tr><td><p>KDDI Pre-Install</p></td><td><span>kddipai_int</span></td></tr></tbody></table>

## 프리로드 파트너를 위한 포스트백

앱스플라이어와의 통합의 일환으로, 프리로드 파트너는 앱스플라이어가 전송한 포스트백의 콘텐츠와 엔드포인트를 정의합니다.

포스트백에 포함된 경우 매크로에는 사용자 관련 데이터가 포함됩니다. 지원되는 매크로는 다음 표에 나열되어 있습니다.

* **소스**: 데이터의 출처를 나타냅니다.
  * **SDK**: 앱 또는 서버 간 API에 내장된 앱스플라이어 SDK.
  * **앱스플라이어**: 앱스플라이어에서 처리한 후.

| 프리로드 파트너에 대한 포스트백 매크로(매개 변수 이름) | 소스 | 설명 |
| --- | --- | --- |
| app\_name | SDK | 광고주가 설정한 앱 이름 |
| country\_code | 앱스플라이어 | ISO 3166(alpha-2)을 사용한 국가 코드. 예: 미국, 중국 |
| 설치 시간 | SDK | 타임스탬프 설치 |
| 언어 | SDK | 장치에서 보고하고 장치 OS에서 설정하는 언어(로캘)입니다. |
| app\_id | SDK | 앱스플라이어의 고유 앱 식별자 |
| app\_version | SDK | 앱 개발자가 앱 코드에서 설정한 앱 버전 |
| device\_type | SDK | 장치의 상용 모델 이름입니다. 예시: |
| os\_버전 | SDK | 디바이스 운영 체제 버전 |

#### 포스트백 예시

```http
http://YourCompanyDomain.com?pid=(preinstall_partner)&app_name=(app-name)&app_id=(app-id)&install_time=(install-unix-ts)
```

<div data-zendesk-anchors="pai-preload-attribution=pai-%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HEJG4FHSGJDZ77Y281F7SG4R=pai-%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 pai-preload-attribution-flow=%ED%94%8C%EB%A1%9C%EC%9A%B0 h_01HEJG4FHSF8X1TEMMNJBYP71Z=%ED%94%8C%EB%A1%9C%EC%9A%B0 campaign-performance-data-availability=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01HEJG4FHSCMPJM5TRNSPNDHVN=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 run-preload-referrer-campaigns=google-play-%EC%9E%90%EB%8F%99-%EC%84%A4%EC%B9%98pai-%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 h_01HEJG4FHS7E5JZT2BBYG2BNEK=google-play-%EC%9E%90%EB%8F%99-%EC%84%A4%EC%B9%98pai-%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 partners-supporting-preload-referrer-campaigns=google-play-%EC%9E%90%EB%8F%99-%EC%84%A4%EC%B9%98pai-%EC%82%AC%EC%A0%84-%EB%A1%9C%EB%93%9C-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EC%A7%80%EC%9B%90%ED%95%98%EB%8A%94-%ED%8C%8C%ED%8A%B8%EB%84%88 h_01HEJG4FHSNEGR7R9VCSDT9TSZ=google-play-%EC%9E%90%EB%8F%99-%EC%84%A4%EC%B9%98pai-%EC%82%AC%EC%A0%84-%EB%A1%9C%EB%93%9C-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EC%A7%80%EC%9B%90%ED%95%98%EB%8A%94-%ED%8C%8C%ED%8A%B8%EB%84%88 postbacks-for-preload-partners=%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%ED%8C%8C%ED%8A%B8%EB%84%88%EB%A5%BC-%EC%9C%84%ED%95%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HEJG4FHSKD7DY6W7W65YBMGN=%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%ED%8C%8C%ED%8A%B8%EB%84%88%EB%A5%BC-%EC%9C%84%ED%95%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 preload-postback-example=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%98%88%EC%8B%9C h_01HEJG4FHSBFB456Z752HFC8KN=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%98%88%EC%8B%9C" />
