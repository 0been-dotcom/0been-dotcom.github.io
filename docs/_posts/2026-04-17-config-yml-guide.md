---
layout: single
title: "_config.yml 설정 완전 정리 - 블로그 이름부터 URL까지"
date: 2026-04-17
categories: Jekyll블로그
author_profile: false
share: false
---

Jekyll 블로그를 만들고 나서
가장 먼저 손대야 할 파일이 _config.yml 이다.

이 파일 하나에서
블로그 이름, 주소, 부제목, 저자 정보까지
거의 모든 기본 설정이 이루어진다.

Minimal Mistakes 테마를 Fork한 경우
_config.yml 파일이 두 곳에 있다.

저장소 루트의 _config.yml 과
docs 폴더 안의 _config.yml 이다.

실제 블로그 설정은
docs 폴더 안의 _config.yml 을 수정해야 한다.

루트의 _config.yml 을 수정해도
블로그에 반영되지 않아서 한참 헤맸다.

---

파일을 열면 항목이 많아서 처음엔 막막하다.

전부 다 건드릴 필요는 없고
우선 바꿔야 할 항목들만 정리하면 이렇다.

---

title 은 블로그 이름이다.

상단 로고 옆에 표시되는 이름이라
가장 눈에 띄는 부분이다.

title : "블로그 이름" 형태로 입력하면 된다.

---

subtitle 은 블로그 부제목이다.

title 바로 아래에 작게 표시된다.

없애고 싶으면 비워두거나
항목 자체를 주석 처리하면 된다.

---

name 항목은 좀 특이한 구조다.

파일 상단을 보면
name : &name "Michael Rose" 형태로 되어 있다.

&name 은 YAML 앵커라는 것인데
파일 다른 곳에서 *name 으로 참조하는 방식이다.

"Michael Rose" 부분만 원하는 이름으로 바꾸면
참조하는 다른 항목들도 자동으로 바뀐다.

---

url 은 실제 블로그 주소다.

https://아이디.github.io 형태로 입력한다.

이 항목이 잘못되어 있으면
CSS가 깨지거나 이미지가 안 보이는 문제가 생긴다.

---

baseurl 은 사용자 페이지 방식이면
비워두거나 "" 로 설정한다.

프로젝트 페이지 방식이라면
/저장소이름 을 입력해야 한다.

Minimal Mistakes Fork 방식으로 만든 블로그는
사용자 페이지 방식이라
baseurl 을 비워두면 된다.

---

locale 은 블로그 언어 설정이다.

기본값은 en 으로 되어 있는데
ko-KR 로 바꾸면 날짜 표시 형식 등이
한국어 기준으로 바뀐다.

---

footer 항목에서는 하단 SNS 링크를 설정할 수 있다.

기본으로 Twitter, GitHub, Instagram 링크가 들어있는데
links 항목을 비워두면 전부 사라진다.

footer:
  links: []

이렇게 설정하면 된다.

since 항목에는 블로그 시작 연도를 넣으면
하단에 저작권 표시와 함께 나온다.

---

defaults 항목에서는
모든 글에 적용할 기본값을 설정할 수 있다.

author_profile 을 false 로 설정하면
모든 글 페이지에서 프로필 사이드바가 사라진다.

share 를 false 로 설정하면
모든 글에서 SNS 공유 버튼이 사라진다.

글마다 개별로 설정하지 않아도
여기서 한 번에 처리할 수 있어서 편했다.

---

수정이 끝나면
GitHub에 커밋하고 푸시하면 된다.

저장소
-> docs -> _config.yml 파일 클릭
-> 연필 아이콘 클릭
-> 수정 후 Commit changes 클릭

터미널을 쓴다면
git add, git commit, git push 순서로 진행하면 된다.

변경 사항은 GitHub Actions 빌드가 완료된 후
보통 2~3분 안에 반영된다.

저장소
-> Actions 탭에서 배포 상태를 확인할 수 있다.

초록색 체크가 뜨면 완료된 것이다.
