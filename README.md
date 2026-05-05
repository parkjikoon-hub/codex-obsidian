# Codex Obsidian

Obsidian 안에서 OpenAI GPT와 대화하고, 노트를 분석·저장하는 KNOT 플러그인입니다.  
[codexian](https://github.com/reallygood83/codexian) 오픈소스를 기반으로 KNOT 생태계에 맞게 확장했습니다.

![version](https://img.shields.io/badge/version-1.1.0-blue)
![obsidian](https://img.shields.io/badge/Obsidian-1.0.0+-purple)
![license](https://img.shields.io/badge/license-MIT-green)

---

## KNOT란?

> **K**now · **N**ote · **O**utput · **T**ransform

지식을 **알고(Know)** → **기록하고(Note)** → **산출하고(Output)** → **변환한다(Transform)**

KNOT는 단순한 노트 도구가 아닌, 지식이 행동으로 이어지는 흐름을 만드는 플러그인 생태계입니다.  
매듭(Knot)처럼 흩어진 생각과 대화를 단단하게 엮어 하나의 지식으로 만들어줍니다.

---

## 주요 기능

| 기능 | 설명 |
|------|------|
| 💬 **GPT 채팅 사이드바** | Obsidian 오른쪽 패널에서 GPT와 실시간 대화 |
| 🗺️ **Memory Map** | BM25 알고리즘으로 관련 노트를 로컬에서 탐색 (API 비용 0원) |
| 📌 **핀 노트 영구 저장** | 재시작 후에도 핀 고정 노트 유지 |
| ⚡ **슬래시(/) 커맨드** | `/분석` `/코드` `/기획서` 등 입력창에서 빠른 명령 실행 |
| ⏱️ **작업 타임라인** | AI 응답 중 진행 단계 실시간 표시 |
| 📎 **노트 컨텍스트 자동 전달** | 현재 열린 노트를 GPT에게 자동 전달 |
| 💾 **노트 자동 생성** | 대화 내용을 KNOT 프론트매터가 포함된 노트로 저장 |
| 🧠 **Reasoning Effort** | Minimum / Low / Medium / High / Ultra High 사고 강도 선택 |
| ⏹ **스트리밍 중지** | 생성 중 언제든지 중지 가능 |
| 💻 **Codex CLI 연동** | Codex CLI 설치 시 로컬 에이전트로 동작 (선택 사항) |

---

## 슬래시(/) 커맨드 목록

입력창에 `/`를 입력하면 커맨드 메뉴가 열립니다.

| 커맨드 | 동작 |
|--------|------|
| `/분석` | 현재 노트 핵심 분석 + 개선점 제안 |
| `/요약` | 현재 노트 핵심 요약 |
| `/코드` | 노트 내용 기반 코드/스크립트 생성 |
| `/기획서` | 대화를 기획서 형식으로 변환 |
| `/회의록` | 대화를 회의록으로 정리 |
| `/저장` | 대화를 옵시디언 노트로 저장 |
| `/액션` | 할 일 체크리스트 추출 |
| `/초기화` | 대화 초기화 |

---

## Memory Map 사용법

1. 패널 상단 **"구축"** 클릭 → 볼트 전체 노트 색인 생성
2. 노트를 열고 **"관련 노트 찾기"** 클릭 → 관련 노트 최대 8개 추천
3. 추천 결과의 📌 버튼으로 바로 핀 고정 가능
4. **"재구축"** 으로 새 노트 추가 후 색인 갱신

> Memory Map은 완전히 로컬에서 동작합니다. API 호출 없이 무료로 사용할 수 있습니다.

---

## 사전 준비

### OpenAI API 키 발급

1. [OpenAI Platform](https://platform.openai.com/api-keys) 접속
2. **"Create new secret key"** 클릭
3. 발급된 키 복사 (`sk-...` 형태)
4. 플러그인 설정에서 **OpenAI API 키** 칸에 입력

### Codex CLI 설치 (선택 사항)

API 키만으로도 완전히 동작합니다. Codex CLI는 로컬 에이전트 모드를 원할 때만 필요합니다.

```bash
npm install -g @openai/codex@latest
codex --version  # 설치 확인
```

---

## 설치 방법

### 직접 설치 (권장)

1. 이 저장소에서 파일 3개 다운로드:
   - `main.js`
   - `manifest.json`
   - `styles.css`

2. 옵시디언 볼트 폴더에 복사:
   ```
   <볼트 경로>/.obsidian/plugins/codex-obsidian/
   ```

3. 옵시디언 재시작 → **설정 → 커뮤니티 플러그인 → Codex Obsidian** 활성화

4. **설정 → Codex Obsidian → OpenAI API 키** 입력

### Git 클론으로 설치

```bash
cd <볼트 경로>/.obsidian/plugins/
git clone https://github.com/parkjikoon-hub/codex-obsidian
```

---

## 사용 방법

### 패널 열기
- 왼쪽 사이드바의 **💻 터미널 아이콘** 클릭
- 또는 `Ctrl+P` → `Codex Obsidian 패널 열기`

### 메시지 전송
- `Enter`: 메시지 전송
- `Shift+Enter` / `Ctrl+Enter`: 줄바꿈
- `/`: 슬래시 커맨드 메뉴 열기

### 승인 모드 (Codex CLI 사용 시)

| 모드 | 설명 |
|------|------|
| 제안 모드 | 명령 실행 전 확인 요청 (안전) |
| 자동 모드 | 안전한 명령 자동 실행 |
| 전체 자동 | 모든 명령 자동 실행 |

### 노트 자동 저장
채팅창에서 다음 키워드를 포함하면 자동으로 노트가 생성됩니다:
- "저장해줘", "노트로 저장", "파일로 만들어", "기획서로", "회의록으로"

---

## 지원 모델

| 모델 | 특징 |
|------|------|
| GPT 5.3 | 빠른 응답 |
| GPT 5.4 | 균형 잡힌 성능 (추천) |
| GPT 5.5 | 최고 성능 |

---

## KNOT 플러그인 생태계

| 플러그인 | AI | 저장소 |
|----------|-----|--------|
| **Claude Obsidian** | Anthropic Claude | [parkjikoon-hub/claude-obsidian](https://github.com/parkjikoon-hub/claude-obsidian) |
| **Gemini Obsidian** | Google Gemini | [parkjikoon-hub/gemini-obsidian](https://github.com/parkjikoon-hub/gemini-obsidian) |
| **Codex Obsidian** | OpenAI GPT | [parkjikoon-hub/codex-obsidian](https://github.com/parkjikoon-hub/codex-obsidian) |

---

## 개인정보 보호

- API 키는 옵시디언 로컬 설정에만 저장됩니다.
- 대화 내용은 OpenAI API로만 전송됩니다.
- Memory Map 색인은 볼트 내 로컬 파일(`.codex-obsidian/memory/`)에 저장됩니다.

---

## 관련 프로젝트

- [gemini-obsidian](https://github.com/parkjikoon-hub/gemini-obsidian) — Gemini AI 버전
- [claude-obsidian](https://github.com/parkjikoon-hub/claude-obsidian) — Claude AI 버전
- [codexian](https://github.com/reallygood83/codexian) — 원본 오픈소스 (감사합니다!)

---

## 라이선스

MIT License

---

Made with ❤️ by [KNOT](https://github.com/parkjikoon-hub)
