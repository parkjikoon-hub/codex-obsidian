# Codex Obsidian

Obsidian 안에서 OpenAI GPT와 대화하고, 노트를 분석·저장하는 KNOT 플러그인입니다.

![version](https://img.shields.io/badge/version-1.3.0-blue)
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
| 📌 **핀 노트 영구 저장** | 재시작 후에도 핀 고정 노트 유지 |
| ⚡ **슬래시(/) 커맨드** | `/분석` `/코드` `/기획서` 등 입력창에서 빠른 명령 실행 |
| ⏱️ **작업 타임라인** | AI 응답 중 진행 단계 실시간 표시 |
| 📄 **노트 컨텍스트 토글** | 현재 열린 노트를 GPT에게 전달 (버튼으로 켜기/끄기) |
| 🌐 **웹 검색 토글** | 실시간 웹 검색으로 최신 정보 활용 (버튼으로 켜기/끄기) |
| 💾 **노트 자동 생성** | 대화 내용을 KNOT 프론트매터가 포함된 노트로 저장 |
| 🧠 **Reasoning Effort** | Minimum / Low / Medium / High / Ultra High 사고 강도 선택 |
| 🔄 **재생성** | AI 응답이 마음에 안 들면 같은 질문으로 다시 생성 |
| ✏️ **메시지 편집** | 이전에 보낸 메시지를 수정하면 그 이후 대화 자동 재시작 |
| ⏹️ **중단 후 텍스트 보존** | Esc로 중단해도 받은 내용은 저장됨 |
| 📏 **히스토리 자동 관리** | 대화가 길어지면 오래된 내용을 자동으로 정리해 토큰 초과 방지 |

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

## 사전 준비

### OpenAI API 키 발급

1. [OpenAI Platform](https://platform.openai.com/api-keys) 접속
2. **"Create new secret key"** 클릭
3. 발급된 키 복사 (`sk-...` 형태)
4. 플러그인 설정에서 **OpenAI API 키** 칸에 입력

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

### KNOT Starter Vault 사용 (추천)

KNOT Vault를 통째로 설치하면 3개 플러그인이 모두 포함되어 있습니다.

```bash
git clone https://github.com/parkjikoon-hub/knot-vault
```

---

## 사용 방법

### 패널 열기
- 왼쪽 사이드바의 **💻 터미널 아이콘** 클릭
- 또는 `Ctrl+P` → `Codex Obsidian 패널 열기`

### 키보드 단축키

| 키 | 동작 |
|----|------|
| `Enter` | 메시지 전송 |
| `Shift+Enter` / `Ctrl+Enter` | 줄바꿈 |
| `/` | 슬래시 커맨드 메뉴 열기 |
| `Esc` | 생성 중단 (받은 내용은 저장됨) |

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

---

## 라이선스

MIT License

---

Made with ❤️ by [KNOT](https://github.com/parkjikoon-hub)
