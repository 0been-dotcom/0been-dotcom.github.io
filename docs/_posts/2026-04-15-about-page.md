---
layout: single
title: "Jekyll 블로그 About 페이지 만드는 법"
date: 2026-04-15
categories: Jekyll블로그
author_profile: false
share: false
---

Jekyll 블로그를 만들고 나면
About 페이지가 기본으로 들어있다.

그런데 기본 About 페이지는
Minimal Mistakes 테마 제작자 Michael Rose 의
샘플 내용이 들어있다.

그대로 두면 방문자가 봤을 때
완성된 블로그처럼 보이지 않아서
빠르게 바꾸는 게 낫다.

---

About 페이지 파일 위치는 여기다.

docs 폴더
-> _pages 폴더
-> about.md 파일

파일을 열면 상단에 front matter 가 있고
아래에 본문 내용이 있다.

front matter 는 이런 형태로 되어있다.

---
permalink: /about/
title: "About"
---

permalink 는 이 페이지의 URL 이다.
/about/ 로 되어있으면
블로그주소/about/ 으로 접속할 수 있다.

title 은 페이지 상단에 표시되는 제목이다.

---

수정 방법은 간단하다.

GitHub 저장소
-> docs -> _pages -> about.md 클릭
-> 연필 아이콘 클릭

front matter 아래 본문 부분을
원하는 내용으로 바꾸면 된다.

마크다운 형식으로 작성할 수 있어서
줄바꿈, 굵게, 링크 같은 서식을 쓸 수 있다.

수정 후 Commit changes 를 누르면 된다.

---

About 페이지에 뭘 써야 할지
처음엔 막막할 수 있다.

너무 많이 쓸 필요는 없다.

블로그가 어떤 내용을 담는지,
어떤 사람이 운영하는지
짧게 적는 것만으로 충분하다.

거창하게 쓰려고 하면
오히려 쓰기가 어려워진다.

---

한 가지 주의할 점이 있다.

기본 about.md 파일 안에
샘플 글을 참조하는 코드가 들어있는 경우가 있다.

이 코드가 남아있으면
빌드할 때 해당 샘플 글을 찾지 못해서
오류가 발생한다.

about.md 파일 내용을 전부 지우고
front matter 와 새 본문만 남기면 해결된다.

---

터미널에서 수정하는 방법도 있다.

저장소를 로컬에 clone 한 상태라면
docs/_pages/about.md 파일을 직접 열어서 수정하고
git add, git commit, git push 순서로 올리면 된다.

---

About 페이지를 바꾸고 나면
블로그가 한결 완성된 느낌이 난다.

방문자가 상단 메뉴에서 About 을 클릭했을 때
블로그 소개 글이 나오면
그것만으로도 충분히 운영 중인 블로그처럼 보인다.
