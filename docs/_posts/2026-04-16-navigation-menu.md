---
layout: single
title: "Jekyll 블로그 상단 메뉴 직접 수정한 방법"
date: 2026-04-16
categories: Jekyll블로그
author_profile: false
share: false
---

Jekyll 블로그를 처음 만들면
상단 메뉴에 Quick-Start Guide, Sample Posts,
Sample Collections, Terms & Privacy Policy 같은
항목들이 기본으로 들어있다.

전부 Minimal Mistakes 테마 샘플 메뉴들이라
그대로 두면 방문자 입장에서 어색하다.

내 블로그에 맞게 바꾸는 방법을 정리해봤다.

---

상단 메뉴는 _config.yml 이 아니라
별도의 파일에서 관리한다.

docs 폴더
-> _data 폴더
-> navigation.yml 파일

이 파일을 열면 여러 섹션이 있는데
그 중 main 항목이 상단 메뉴를 담당한다.

기본 구조는 이런 형태다.

main:
  - title: "Quick-Start Guide"
    url: /docs/quick-start-guide/
  - title: "About"
    url: /about/
  - title: "Sample Posts"
    url: /year-archive/

title 은 메뉴에 표시되는 이름이고
url 은 클릭했을 때 이동할 주소다.

---

수정하는 방법은 간단하다.

GitHub 저장소
-> docs -> _data -> navigation.yml 클릭
-> 연필 아이콘 클릭

main 항목 아래에 있는 내용 중
필요 없는 메뉴는 통째로 지우면 된다.

예를 들어 About 메뉴만 남기고 싶다면
나머지 항목을 전부 지우고
이렇게만 남기면 된다.

main:
  - title: "About"
    url: /about/

저장 후 Commit changes 를 누르면
빌드가 완료된 뒤 상단 메뉴가 바뀐다.

---

새 메뉴를 추가하고 싶을 때도
같은 방식으로 항목을 추가하면 된다.

예를 들어 카테고리 페이지로 이동하는 메뉴를 만들고 싶다면

main:
  - title: "About"
    url: /about/
  - title: "카테고리"
    url: /categories/

이렇게 추가하면 된다.

url 에 외부 링크를 넣어도 된다.

- title: "GitHub"
  url: https://github.com/아이디

이런 식으로 외부 사이트로 연결되는 메뉴도 만들 수 있다.

---

터미널에서 수정하는 방법도 있다.

저장소를 로컬에 clone 한 상태라면
docs/_data/navigation.yml 파일을 직접 열어서 수정하고
git add, git commit, git push 순서로 올리면 된다.

---

주의할 점이 하나 있다.

navigation.yml 파일은 YAML 형식이라
들여쓰기가 맞지 않으면 빌드가 실패한다.

각 항목 앞의 - 기호와
title, url 앞의 공백 개수가
일정하게 맞아야 한다.

수정 후 빌드 오류가 뜬다면
저장소
-> Actions 탭
-> 가장 최근 빌드 클릭

로그에서 오류 위치를 확인하면 된다.

대부분 들여쓰기 문제라
파일을 다시 열어서 공백을 맞춰주면 해결됐다.

---

메뉴를 바꾸고 나면
블로그가 훨씬 깔끔해 보였다.

샘플 메뉴가 그대로 남아있을 때는
방문자 입장에서 완성된 블로그처럼 보이지 않았는데
필요한 것만 남기고 나니 달랐다.
