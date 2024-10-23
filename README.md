# manatoki
마나토끼 바로가기

https://마나토끼.store/, https://www.newtoki.info/ 등 주소 안내 페이지에서 실시간 마나토끼 주소로 리다이렉트 합니다.

## 설치 방법
**Tampermonkey 설치**

  Chrome 또는 Firefox에서 Tampermonkey 확장 프로그램을 설치합니다.
  
  Tampermonkey가 활성화되었는지 확인합니다.

**스크립트 추가**

  브라우저 우측 상단 확장 기능 (퍼즐모양) 을 클릭합니다.
  
  Tampermonkey를 클릭합니다. 
  
  새 스크립트 만들기... 버튼을 클릭합니다.
  
  원래 코드를 모두 지우고 아래 코드를 복사하여 붙여 넣습니다:

```
// ==UserScript==
// @name         manatoki
// @namespace    http://tampermonkey.net/
// @version      2024-02-12
// @description  redirect to manatoki.net
// @author       You
// @match        https://xn--h10b2b940bwzy.store/*
// @icon         data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==
// @grant        none
// ==/UserScript==

(function() {
  // 1. 추출할 텍스트
  const desiredText = "manatoki";

  // 2. URL 추출
  const allLinks = document.querySelectorAll("a");
  const urls = [];
  for (const link of allLinks) {
    urls.push(link.href);
  }

  // 3. 텍스트가 포함된 URL 찾기
  const redirectUrl = urls.find((url) => url.includes(desiredText));

  // 4. 리다이렉트
  if (redirectUrl) {
    window.location.href = redirectUrl;
  }
})();
```
 파일 > 저장을 클릭하여 스크립트를 저장하고 활성화합니다.
 Tampermonkey 대시보드에서 활성화되었는지 확인합니다.

## 뉴토끼 바로가기

```
// ==UserScript==
// @name         newtoki
// @namespace    http://tampermonkey.net/
// @version      2024-02-12
// @description  redirect to newtoki.com
// @author       You
// @match        https://xn--h10b90b998c.site/*
// @icon         data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==
// @grant        none
// ==/UserScript==

(function() {
  // 1. 추출할 텍스트
  const desiredText = "newtoki";

  // 2. URL 추출
  const allLinks = document.querySelectorAll("a");
  const urls = [];
  for (const link of allLinks) {
    urls.push(link.href);
  }

  // 3. 텍스트가 포함된 URL 찾기
  const redirectUrl = urls.find((url) => url.includes(desiredText));

  // 4. 리다이렉트
  if (redirectUrl) {
    window.location.href = redirectUrl;
  }
})();
```

## 주소 안내 페이지 URL 변경

  @match 부분을 수정합니다. URL에 한글이 포함될 경우 Punycode 형식으로 변환해야 합니다. 
  [Punycode 변환기](https://www.punycoder.com/)
