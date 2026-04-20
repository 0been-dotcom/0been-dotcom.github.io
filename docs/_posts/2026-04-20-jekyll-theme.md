---
layout: single
title: "Jekyll 블로그 테마 고르는 법 - Minimal Mistakes 선택한 이유"
date: 2026-04-20
categories: Jekyll블로그
author_profile: false
share: false
---

Jekyll 블로그를 만들기로 했는데
가장 먼저 막힌 게 테마였다.

어디서 찾아야 하는지부터 몰랐다.

---

테마를 찾을 수 있는 곳은 몇 군데 있다.

가장 많이 쓰이는 곳은 jekyllthemes.io다.
무료 테마만 모아놓은 페이지도 따로 있어서
jekyllthemes.io/free 로 들어가면
비용 없이 쓸 수 있는 테마만 골라서 볼 수 있다.

github.com/topics/jekyll-theme 도 있다.
GitHub에서 직접 jekyll-theme 태그가 붙은
저장소들을 모아서 보여주는 페이지인데,
스타 수 기준으로 정렬하면
사람들이 많이 쓰는 테마 순서대로 볼 수 있다.

jamstackthemes.dev 는 Jekyll 외에
다른 정적 사이트 생성기 테마도 같이 보여주는데
미리보기가 잘 되어 있어서 눈으로 비교하기 편했다.

---

처음엔 예쁜 것 위주로 봤다.

근데 예쁜 테마는 대부분
설정이 복잡하거나 문서가 부실했다.

코딩을 잘 모르는 입장에서는
디자인보다 얼마나 손대기 쉬운가가 더 중요했다.

그래서 기준을 바꿨다.

결국 따진 건 세 가지였다.

공식 문서가 잘 되어 있는가.
GitHub 스타 수가 많은가.
GitHub Pages와 바로 연동이 되는가.

이 기준으로 좁히다 보니
Minimal Mistakes가 남았다.

---

Minimal Mistakes는
github.com/mmistakes/minimal-mistakes 에서 찾을 수 있다.

GitHub 스타가 1만 개가 넘고
공식 문서가 꽤 상세하게 정리되어 있다.

실제로 적용하는 방법은 간단하다.

저장소에 들어가서
오른쪽 상단 Fork 버튼을 누르면 된다.

Fork는 이 테마를 내 GitHub 계정으로 복사하는 것이다.

Fork 화면에서
저장소 이름을 본인 GitHub 아이디.github.io 형태로 바꾼다.

예를 들어 GitHub 아이디가 example이면
example.github.io 로 입력한다.

이렇게 하면 바로 블로그 주소가 만들어진다.

Create fork 버튼을 누르면 끝이다.

---

Fork가 완료되면
본인 GitHub 저장소에 테마 파일이 통째로 복사된다.

이 상태에서 Settings 탭으로 들어가
Pages 메뉴를 찾는다.

Branch 설정에서 master 또는 main을 선택하고
Save를 누르면
몇 분 안에 아이디.github.io 주소로 블로그가 열린다.

처음 열었을 때 Minimal Mistakes 테마 소개 페이지가 뜨는 건 정상이다.

블로그 형태로 바꾸려면
저장소 안에 있는 docs 폴더의 _config.yml 파일을 수정해야 한다.

url 항목에 본인 블로그 주소를 넣고
title 에 블로그 이름을 입력하면
새로고침 후 반영된다.

---

테마를 고르는 데 시간을 너무 쓰지 않는 게 나을 것 같다.

어떤 테마를 골라도
처음엔 뭔가 마음에 안 드는 부분이 생기게 되어 있다.

Minimal Mistakes를 고른 이유는 결국 하나였다.

막혔을 때 검색하면 해결책이 나왔다.

같은 문제를 겪은 사람의 글이 많다는 게
처음 시작하는 입장에서는 가장 중요한 기준이었다.
