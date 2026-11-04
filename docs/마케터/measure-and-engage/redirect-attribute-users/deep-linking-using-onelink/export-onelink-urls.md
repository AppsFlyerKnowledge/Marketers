---
title: 원링크 URL 내보내기
metadata:
  keywords:
    - export
    - Marketers
    - download
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2022-01-09T11:58:46Z'
  edited_at: '2026-10-14T10:26:50Z'
  id: 4416027813905
  locale: ko
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ko/articles/4416027813905
---
> **한눈에 보기:** 요약: 앱스플라이어 사용자 인터페이스에서 생성된 모든 원링크 URL을 내려받습니다.

<div id="export-onelink-urls" />

## 원링크 URL 내보내기

원링크 사용자 인터페이스에서 원링크 설정을 사용하여 원링크 템플릿별로 생성된 모든 원링크 URL의 CSV 파일을 내려받습니다. (SDK, 원링크 API 또는 일괄 업로드를 통해 생성된 원링크 URL은 내보낼 수 없습니다.)

CSV 파일에는 각 링크에 대해 다음과 같은 정보가 포함되어 있습니다.

* 링크 이름
* 미디어 소스
* 캠페인 이름
* 단축 URL
* 긴 URL
* 마지막 수정/생성 날짜(MM:DD:YY HH:MM)
* 수정한 사람(이메일)

샘플 CSV

**참고**: 참고: 링크가 앱스플라이어 UI에서 처음 생성되었지만 파라미터가 UI 외부에서 업데이트되면(원링크 API, 스프레드시트 등을 사용하여) 업데이트된 파라미터는 내려받은 CSV의 일부가 아닙니다.

CSV를 내려받으려면:

1. 앱스플라이어에서 **경험 및 딥링킹** > **원링크 커스텀 링크**로 이동 합니다.
2. 링크 목록을 원하는 원링크 템플릿을 선택합니다.
3. 내보내기를 클릭합니다. **CSV 파일이 다운로드됩니다.**

<div id="traits-and-limitations" />

### 특징 및 제약 사항

| **특징** | **비고** |
| --- | --- |
| 대행사 | 원링크 템플릿을 기반으로 만든 링크만 가져올 수 있습니다. |
| 광고주 | 원링크 템플릿을 기반으로 만든 링크만 가져올 수 있습니다. |

<div data-zendesk-anchors="export-onelink-urls=%EC%9B%90%EB%A7%81%ED%81%AC-url-%EB%82%B4%EB%B3%B4%EB%82%B4%EA%B8%B0 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
