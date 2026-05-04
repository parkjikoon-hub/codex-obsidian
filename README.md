# Codex Obsidian

OpenAI Codex CLI를 Obsidian 안에서 직접 사용하고, 대화 내용을 자동으로 노트로 생성하는 플러그인입니다.
[codexian](https://github.com/reallygood83/codexian) 오픈소스를 기반으로 obsidian-skill 통합, 노트 자동 저장 등 더 강력한 기능을 추가했습니다.

![version](https://img.shields.io/badge/version-1.0.0-blue)
![obsidian](https://img.shields.io/badge/Obsidian-0.15.0+-purple)
![license](https://img.shields.io/badge/license-MIT-green)

---

## codexian과의 차이점

| 기능 | codexian | Codex Obsidian |
|------|----------|----------------|
| Codex CLI 연동 | ✅ | ✅ 더 안정적 |
| 현재 노트 컨텍스트 | ✅ | ✅ |
| 관련 노트 검색 (CLI) | 기초적 | ✅ Obsidian CLI 기반 |
| 노트 자동 저장 | ❌ | ✅ CMDS 프론트매터 포함 |
| 기획서/회의록 변환 | ❌ | ✅ 툴바 버튼 |
| BRAT 없이 설치 | ❌ | ✅ 직접 설치 가능 |
| pencil MCP 에러 | ❌ 에러 발생 | ✅ 없음 |

---

## 주요 기능

| 기능 | 설명 |
|------|------|
| 💻 **Codex 채팅 사이드바** | Obsidian 안에서 Codex와 실시간 대화 |
| 📎 **노트 컨텍스트 자동 전달** | 현재 열린 노트를 Codex에게 자동 전달 |
| 🔍 **관련 노트 검색** | Obsidian CLI로 관련 노트를 찾아 컨텍스트에 추가 |
| 💾 **노트 자동 생성** | 대화 내용을 CMDS 프론트매터가 포함된 노트로 저장 |
| 📋 **빠른 변환 툴바** | 기획서, 회의록, 액션 아이템, 코드 생성 버튼 |
| ⏹ **스트리밍 중지** | 생성 중 언제든지 중지 가능 |
| ⚙️ **승인 모드** | 제안/자동/전체 자동 모드 선택 |

---

## 필수 요구사항

1. **Obsidian** 0.15.0 이상 (데스크톱)
2. **Node.js** 20 이상
3. **Codex CLI** (OpenAI 계정 필요)
4. **Obsidian CLI** v1.12+ (선택 — 관련 노트 검색 기능)

---

## 설치 방법

### Codex CLI 먼저 설치

```bash
npm install -g @openai/codex@latest
codex --version  # 설치 확인
```

OpenAI 계정으로 로그인:
```bash
codex auth
```

### 플러그인 설치

1. 이 저장소에서 파일 3개 다운로드:
   - `main.js`
   - `manifest.json`
   - `styles.css`

2. 옵시디언 볼트 폴더에 복사:
   ```
   <볼트 경로>/.obsidian/plugins/codex-obsidian/
   ```

3. 옵시디언 재시작 → **설정 → 커뮤니티 플러그인 → Codex Obsidian** 활성화

### Git 클론으로 설치

```bash
cd <볼트 경로>/.obsidian/plugins/
git clone https://github.com/cmds-hub/codex-obsidian
```

---

## 사용 방법

### 패널 열기
- 왼쪽 사이드바의 **💻 터미널 아이콘** 클릭
- 또는 `Ctrl+P` → `Codex Obsidian 패널 열기`

### 빠른 명령 (툴바)
- **📄 현재 노트 분석**: 열린 노트를 분석하고 개선점 제안
- **🔍 관련 노트 검색**: Obsidian CLI로 관련 노트 검색 후 컨텍스트 추가
- **💻 코드 생성**: 노트 내용 기반 코드/스크립트 생성
- **📋 기획서 변환**: 대화를 기획서로 정리
- **📝 회의록 작성**: 대화를 회의록으로 정리
- **💾 노트 저장**: 대화 전체를 노트로 저장
- **⏹ 중지**: 현재 생성 중지
- **🔄 초기화**: 새 대화 시작

### 승인 모드
| 모드 | 설명 |
|------|------|
| 제안 모드 | 명령 실행 전 확인 요청 (안전) |
| 자동 모드 | 안전한 명령 자동 실행 |
| 전체 자동 | 모든 명령 자동 실행 |

---

## Obsidian CLI 연동 (obsidian-skill)

Obsidian CLI가 설치되어 있으면 추가 기능이 활성화됩니다:

- **스마트 노트 검색**: 현재 주제와 관련된 노트를 볼트 전체에서 검색
- **CLI 기반 노트 저장**: CMDS 프론트매터가 완벽하게 포함된 노트 생성
- **플러그인 리로드**: 설정에서 버튼 하나로 즉시 리로드

Obsidian CLI 설치: https://help.obsidian.md/cli

---

## 파일 구조

```
codex-obsidian/
├── main.js          ← 플러그인 핵심 로직
├── manifest.json    ← 플러그인 메타데이터
├── styles.css       ← UI 스타일
├── package.json     ← 프로젝트 정보
└── README.md        ← 이 파일
```

---

## 개인정보 보호

- Codex CLI는 로컬에서 실행됩니다.
- 대화 내용은 OpenAI API를 통해 처리됩니다.
- API 키는 OpenAI CLI 인증을 통해 안전하게 관리됩니다.

---

## 라이선스

MIT License

---

## 관련 프로젝트

- [gemini-obsidian](https://github.com/cmds-hub/gemini-obsidian) — Gemini AI 버전
- [codexian](https://github.com/reallygood83/codexian) — 원본 오픈소스 (감사합니다!)

---

Made with ❤️ by [CMDS](https://github.com/cmds-hub)
