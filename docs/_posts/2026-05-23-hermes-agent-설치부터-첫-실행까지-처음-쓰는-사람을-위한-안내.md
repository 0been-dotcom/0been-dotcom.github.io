---
layout: single
title: "Hermes Agent 설치부터 첫 실행까지 — 처음 쓰는 사람을 위한 안내"
date: 2026-05-23
last_modified_at: 2026-05-23
categories: 사용법-가이드
tags: [hermes-agent, 설치, 명령어, 초보자, 가이드, "로컬 LLM", "AI 에이전트"]
description: "Hermes Agent 처음 설치하는 사람을 위한 단계별 가이드. 명령어 복사해서 바로 실행 가능. Mac, Linux 환경 기준. 로컬 모델(Carnice, Ollama) 연결 방법 포함."
excerpt: "Hermes Agent 처음 설치하는 사람을 위한 단계별 가이드. 명령어 복사해서 바로 실행 가능. Mac, Linux 환경 기준. 로컬 모델(Carnice, Ollama) 연결 방법 포함."
author_profile: false
share: true
toc: true
toc_label: "목차"
toc_sticky: true
---

처음 봤을 때 솔직히 몰랐다.

터미널을 켜라, 모델을 연결하라, 컨텍스트 창을 설정하라 — 익숙하지 않은 사람한테는 막막한 말들이다. ChatGPT나 Claude처럼 웹에서 쓰는 게 아니라는 것도 처음엔 낯설다.

이 글은 그 막막함을 없애기 위해 썼다. **명령어를 그대로 복사해서 붙여넣으면 된다.** 무슨 뜻인지 몰라도 일단 따라하면 동작한다.

<!-- 📸 스크린샷: 완성된 Hermes Agent 실행 화면
     저장 경로: docs/assets/images/posts/2026-05-23-hermes-guide-terminal.png -->
![Hermes Agent 터미널 실행 화면](/assets/images/posts/2026-05-23-hermes-guide-terminal.png)
*▲ 설치 완료 후 Hermes Agent 첫 실행 화면*

<div class="notice--info" markdown="1">
**📌 이 글의 대상**

- Hermes Agent가 처음인 사람
- 터미널 기초는 알지만 AI 에이전트는 처음인 사람
- 로컬에서 LLM을 돌려보고 싶은 사람
</div>

---

## 🛠️ 설치 전 확인

**필요한 것:**

```bash
# Node.js 설치 여부 확인 (v18 이상 필요)
node --version

# git 확인
git --version
```

Node.js가 없다면 [nodejs.org](https://nodejs.org) 에서 LTS 버전을 설치하세요.
macOS라면 Homebrew가 편합니다.

```bash
# macOS: Homebrew로 Node.js 설치
brew install node
```

---

## 📦 설치

```bash
npm install -g hermes-agent
```

설치 후 버전 확인:

```bash
hermes --version
```

에러가 나면 Node.js 버전이 v18 미만인 경우가 많습니다.
`node --version` 으로 확인 후 업그레이드하세요.

---

## ▶️ 처음 실행

```bash
# 새 세션 시작
hermes

# 이전 대화 이어서
hermes -c

# 저장된 세션 이름으로 재개
hermes -r "세션이름"
```

처음 실행하면 모델을 선택하라고 나옵니다.

| 선택 | 특징 | 추천 대상 |
|------|------|-----------|
| OpenRouter | 클라우드 모델, 무료 티어 있음 | 처음 시작하는 사람 |
| 로컬 모델 (llama.cpp) | 인터넷 없이, 비용 없이 | 16GB RAM 이상 보유자 |

무료로 시작하려면 **OpenRouter** 를 선택하세요.
[openrouter.ai](https://openrouter.ai) 에서 계정 만들면 API 키를 받을 수 있습니다.

---

## 🏠 로컬 모델 연결 (선택)

인터넷 없이, 비용 없이 쓰고 싶다면 로컬 모델을 연결합니다.
Mac M 시리즈나 고성능 PC에서 권장합니다.

```bash
# 별도 터미널에서 llama-server 실행
llama-server \
  -m ~/.ollama/models/blobs/[모델파일해시] \
  --port 8080 \
  -ngl 99 \
  --flash-attn on \
  -c 8192

# Hermes에서 로컬 모델 선택
hermes /model
# → Custom OpenAI-Compatible 선택
# → Base URL: http://localhost:8080/v1
# → Model: 아무 이름 입력 (ex: carnice)
```

<!-- 📸 스크린샷: 로컬 모델 연결 설정 화면
     저장 경로: docs/assets/images/posts/2026-05-23-hermes-guide-local-model.png -->
![로컬 모델 연결 설정 화면](/assets/images/posts/2026-05-23-hermes-guide-local-model.png)
*▲ 로컬 llama-server 연결 설정 예시*

---

## ⚙️ 자주 쓰는 명령어

이것들만 알아도 일단 쓸 수 있습니다.

| 명령어 | 언제 쓰나 |
|--------|-----------|
| `/compress` | 대화가 길어져서 느려질 때 |
| `/model` | 더 빠른/좋은 모델로 바꾸고 싶을 때 |
| `/usage` | 토큰 얼마나 썼는지 볼 때 |
| `/new` | 완전히 새로 시작할 때 |
| `/memory` | 에이전트가 뭘 기억하는지 볼 때 |
| `/stop` | 실행 중인 작업 중단 |
| `/skills` | 설치된 스킬 목록 보기 |

```bash
# 세션 내부 명령어 (대화 중에 입력)
/compress    # 대화 압축 → 속도 회복
/usage       # 토큰 사용량 확인
/model       # 모델 변경
/new         # 완전히 새 세션
/stop        # 긴 작업 중단
```

---

## 💡 처음에 시도해볼 것들

```bash
# 파일 요약 시키기
"이 파일 요약해줘: ~/Documents/report.txt"

# 코드 설명 요청
"이 파이썬 코드 설명해줘"
# (코드를 붙여넣기)

# 안전한 첫 번째 실습 — 계획 먼저 보기
"~/Downloads 폴더 정리 계획 세워줘. 실행은 하지 말고 계획만 먼저 보여줘."
```

마지막 예시처럼 **"실행은 하지 말고 계획만 먼저 보여줘"** 를 붙이는 게 중요합니다.
Hermes는 바로 실행하려는 성향이 있어서, 처음엔 계획을 먼저 확인하는 습관을 들이는 게 좋습니다.

---

## 💬 직접 써보니까

<!-- Carnice야: 아래 질문들에 답하는 형식으로 채워줘.
각 2-3문장. 확실하지 않으면 "(확인 필요)".
개인 직업/신상 정보는 절대 언급하지 마. 기술 경험만 써.
- 설치 과정에서 막혔던 부분이 있었나요?
- 처음 실행했을 때 가장 놀랐던 점은?
- 초보자가 가장 많이 헷갈리는 부분은 어디인가요?
- Mac mini M4 Pro 환경에서 특이한 점이 있었나요?
- 추천하는 첫 번째 실습 과제는?
-->

> **[이 섹션은 실제 사용 경험으로 채워주세요]**
> Mac mini M4 Pro (48GB) + Carnice-V2-27B Q4 환경 기준.

---

## ❓ 자주 묻는 것들

**Q. ChatGPT, Claude랑 어떻게 다른가요?**

A. ChatGPT/Claude는 웹 인터페이스 위주이고, Hermes Agent는 터미널에서 파일·코드·시스템을 직접 다루는 도구입니다. AI가 내 컴퓨터의 파일을 직접 만들고, 명령어를 실행하고, 검색을 대신 해줄 수 있습니다. 자동화에 초점을 맞춘 도구라고 보면 됩니다.

**Q. 유료인가요?**

A. Hermes Agent 자체는 오픈소스 무료입니다. OpenRouter 무료 티어로 시작할 수 있고, 로컬 모델을 쓰면 완전 무료입니다.

**Q. 한국어로 대화되나요?**

A. 됩니다. 단, 로컬 모델은 영어 기반이라 한국어 품질이 모델마다 다릅니다. Carnice-V2-27B 기준으로 한국어 지시는 이해하지만 응답은 어색할 수 있습니다. Claude API 연결 시 한국어 품질이 크게 올라갑니다.

**Q. Apple Silicon(M1/M2/M4)에서 잘 돌아가나요?**

A. 잘 됩니다. Metal GPU 가속이 지원되어 macOS 환경에서 좋은 성능을 냅니다. `-ngl 99` 플래그로 모든 레이어를 GPU에 올리면 더 빠릅니다.

---

## ➡️ 다음 단계

설치와 첫 실행이 됐다면 이걸 해보세요.

```bash
# 스킬 목록 보기 (자주 쓰는 작업 자동화)
hermes skills list

# 메모리 저장 (에이전트가 기억하게)
# 대화 중 입력:
# "이걸 기억해줘: 이 프로젝트는 항상 Python 3.11 사용"

# 텔레그램 연동 (폰에서 명령)
# → 별도 설정 필요, 이후 포스트에서 다룰 예정
```

막히는 부분이 있다면 댓글로 남겨주세요.

---

### 참고 소스
- [Hermes Agent v0.9 리뷰 가이드](https://www.heyuan110.com/posts/ai/2026-04-14-hermes-agent-guide/)
