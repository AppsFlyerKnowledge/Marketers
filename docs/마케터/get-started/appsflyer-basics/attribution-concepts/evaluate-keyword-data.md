---
title: 키워드 데이터
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-07-25T08:19:25Z'
  edited_at: '2026-10-14T10:37:02Z'
  id: 17255366785553
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/17255366785553
---
> **한눈에 보기:** 자세한 키워드 데이터를 얻어 가장 인기 있는 검색어를 확인하고 유기적 전환을 최적화할 수 있습니다.

<div id="keyword-data" />

## 키워드 데이터

유기적 검색은 귀하의 앱에 대한 귀중한 트래픽 소스입니다. 유기적 사용자들은 인수 비용이 발생하지 않으며, 일반적으로 가장 참여도가 높은 집단 중 하나입니다.

앱 페이지에 몇 가지 조정을 하면 새로운 유기적 설치 수를 늘릴 수 있습니다. 유기적인 검색을 최적화하려면 앱에 대한 유기적인 키워드 데이터를 얻어야 합니다.

<div id="ios-keywords" />

### iOS 키워드

Apple Search Ads와 함께 작업하면 Apple Search Ads에 귀속된 비유기적 사용자에 대한 자세한 키워드 데이터를 얻을 수 있습니다. iOS에서는 유기적 키워드 데이터가 제공되지 않습니다.

<div id="android-keywords" />

### 안드로이드 키워드

구글은 다음과 같은 사용자에게 리퍼러 URL에서 유기적 키워드 데이터를 공유합니다:

* 안드로이드 기기 사용
* 크롬 브라우저 사용
* Google.com을 방문하여 검색을 수행하세요.
* Google 검색 결과 페이지에서 앱 설치하기
* 앱 실행

SDK는 Google Play 링크의 일부인 경우 referrer의 &utm\_term 매개변수로 Google에서 제공된 키워드를 추출합니다. 가능한 값은 다음 AppsFlyer 원시 데이터 필드에 포함되어 있습니다: http\_referrer, gp\_broadcast\_referrer, keywords.

유기적인 안드로이드 사용자 중 1% 미만이 이 퍼널을 따르고 유기적인 키워드 데이터를 가지고 있을 것으로 예상합니다.

다른 시나리오에서는 Google이 유기적 키워드 데이터를 공유하지 않습니다. 예를 들어, Google Play에서 검색하는 사용자는 유기적 키워드 데이터가 없습니다.

<div id="note" />

> 📘 **참고사항**
>
> 이 제한은 모든 외부 공급업체, 모든 귀속 공급업체를 포함하여 Google에 의해 적용됩니다.

<div id="using-thekeyworddata" />

### 키워드 데이터를 사용하여

유기적 키워드 데이터는 다음에서 찾을 수 있습니다:

* 원시 유기 데이터 보고서  
  앱스플라이어에서 사이드 메뉴에서 보고서 > 원시 데이터 내보내기를 선택하여 사용된 유기적 키워드의 세부 정보를 확인합니다.
* 고급 보고서   
  피벗, 유지 및 코호트 보고서로 이동하여 키워드별로 그룹화합니다.  
  키워드를 기반으로 유기적 사용자 품질을 비교하십시오.
* 푸시 API 메시지

<div id="testing-organickeyworddata" />

### 유기적 키워드 데이터 테스트

1. 허용된 Android 기기를 사용하세요.
2. 크롬 브라우저를 열고 Google.com으로 이동하세요.
3. 앱을 검색할 때 강력한 키워드를 사용하세요.   
   이 예제는 "오늘 밤 호텔"을 사용합니다.  
     

   <Image align="center" alt="organic_keywords_search.jpg" src="https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg" width="426px" />
4. 설치를 클릭하면 Google Play 스토어로 리디렉션됩니다.
5. 앱을 설치하고 실행하세요.  

   <Image align="center" alt="Hotels_Tonight_3.png" src="https://files.readme.io/c455f8229ba7879157eec6782d0eb2d94a91e1080a3c081f5452cc7e92608047-205710046.png" width="373px" />
6. 위에 설명된 AppsFlyer 소스에서 키워드를 검색하세요.

<div data-zendesk-anchors="keyword-data=%ED%82%A4%EC%9B%8C%EB%93%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HKA1D1TW1R20X6K05Q9GX904=%ED%82%A4%EC%9B%8C%EB%93%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0 ios-keywords=ios-%ED%82%A4%EC%9B%8C%EB%93%9C h_01HKA1D1TW9YXBMGERHW4EHZZN=ios-%ED%82%A4%EC%9B%8C%EB%93%9C android-keywords=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%ED%82%A4%EC%9B%8C%EB%93%9C h_01HKA1D1TWT1VQ6NZ789BTCZJX=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%ED%82%A4%EC%9B%8C%EB%93%9C h_01HKA1D1TW7E2RM7SXC9R5SA99=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD using-the%C2%A0keyword%C2%A0data=%ED%82%A4%EC%9B%8C%EB%93%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC h_01HKA1D1TWRPGTNGJKF7T1R71B=%ED%82%A4%EC%9B%8C%EB%93%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC testing-organic%C2%A0keyword%C2%A0data=%EC%9C%A0%EA%B8%B0%EC%A0%81-%ED%82%A4%EC%9B%8C%EB%93%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HKA1D1TW5W9A72V2NMPX932H=%EC%9C%A0%EA%B8%B0%EC%A0%81-%ED%82%A4%EC%9B%8C%EB%93%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%85%8C%EC%8A%A4%ED%8A%B8" />
