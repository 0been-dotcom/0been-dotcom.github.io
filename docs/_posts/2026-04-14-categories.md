---
layout: single
title: "Jekyll 블로그 카테고리 설정하는 법"
date: 2026-04-14
categories: Jekyll블로그
author_profile: false
share: false
---

Jekyll 블로그에서 카테고리는
글을 주제별로 묶어주는 역할을 한다.

방문자 입장에서
같은 주제의 글을 한 번에 찾을 수 있어서
카테고리가 잘 정리되어 있으면
블로그 체류 시간이 늘어난다.

설정하는 방법을 정리해봤다.

---

Jekyll에서 카테고리를 지정하는 방법은 간단하다.

글 파일 상단 front matter 에
categories 항목을 추가하면 된다.

---
layout: single
title: "글 제목"
date: 2026-04-15
categories: Jekyll블로그
---

이렇게 설정하면
이 글은 Jekyll블로그 카테고리에 속하게 된다.

카테고리를 여러 개 지정하고 싶다면
대괄호로 묶어서 쓰면 된다.

categories: [Jekyll블로그, 개발]

---

카테고리 이름에 띄어쓰기가 있으면
두 개의 카테고리로 인식된다.

예를 들어
categories: Jekyll 블로그

이렇게 쓰면
Jekyll 과 블로그 가 각각 별개의 카테고리로 처리된다.

하나의 카테고리로 쓰려면
띄어쓰기 없이 붙여쓰거나
Jekyll블로그 이런 식으로 붙여쓰면 된다.

---

카테고리 목록 페이지를 만들려면
별도의 페이지 파일이 필요하다.

docs 폴더
-> _pages 폴더
-> category-archive.md 파일을 만들면 된다.

파일 내용은 이렇게 작성한다.

---
title: "카테고리"
layout: categories
permalink: /categories/
author_profile: false
---

이 파일을 만들고 나면
블로그주소/categories/ 로 접속했을 때
카테고리별로 글 목록이 표시된다.

---

상단 메뉴에 카테고리 페이지를 추가하고 싶다면
docs -> _data -> navigation.yml 파일을 열어서

main 항목 아래에 추가하면 된다.

main:
  - title: "About"
    url: /about/
  - title: "카테고리"
    url: /categories/

---

Minimal Mistakes 테마는
카테고리 아카이브 레이아웃을 기본으로 제공한다.

layout: categories 를 지정하면
카테고리별로 글이 자동으로 묶여서 표시된다.

별도로 카테고리마다 페이지를 만들 필요 없이
하나의 페이지에서 전체 카테고리를 볼 수 있어서 편하다.

---

태그도 카테고리와 비슷한 방식으로 쓸 수 있다.

front matter 에 tags 항목을 추가하면 된다.

tags: [Jekyll, 블로그, GitHub]

카테고리가 큰 주제를 묶는 용도라면
태그는 세부 키워드를 지정하는 용도로 쓰는 경우가 많다.

태그 목록 페이지도 카테고리와 같은 방식으로 만들 수 있다.

_pages 폴더에 tag-archive.md 파일을 만들고
layout: tags 를 지정하면 된다.

---

카테고리와 태그를 잘 활용하면
글이 많아질수록 블로그 구조가 정리된다.

처음부터 카테고리 체계를 잡아두면
나중에 글이 늘어났을 때
관리하기 훨씬 수월하다.
