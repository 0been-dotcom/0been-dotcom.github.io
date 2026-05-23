---
title: "Hermes Agent v0.14.0 Foundation 릴리스 — 180배 빠른 브라우저, SuperGrok 연동"
date: 2026-05-23 14:00 +0900
categories:
  - hermes-agent
tags:
  - automation
  - nousresearch
  - ai-agent
toc: true
---

## 도입

Nous Research가 2026년 5월 16일 Hermes Agent v0.14.0 'Foundation' 릴리스를 발표했다. v0.13.0 이후 808커밋, 633개 PR, 1393개 파일이 변경된 대형 업데이트다. 이번 릴리스의 핵심은 '어디서든 실행, 실제로 필요한 것만 탑재'다.

## 주요 변경 사항

### SuperGrok 연동 (xAI Grok OAuth)

SuperGrok 구독자는 xAI 계정 OAuth로 Grok을 Hermes 내부에서 바로 사용 가능하다. 별도의 API 키나 추가 청구가 필요 없다. grok-4.3 모델의 컨텍스트 윈도우가 **1M 토큰**으로 확대되어 전체 코드베이스나 연구 코퍼스를 단일 프롬프트에 넣을 수 있다.

### 브라우저 CDP 속도 180배 개선

브라우저 CDP 호출 속도가 180배 빨라졌다. 웹 스크래핑, 테스트 자동화, 브라우저 기반 에이전트 작업에서 체감 속도가 크게 향상된다.

### OpenAI 호환 로컬 프록시

`hermes proxy` 명령어로 로컬 OpenAI 호환 엔드포인트가 생성된다. Claude Pro, ChatGPT Pro, SuperGrok 등 OAuth 인증된 Hermes 제공자를 Codex, Aider, Cline, Continue 등 외부 도구에서 호출할 수 있다.

### 설치 최적화

- `pip install hermes-agent`로 PyPI에서 바로 설치
- 무거운 백엔드는 첫 사용 시 지연 설치 (lazy-install)
- 초기 시작 시간 약 19초 단축
- `[all]` 엑스트라에서 lazy-deps 중복 제거

### 신규 메시지 플랫폼 2개

LINE과 SimpleX Chat이 추가되어 총 **22개 플랫폼**을 지원하게 되었다.

## 정리

v0.14.0은 성능 최적화(브라우저 180배, 초기 시작 19초 절감), 설치 경량화, 그리고 SuperGrok 연동을 핵심으로 한 '기초 체질 개선' 릴리스다. 다중 플랫폼 연동과 외부 도구 호환성까지 확보하면서 일상 사용의 진입 장벽을 낮췄다.

## 출처

- [Hermes Agent Releases · GitHub](https://github.com/NousResearch/hermes-agent/releases)
- [Hermes Agent Documentation](https://hermes-agent.nousresearch.com/docs/)
