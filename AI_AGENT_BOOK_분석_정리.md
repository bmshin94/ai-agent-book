# 📚 ai-agent-book 전수조사 분석 & 활용 전략 정리

> 작성: Claude Code (카리나 페르소나) · 작성일: 2026-10-07
> 대상 저장소: **[github.com/bmshin94/ai-agent-book](https://github.com/bmshin94/ai-agent-book)**
> 원본(upstream): **[github.com/bojieli/ai-agent-book](https://github.com/bojieli/ai-agent-book)**
> 라이선스: **Apache License 2.0** (상업적 이용 가능, 출처 표기 필요)

---

## 📑 목차

1. [저장소 정체 — 이게 뭐하는 건가](#1-저장소-정체)
2. [폴더별 전수조사 결과](#2-폴더별-전수조사-결과)
3. [쉽게 이해하기 — 비유와 구조](#3-쉽게-이해하기)
4. [7개 핵심 질문 답변](#4-7개-핵심-질문-답변)
5. [수익화 아이디어 10선](#5-수익화-아이디어-10선)
6. [실행 로드맵](#6-실행-로드맵)
7. [참고 링크 모음](#7-참고-링크-모음)

---

## 1. 저장소 정체

### 한 줄 요약

**『深入理解 AI Agent：设计原理与工程实践』**(깊이 있게 이해하는 AI 에이전트: 설계 원리와 엔지니어링 실무)
→ AI 에이전트 개발 **교과서 전문 + 실습 코드 109개 + Claude Code Skill 22개 + 강의 슬라이드 42강**이 통째로 담긴 오픈소스 책 저장소.

| 항목 | 내용 |
|---|---|
| 원작자 | Bojie Li (李博杰) |
| 원본 저장소 | https://github.com/bojieli/ai-agent-book |
| 포크 저장소 | https://github.com/bmshin94/ai-agent-book |
| 자매편 (AI Infra) | https://github.com/bojieli/ai-infra-book |
| 온라인 리더 | https://bojieli.github.io/ai-agent-book/astro/ |
| 라이선스 | Apache-2.0 |
| 핵심 공식 | `Agent = LLM + 컨텍스트(Context) + 도구(Tools)` |
| 책 버전 | 2.0 (1.4에서 챕터 재구성) |
| 규모 | 10장 · 실험 109개 · 15개 언어 · Skill 22개 · 강의 42강 |
| 실측 파일 수 | Python 1,763개 / Markdown 1,438개 / 통합 테스트 92개 |

### 핵심 철학

> **"모델(두뇌)은 다 비슷해졌다. 승부는 컨텍스트(눈)와 도구(손)에서 난다."**
> 모델 바깥의 모든 엔지니어링 역량 = **하네스(Harness) 엔지니어링**이 진짜 경쟁력.

> **"평가(Eval) 없이는 변화와 운을 구분할 수 없다."**
> 데모 성공 ≠ 신뢰성. 평가 체계가 아마추어와 프로를 가른다.

### 한국어 자료 (바로 쓸 수 있음)

| 자료 | 경로 / 링크 |
|---|---|
| 한국어 본문 | `book-ko/chapter1.ko.md` ~ `chapter10.ko.md` |
| 서문 / 후기 | `book-ko/introduction.ko.md`, `book-ko/afterword.ko.md` |
| 사고력 문제 모범답안 | `book-ko/reference-answers.ko.md` |
| 한국어 README | `docs/ko/README.md` |
| 한국어 학습 가이드 | `docs/ko/LEARNING.md` |
| 챕터별 한국어 실험 안내 | `chapter{1..10}/README.ko.md` |
| 한국어 PDF | https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-ko.pdf |
| 한국어 EPUB | https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-ko.epub |
| 번역 기여자 | [@JeongJaeSoon](https://github.com/JeongJaeSoon) |

---

## 2. 폴더별 전수조사 결과

### ① 책 본문 — 15개 언어

```
book/      ← 중국어 원본(정본)
book-ko/   ← 한국어
book-en/ book-es/ book-id/ book-ar/ book-zhtw/ book-ru/
book-ta/ book-vi/ book-ja/ book-tr/ book-hu/ book-he/ book-ptbr/
```
각 폴더에 `build_pdf.sh`, `preamble.tex`, `images/`, Lua 필터가 있어 직접 PDF 빌드 가능.
한국어판에는 `korean_spacing.lua` (한글 띄어쓰기 필터)까지 포함.

### ② 실습 코드 — `chapter1/` ~ `chapter10/` (109개 프로젝트)

| 장 | 주제 | 실험 수 | 대표 프로젝트 |
|:--:|---|:--:|---|
| 1 | 🚀 AI 에이전트 입문 | 4 | `context/`, `web-search-agent/`, `search-codegen/`, `image-gen-workflow/`, `learning-from-experience/` |
| 2 | 🎯 컨텍스트 엔지니어링 | 10 | `kv-cache/`, `context-compression/`, `prompt-engineering/`, `prompt-injection/`, `system-hint/`, `attention_visualization/`, `agent-skills-ppt/`, `local_llm_serving/` |
| 3 | 📚 유저 기억 & 지식베이스 | 12 | `user-memory/`, `mem0/`, `memobase/`, `retrieval-pipeline/`, `dense-embedding/`, `sparse-embedding/`, `contextual-retrieval/`, `agentic-rag/`, `structured-index/`, `knowledge 추출`, `log-sanitization/` |
| 4 | 🛠️ 도구 & MCP | 5 | `perception-tools/`, `execution-tools/`, `collaboration-tools/`, `active-tool-discovery/`, `active-tool-selection/`, `multimodal-agent/`, `DOCKER_DEPLOYMENT.md` |
| 5 | 💻 코딩 에이전트 & 범용 에이전트 | 16 | **`coding-agent/`**, `agent-creator/`, `paper-to-ppt/`, `paper-to-video/`, `video-edit/`, `erp-agent/`, `provider-failover/`, `code-for-math/`, `code-for-logic/`, `dynamic-form/`, `log-diagnosis/`, `adaptive-log-parser/`, `conversational-ui/`, `permission-embedded-data-objects/`, `small-model-codified-rules/`, `cad-vs-diffusion/` |
| 6 | 🎙️ 교류: 관찰·행동 공간 확장 | 14 | `async-agent/`, `agent-with-event-trigger/`, `astra-async-steering/`, `claude-computer-use-native/`, `computer-use-open-model/`, `phone-agent/`, `live-audio/`, `streaming-speech/`, `end-to-end-speech/`, `controllable-tts/`, `xlerobot-teleoperation/`, `gemini-xlerobot-navigation/`, `rgb-sim2real-grasping/` |
| 7 | 🎯 에이전트 평가 | 14 | `tau2-bench-eval/`, `model-benchmark/`, `elo-leaderboard/`, `agent-cost-analysis/`, `android-world/`, `model-action-threshold/`, `tts-quality-eval/`, `user-memory-policy-eval/`, `public-health-reporting-eval/`, `openvla-robotwin2-eval/` |
| 8 | 🧠 모델 후학습 | 19 | `RLVP/`, `retool/`, `premature-completion-dpo/`, `continued-pretraining/`, `cot-distillation/`, `prompt-distillation/`, `exact-copy-sft/`, `curly-quote-sft/`, `MiniMind-pretrain/`, `AdaptThink/`, `Intuitor/`, `AWorld-train/`, `SimpleVLA-RL/`, `SpatialReasoning/`, `MultilingualReasoning/`, `orpheus/`, `sesame/`, `speech-sft-experiment/` |
| 9 | 🔄 에이전트의 지속 진화 | 9 | `self-evolving-tools/`, `self-modifying-agent/`, `self-evolution-eval/`, `hermes-self-evolution/`, `prompt-auto-optimization/`, `trajectory-verifier/`, `harness-safety-gate/`, `browser-use-rpa/`, `ai-style-skill/`, `tau2-escalation-experience/` |
| 10 | 🤝 멀티 에이전트 협업 | 6 | `generative-agents/`, `parallel-web-research/`, `voice-werewolf/`, `multi-role-transfer/`, `staged-system-prompt/`, `talkact-reproduction/`, `book-translation/`, `autonomous-phone-registration/` |

**프로젝트 공통 구조** (예: `chapter1/context/`)
```
agent.py        에이전트 본체
main.py         실행 진입점
config.py       프로바이더 설정
grounding.py    근거 평가 로직
tools/          도구 정의
tests/          테스트 코드
validation/     ★ 실측 증거 로그 (evidence.json)
fixtures/       테스트 픽스처
README.md       실행법 + 검수 조건
```

**프로젝트 유형 아이콘**
| 아이콘 | 의미 |
|:--:|---|
| ✅ | 독립 실행 — 전체 코드가 저장소에 있고 API 키만 넣으면 실행 가능 |
| 📖 | 재현 가이드 — 외부 저장소를 `git clone` 해야 하는 안내 문서 |
| 🚧 | 설계 문서 — 아키텍처/구현 계획만 있고 코드는 작성 중 |

### ③ ⭐ Skills — `skills/` (22개, 즉시 활용 가능)

책 10장을 **Claude Code용 Agent Skill 22개로 증류**. 각각 단일 `SKILL.md` 자립 파일.

**Part 1. 에이전트를 어떻게 구축하는가 (14개)**

| Skill | 트리거 상황 | 장 | 연계 코드 |
|---|---|:--:|---|
| `context-engineering` | 시스템 프롬프트·컨텍스트 구조·온디맨드 Skill 설계 | 2 | `chapter1/context/`, `chapter2/prompt-engineering/` |
| `kv-cache-design` | 추론 지연·비용 최적화, 캐시 히트율 하락 진단 | 2 | `chapter2/kv-cache/` |
| `context-compression` | 컨텍스트 팽창, 턴 수 증가에 따른 품질 저하 | 2 | `chapter2/context-compression/` |
| `agent-state-bar` | 무한 루프, TODO 망각, thinking 토큰 팽창 | 2 | `chapter2/system-hint/` |
| `memory-system` | 유저 기억 시스템 설계·구현·평가 | 3 | `chapter3/user-memory/`, `mem0/`, `memobase/` |
| `rag-pipeline` | RAG 검색 파이프라인 구축·튜닝 | 3 | `chapter3/retrieval-pipeline/`, `dense-embedding/` |
| `knowledge-org` | 평면 텍스트를 넘는 지식 조직 (RAPTOR/GraphRAG) | 3 | `chapter3/structured-index/`, `agentic-rag/` |
| `tool-design` | 에이전트 도구 설계, 능력 형태 판단 | 4 | `chapter4/perception-tools/`, `execution-tools/` |
| `tool-discovery` | 도구 수 증가, 도구 정의가 컨텍스트 점유 | 4 | `chapter4/active-tool-discovery/` |
| `mcp-skill-hub` | 서드파티 능력 연동, MCP vs Skill Hub 선택 | 4 | `chapter4/DOCKER_DEPLOYMENT.md` |
| `coding-agent-harness` | 코딩 에이전트 구축, 가드레일 설계 | 5+1 | `chapter5/coding-agent/` |
| `error-recovery` | 장애 복구, 스트림 중단, 프로바이더 교체 | 5 | `chapter5/provider-failover/` |
| `async-event-agent` | 비동기/이벤트 드리븐 에이전트, 외부 이벤트 대응 | 6 | `chapter6/async-agent/` |
| `computer-use` | GUI 자동화 에이전트, 비주얼 그라운딩 | 6 | `chapter6/claude-computer-use-native/` |

**Part 2. 에이전트 능력을 어떻게 높이는가 (8개)**

| Skill | 트리거 상황 | 장 | 연계 코드 |
|---|---|:--:|---|
| `agent-evaluation` | 평가 체계 수립, 지표·환경 설계 | 7 | `chapter7/tau2-bench-eval/`, `model-benchmark/` |
| `eval-dataset-design` | 평가 데이터셋 설계, 평가 태스크 해부 | 7 | `chapter7/tau2-bench-eval/`, `android-world/` |
| `post-training-strategy` | Mid-training / SFT / RL 노선 선택 | 8 | `chapter8/continued-pretraining/`, `retool/` |
| `reward-design` | 보상 함수 설계, 보상 해킹 진단 | 8 | `chapter8/RLVP/`, `retool/` |
| `bad-case-to-dpo` | 프로덕션 bad case를 학습 데이터로 전환 | 8+9 | `chapter8/premature-completion-dpo/` |
| `agent-evolution` | 운영 경험 기반 지속 학습, 자가 진화 루프 | 9 | `chapter9/self-evolution-eval/`, `self-evolving-tools/` |
| `multi-agent-design` | 단일 vs 멀티 에이전트, 협업 토폴로지 | 10 | `chapter10/generative-agents/`, `parallel-web-research/` |
| `loop-engineering` | 에이전트의 조기 완료 선언, 검증기(verifier) 설계 | 10 | `chapter5/paper-to-ppt/`, `video-edit/` |

### ④ 🎬 강의 슬라이드 — `slides/` (42강 완성본)

```
slides/
├── COURSE_OUTLINE.md     승인된 42강 커리큘럼 (Option B)
├── README.md             제작 규칙 문서
├── lesson-01.md ~ lesson-42.md   Slidev 슬라이드 42개
├── course.mjs            강의 메타데이터 (질문/대조표/코드예시 구조화)
├── build-all.mjs         빌드 스크립트
├── style.css             비주얼 스타일 (Seriph 테마)
└── public/images/        도표 리소스
```

**42강 배분**

| 파트 | 챕터 | 강의 번호 | 강의 수 |
|---|---|---|:--:|
| Build an Agent | 서문~5장 | 1~21 | 21 |
| Improve it scientifically | 6~8장 | 22~34 | 13 |
| Expand it | 9~10장 | 35~42 | 8 |
| **합계** | | **1~42** | **42** |

**제작 규칙 (문서화되어 있음)**
- 강의당 15~20분, 슬라이드 1장 ≈ 1분
- 슬라이드 1장에 주장/대조/도표/짧은 코드 중 **하나만**
- 라이브 터미널 데모 전 "Switching to the terminal" 전환 슬라이드 필수
- 라이브 데모는 1~3분 예산
- 슬라이드에 나레이션 대본 없음 → 발표자가 자기 목소리로 해석
- 모든 슬라이드 텍스트는 영어

### ⑤ 웹사이트 & 문서

| 폴더 | 역할 |
|---|---|
| `web-astro/` | Astro 7 기반 온라인 리더 (다국어 전환·챕터 접기·하이라이트·노트) |
| `docs/` | 14개 언어 README + 학습 가이드(`LEARNING.*.md`) + 실험 규약 문서 |
| `docs/EXPERIMENT_CONVENTIONS.md` | 실험 작성 규약 |
| `docs/EXPERIMENT_STATUS.md` | 실험 진행 상태 추적 |
| `extras/agent-lab/` | 에이전트 실행 궤적(trajectory) 시각화 JS + `SCHEMA.md` |
| `extras/` | 다국어 전환기, 네비 접기, Mermaid/MathJax 초기화, 검색 인덱스 라우터 |
| `overrides/` | MkDocs 테마 오버라이드 |
| `mkdocs.yml` | MkDocs 사이트 설정 |

### ⑥ 공용 인프라

| 경로 | 역할 |
|---|---|
| `agentbook/providers/` | 프로바이더 추상화 레이어 (`registry.py`, `resolution.py`, `openrouter.py`, `legacy.py`, `models.py`) |
| `.env.example` | API 키 템플릿 — 12개 프로바이더 + **무료 옵션 2종 명시** |
| `pyproject.toml` | `ch1`~`ch10` extras로 챕터별 의존성 분리 + `viz`/`vllm`/`unsloth`/`all` |
| `uv.lock` | 재현 가능한 lock 파일 (1.3MB) |
| `tests/` | 통합 테스트 92개 |
| `cursor-chats/` | 저자가 책 집필 시 AI와 대화한 기록 **269개 전부 공개** |
| `build_epub.sh`, `epub.css`, `flatten_epub_toc.py` | EPUB 빌드 파이프라인 |
| `scripts/` | 사이트 빌드, i18n 일관성 검사, OG 카드 생성, SEO 메타, 검색 인덱스 분할 등 |
| `.coderabbit.yaml` | CodeRabbit 자동 리뷰 설정 |
| `CLAUDE.md`, `GEMINI.md` | ← **오빠가 직접 추가한 파일** (카리나 페르소나 정의) |

---

## 3. 쉽게 이해하기

### 비유: 이건 "요리학원" 이다

| 보통 레포 | 이 레포 |
|---|---|
| 🍜 인스턴트 라면 한 봉지 (LangChain, CrewAI 사용법) | 🏫 요리학원 전체 |
| 쓰면 됨 | **왜 이 재료를 넣는지** 배움 |

구성물:
- 📕 교재 10과목 (한국어판 포함) → `book-ko/`
- 🍳 실습실 109개 실습 키트 → `chapter1~10/`
- 📝 치트시트 22장 (막힐 때 꺼내보는 쪽지) → `skills/`
- 🎥 강의용 PPT 42장 세트 → `slides/`
- 📓 선생님이 교재 쓸 때 쓴 메모 269장 → `cursor-chats/`

### 핵심 공식을 로봇으로 비유하면

```
🧠 LLM        = 두뇌    (생각하고 결정함)
👀 컨텍스트     = 눈/기억 (지금 뭘 보고 뭘 기억하는지)
✋ 도구        = 손      (검색·코드실행·전화걸기...)
```

**핵심 주장**: 두뇌(모델)는 다 비슷해졌다 → 승부는 **눈(컨텍스트)과 손(도구)** 설계에서 난다.
이 "모델 바깥의 모든 엔지니어링"이 **하네스(Harness)**.

### 10장을 "로봇 키우기 게임"으로

| 장 | 게임으로 치면 | 쉬운 예시 |
|:--:|---|---|
| 1 | 🥚 로봇 탄생 | "도구를 하나씩 빼보니 로봇이 바보가 됨"을 실험으로 증명 |
| 2 | 👀 눈 달기 | "로봇에게 지시서를 어떻게 써줘야 말을 잘 듣나" |
| 3 | 🧠 기억 심기 | "어제 한 얘기 기억하기", "사내 문서 찾아보기" |
| 4 | ✋ 손 달기 | "검색 손", "코드 실행 손", "다른 로봇 부르는 손" |
| 5 | 🛠️ 손으로 손 만들기 | 코드는 "새 도구를 만드는 도구" → 클로드코드 같은 거 |
| 6 | 🎙️ 입·귀·화면 | "전화 받기", "마우스 클릭", "실제 로봇팔 움직이기" |
| 7 | 📊 성적표 만들기 | "우리 로봇 잘하는 거 맞아? 운 좋았던 거 아냐?" → 점수화 |
| 8 | 💉 두뇌 수술 | "모델 자체를 우리 일에 맞게 재훈련" (GPU 필요) |
| 9 | 🔄 스스로 성장 | "실패 로그를 보고 로봇이 스스로 지시서를 고침" |
| 10 | 👥 팀플 | "로봇 5마리가 음성으로 마피아게임하기" 같은 실험도 있음 |

### 증상별 처방 카탈로그

| 증상 | 처방 Skill / 실험 |
|---|---|
| AI가 말을 안 들음, 규칙 위반 | `context-engineering` (2장) — SOP 패턴, 규칙을 참/거짓 판단문으로 |
| API 비용 폭증, 지연 증가 | `kv-cache-design` (2장) — 프롬프트 앞부분 고정, 뒤에만 추가 |
| 턴 늘어날수록 품질 저하 | `context-compression` (2장) |
| 무한 루프, TODO 망각 | `agent-state-bar` (2장) — 매 턴 상태 요약 주입 |
| "다 했어요" 거짓 완료 선언 | `loop-engineering` (10장) — 검증기(verifier) 설계 |
| 스트림 끊김, 프로바이더 장애 | `error-recovery` (5장) |
| 프롬프트 인젝션 공격 | `chapter2/prompt-injection/` |
| 도구 50개로 컨텍스트 터짐 | `tool-discovery` (4장) — 능동적 도구 발견 |
| 보상 해킹 (RL) | `reward-design` (8장) |

### 난이도 신호등

| 챕터 | 난이도 | 추천도 |
|:--:|:--:|---|
| 1~2장 | 🟢 쉬움 | ⭐⭐⭐⭐⭐ 지금 바로 |
| 3~5장 | 🟡 보통 | ⭐⭐⭐⭐⭐ 실무 직결 |
| 6장 | 🟡 보통 | ⭐⭐⭐ 재밌음 (음성/화면제어) |
| 7장 | 🟡 보통 | ⭐⭐⭐⭐ 제품화 필수 |
| 8장 | 🔴 어려움 | ⭐⭐ GPU 있으면 (건너뛰어도 OK) |
| 9~10장 | 🟡 보통 | ⭐⭐⭐ 재밌고 미래지향적 |

> 책 FAQ 명언: **"책을 얇게 보고, 다시 두껍게 보고, 또 얇게 봐라"**

---

## 4. 7개 핵심 질문 답변

### Q1. 설치 및 사용법?

#### 경로 A — 책만 읽기 (설치 0분, 최우선 추천)

```
한국어 PDF: https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-ko.pdf
온라인 리더: https://bojieli.github.io/ai-agent-book/astro/
로컬:       book-ko/chapter1.ko.md ~ chapter10.ko.md
```

#### 경로 B — Skills 설치 (5분, 가성비 1위)

```bash
cd /path/to/ai-agent-book
mkdir -p ~/.claude/skills

# 방법 1) 심링크 — 저장소 업데이트 자동 반영 (추천)
for d in skills/*/; do
  ln -sfn "$(pwd)/${d%/}" ~/.claude/skills/"$(basename $d)"
done

# 방법 2) 복사
cp -R skills/*/ ~/.claude/skills/

# 확인
ls ~/.claude/skills/        # 22개 보이면 성공
```
- 사용법: 별도 조작 불필요. 관련 작업 요청 시 Claude Code가 자동 로드.
- 직접 호출: `/rag-pipeline` 등 슬래시 커맨드
- 프로젝트 한정 적용: `~/.claude/skills/` 대신 `<프로젝트>/.claude/skills/`

#### 경로 C — 실험 코드 실행 (30분~)

```bash
# 1. uv 설치 (권장)
curl -LsSf https://astral.sh/uv/install.sh | sh

# 2. 챕터별 의존성 (ch1~ch10)
uv sync --locked --extra ch1
uv sync --locked --extra ch2 --extra vllm    # 특수 extra는 한 명령에 합칠 것
python -m pip install -e ".[ch1]"            # uv 없을 때

# 3. API 키
cp .env.example .env && nano .env

# 4. 실행
uv run python chapter1/context/main.py
```

> ⚠️ `uv sync`는 매번 정확히 동기화하므로 이전 extra가 제거됨. 여러 extra는 한 명령에 작성.
> ⚠️ 지원 Python: **3.11 ~ 3.13**. 8장 일부 내장 서드파티 컴포넌트는 3.12+ 필요.

**첫 실험 추천 순서**

| 순서 | 실험 | 이유 |
|:--:|---|---|
| 1 | `chapter1/context/` | 도구/컨텍스트를 빼면 에이전트가 망가지는 걸 눈으로 확인 |
| 2 | `chapter1/web-search-agent/` | 가장 기본적인 검색 에이전트 |
| 3 | `chapter2/prompt-engineering/` | 프롬프트 차이가 결과를 바꾸는 체험 |
| 4 | `chapter5/coding-agent/` | 미니 Claude Code |

#### 경로 D — 웹/PDF/슬라이드 직접 빌드

```bash
cd web-astro && npm install && npm run dev     # Astro 리더 (Node 22.12+)
cd book-ko && bash build_pdf.sh                # PDF (pandoc+xelatex+ElegantBook)
bash build_epub.sh                             # EPUB (EPUB.md 참고)
cd slides && npm install && npm run generate    # Slidev 강의 슬라이드
```

### Q2. 플러그인? 스킬? MCP?

**정답: "책 + 실습 코드"가 본체이고, 그 안에 Skills가 포함되어 있다. 플러그인도 MCP 서버도 아니다.**

| 구분 | 해당? | 설명 |
|---|:--:|---|
| 📘 책/교재 | ✅ **본체** | `book-ko/` 등 15개 언어 본문 |
| 🧪 실습 코드 모음 | ✅ **본체** | `chapter1~10/` 109개 프로젝트 |
| 🎓 Agent Skills | ✅ 포함 | `skills/` 22개 — Claude Code에 설치 가능 |
| 🔌 Claude Code Plugin | ❌ 아님 | `.claude-plugin/`, `plugin.json` 없음. 마켓플레이스 미등록 |
| 🌐 MCP 서버 | ❌ 아님 | MCP 서버를 *제공*하진 않음. MCP를 *가르침* (4장) |

**개념 구분**

```
📄 Skill   = "치트시트 / 업무 매뉴얼"
             마크다운 파일. 조건 맞으면 AI가 읽음. 지식·판단기준 제공
             → 이 저장소의 skills/ 22개

🔌 Plugin  = "확장팩 패키지"
             Skill + 커맨드 + 훅 + MCP 설정을 묶은 배포 단위
             → 이 저장소엔 없음 (직접 만들 수 있음 = 수익화 아이디어 2번)

🌐 MCP     = "AI와 외부 시스템을 잇는 USB-C 규격"
             실행되는 서버. 실시간 도구·데이터 제공
             → 이 저장소는 MCP를 설명. chapter4/에 활용 실험 있음
```

### Q3. API 토큰을 사용해야 돼?

| 하려는 일 | API 키 | 비용 |
|---|:--:|---|
| 📖 책 읽기 (PDF/MD/웹) | ❌ 불필요 | 0원 |
| 🎓 Skills 설치·사용 | ❌ 불필요 (Claude Code 구독은 별도) | 0원 |
| 🌐 웹/슬라이드 빌드 | ❌ 불필요 | 0원 |
| 🧪 실험 코드 실행 | ✅ 필요 | 무료~유료 |
| 🧠 8장 후학습 | ✅ + **GPU** | 💸💸 |

**무료로 실험 돌리는 2가지 (`.env.example`에 공식 명시)**

```bash
# 1) OpenRouter 무료 모델 — 어떤 노트북에서도 동작
OPENROUTER_API_KEY=sk-or-...
OPENROUTER_MODEL=google/gemma-4-31b-it:free     # ':free' = 비용 0

# 2) Ollama 완전 로컬 — 키·네트워크 불필요 (RAM 필요)
OLLAMA_BASE_URL=http://localhost:11434/v1
# 실행: --provider ollama   (실험 README에 ollama가 명시된 경우만)
```

**지원 프로바이더 전체 (12종)**

| 프로바이더 | 환경변수 | 접근 |
|---|---|---|
| OpenRouter | `OPENROUTER_API_KEY` | 🌍 전세계 모델, 무료 티어 있음 |
| Google Gemini | `GEMINI_API_KEY` | 🌍 무료 티어 있음 |
| OpenAI | `OPENAI_API_KEY` | 🌍 |
| DeepSeek | `DEEPSEEK_API_KEY` / `DEEPSEEK_BASE_URL` | 🌍 + 🇨🇳, 저렴 |
| Moonshot / Kimi | `MOONSHOT_API_KEY` | 🇨🇳 — 1장 `$web_search` 실험은 이것만 가능 |
| 智谱 GLM | `ZHIPU_API_KEY` | 🇨🇳 |
| SiliconFlow | `SILICONFLOW_API_KEY` | 🇨🇳 오픈모델 다수 |
| ByteDance Doubao | `ARK_API_KEY` | 🇨🇳 |
| Alibaba DashScope | `DASHSCOPE_API_KEY` / `DASHSCOPE_BASE_URL` | 🇨🇳 / 🌍 |
| Atlas Cloud | `ATLASCLOUD_API_KEY` | 🌍 |
| Krill AI | `KRILL_API_KEY` | 🌍 + 🇨🇳 |
| Ollama | `OLLAMA_BASE_URL` | 로컬 |

**한국 사용자 추천 조합**
```bash
OPENROUTER_API_KEY=...    # 1순위: 모델 커버리지 + 무료 티어
GEMINI_API_KEY=...        # 2순위: 무료 티어 넉넉
DEEPSEEK_API_KEY=...      # 3순위: 유료지만 매우 저렴
```
> `agentbook/providers/`에 프로바이더 추상화 레이어가 있어, 특정 키가 없으면 **OpenRouter로 자동 폴백**.

**예상 비용**

| 범위 | 비용 |
|---|---|
| 1~2장 실험 몇 개 | 무료 모델이면 0원, 유료도 수백원 |
| 1~5장 전체 | 수천원 ~ 수만원 |
| 7장 벤치마크 (tau2-bench 등) | 수만원~ (호출량 많음) |
| 8장 후학습 | GPU 렌탈비 (상당) |

### Q4. AI 에이전트 구축에 도움이 될까?

**정답: 매우 도움됨 (⭐⭐⭐⭐⭐). 단, "어떤 종류의 도움"인지 명확히 구분할 필요.**

#### 크게 도움되는 것

1. **설계 판단력** — 가장 큰 가치
   - 이 지식을 시스템 프롬프트에 넣을까, Skill로 뺄까? → 2장 "소량 목록 상주 + 전문은 온디맨드"
   - 도구 50개로 컨텍스트가 터지는데? → 4장 능동적 도구 발견
   - SFT? RL? → 8장 선택 플로우차트
   - 단일 vs 멀티 에이전트? → 10장 컨텍스트 공유/격리 기준

2. **"망가지는 패턴" 카탈로그** — 위 [증상별 처방](#증상별-처방-카탈로그) 표 참고

3. **평가(Eval) 문화** — 7장 전체. 아마추어/프로를 가르는 지점
   - tau2-bench, Elo 리더보드, 비용 분석, 통계적 유의성

4. **돌아가는 레퍼런스 코드 109개**
   - `chapter5/coding-agent/` — tool_registry, sandbox_evaluator, system_state까지
   - `chapter3/user-memory/` + `mem0/` + `memobase/` — 기억 시스템 3종 비교
   - `chapter6/async-agent/` — 이벤트 드리븐

5. **Claude Code 보강** — Skills 22개 설치 시 즉시 효과

#### 기대하면 안 되는 것

| ❌ 아님 | 이유 |
|---|---|
| 복붙해서 바로 제품 | 실험용 코드. 프로덕션 코드 아님 |
| 프레임워크 하나 배우면 끝 | 특정 프레임워크 가이드 아니라 원리서 |
| 노코드 10분 완성 | 중급 이상 Python 필요 |
| 최신 API 레퍼런스 | 책이라 API 변경 미반영 → 공식 문서 병행 |
| 한국 시장 특화 | 중국/글로벌 사례 중심 |

#### 전제 지식 (책 서문 명시)
- 중등 복잡도 Python 코드를 읽고 수정할 수 있음
- ChatGPT, Claude 등 LLM 제품 사용 경험
- AI 보조 코딩 도구 1개 이상 경험 (Claude Code, Codex, Cursor)
- CLI, Git, JSON, REST API 등 소프트웨어 공학 상식
- **8장(후학습) 외에는 수학/ML 요구 수준 낮음**

#### 상황별 추천 경로

```
케이스 1 — 에이전트 처음
  book-ko ch1~ch2 → chapter1/context 실험 → skills/ 설치 → chapter5/coding-agent 분석

케이스 2 — 챗봇 경험 있음, 더 잘하고 싶음
  2장(컨텍스트) + 4장(도구) + 7장(평가) 집중
  → 내 프로젝트에 "10개 태스크 평가셋" 만들기  ← 터닝포인트
  → 실패 케이스 중심 개선

케이스 3 — 제품화해서 팔고 싶음
  1~5장(구축) + 7장(평가) + 9장(개선 루프). 8장은 건너뛰어도 무관
```

> 저자 FAQ 권장 실전 프로젝트 1순위: **"Claude Code / Codex 같은 coding agent를 처음부터 만들기"**
> 1~5장으로 쓸 만한 coding agent 완성 → 7·9장으로 평가셋·개선 루프 → 8장은 모델 자체 개입 → 6·10장으로 음성/Computer Use/멀티에이전트 확장

### Q5. 수익화 아이디어 있어?

→ [5. 수익화 아이디어 10선](#5-수익화-아이디어-10선) 참고.
**법적 결론: Apache-2.0 이므로 상업적 이용 가능** (저작권 고지 + 라이선스 사본 + 변경사항 명시 필요, 상표 사용은 불가).

### Q6. React나 PHP로 만들 수 있어?

**정답: "무엇을" 만드느냐에 따라 다름.**

| 만들 것 | React | PHP | 비고 |
|---|:--:|:--:|---|
| 책 읽는 웹사이트 | ✅ 최적 | ✅ 가능 | 이미 Astro로 있음 |
| 에이전트 대시보드/UI | ✅✅ **최적** | 🟡 | React 강세 |
| 채팅 인터페이스 (스트리밍) | ✅✅ **최적** | 🟡 | SSE/WebSocket |
| 에이전트 런타임 (핵심 루프) | ✅ 가능 | 🟡 가능 | 원리는 언어 무관 |
| MCP 서버 | ✅ (TS SDK 공식) | ❌ 비추 | TypeScript SDK 품질 좋음 |
| 평가(Eval) 파이프라인 | 🟡 | ❌ | Python 생태계 압도적 |
| RAG 임베딩/벡터 연산 | 🟡 | ❌ | Python 라이브러리 생태계 |
| 모델 후학습 (8장) | ❌ | ❌ | Python + PyTorch 필수 |

**핵심: 책의 원리는 언어 중립적.** 에이전트 핵심 루프를 JS로 쓰면:

```javascript
// ReAct 루프 — 개념은 Python과 동일
async function agentLoop(userInput) {
  let messages = [
    { role: "system", content: SYSTEM_PROMPT },   // 정적 프리픽스 (캐시 친화)
    { role: "user", content: userInput }
  ];

  while (true) {
    const res = await llm.chat({ messages, tools: TOOL_SCHEMAS });
    messages.push(res.message);

    if (!res.message.tool_calls) return res.message.content;   // 종료

    for (const call of res.message.tool_calls) {
      const result = await executeTool(call);                   // 프레임워크가 실행
      messages.push({
        role: "tool",
        tool_call_id: call.id,
        content: JSON.stringify(result)
      });
    }
  }
}
```
→ 책 2장 **"모델은 결정하고, 프레임워크는 실행한다"** 원칙 그대로.

**React/Next.js 추천 프로젝트 TOP 5**

| # | 프로젝트 | 근거 | 스택 |
|:--:|---|---|---|
| 1 | **에이전트 궤적 시각화 대시보드** | `extras/agent-lab/agent-trajectory.js` + `SCHEMA.md` 이미 존재 | Next.js + React Flow + Recharts |
| 2 | 스트리밍 채팅 UI + 도구 호출 표시 | 6장 비동기/이벤트 드리븐 | Next.js App Router + Vercel AI SDK + SSE |
| 3 | 프롬프트 Playground (멀티모델 비교) | 7장 평가 사상 | Next.js + OpenRouter API |
| 4 | 한국어 리더 앱 (하이라이트·노트·퀴즈) | `book-ko/*.md` | Next.js + MDX + Supabase |
| 5 | Eval 결과 리더보드 | `chapter7/elo-leaderboard/` | React + D3/Recharts |

**PHP가 괜찮은 경우**
- 기존 PHP 서비스(Laravel/WordPress)에 AI 기능 추가 ← **PHP 최대 강점: 레거시 통합**
- WordPress 플러그인으로 AI 에이전트 (시장 매우 큼)
- 간단한 RAG 챗봇 (벡터DB는 외부 서비스 사용)
- 웹훅 수신 → 에이전트 트리거 (6장 이벤트 드리븐)

추천 라이브러리: `openai-php/client`, `php-llm/llm-chain`, Laravel + pgvector

**PHP가 버거운 경우**
- 임베딩 직접 계산 (Python sentence-transformers 생태계)
- 모델 학습/파인튜닝 (불가)
- 장시간 실행 에이전트 (요청-응답 모델 → 큐(Redis/Horizon) 필요)
- 복잡한 평가 파이프라인

**권장 하이브리드 아키텍처**

```
┌─────────────────────────────────┐
│  ⚛️ React / Next.js (프론트)      │  채팅 UI, 대시보드, 시각화
└──────────────┬──────────────────┘
               │ REST / SSE / WebSocket
┌──────────────▼──────────────────┐
│  🐘 PHP(Laravel) 또는 Node       │  인증, 과금, 비즈니스 로직, DB
└──────────────┬──────────────────┘
               │ 내부 API
┌──────────────▼──────────────────┐
│  🐍 Python (에이전트 코어)         │  FastAPI + 책의 패턴들
│     + 벡터DB + 평가 파이프라인      │
└─────────────────────────────────┘
```
> 대안: 전부 TypeScript (Node + Next.js + Vercel AI SDK). MCP는 TS SDK가 공식.

### Q7. 유튜브 강의 영상으로 제작 가능할까?

**정답: 가능하며, 레포에 강의 자료가 이미 완성되어 있음.**

- `slides/` 에 **42강 영상 강의용 Slidev 덱 완성본**
- `COURSE_OUTLINE.md` 에 승인된 커리큘럼
- `README.md` 에 제작 규칙 (강의당 15~20분, 슬라이드 1장 ≈ 1분, 터미널 데모 1~3분 등)
- 슬라이드에 나레이션 대본 없음 → **"뼈대는 다 있고 목소리만 얹으면 됨"**

**법적: Apache-2.0 → 상업적 이용 가능 ✅**

영상 설명란 출처 표기 예시:
```
📚 원작: 《深入理解 AI Agent：设计原理与工程实践》 by Bojie Li
🔗 https://github.com/bojieli/ai-agent-book
📄 License: Apache-2.0
🇰🇷 한국어 번역: @JeongJaeSoon
✏️ 본 강의는 원작을 한국어로 재구성했습니다.
```
금지: 저자 공식 강의 사칭(상표), 원작자 크레딧 삭제.
권장: 저자에게 Issue/Discussion으로 사전 연락 → "저자 공인"이라는 마케팅 자산 확보.

**제작 전략 3안**

| 안 | 내용 | 기간 | 평가 |
|---|---|---|---|
| A. 42강 완주 | 한국어권 유일 풀코스 → 강력한 브랜드 | 10~12개월 | 번아웃 리스크 |
| **B. 핵심 12강 압축** | 아래 커리큘럼 | 3개월 | ⭐ **추천** |
| C. 쇼츠 + 실험 데모 | 쇼츠(30~60초) + 롱폼(10~15분) | 즉시 | 가장 빠른 성장 |

**플랜 B 커리큘럼 (핵심 12강)**
```
 1. 에이전트란? (Agent = LLM + 컨텍스트 + 도구)
 2. 컨텍스트 엔지니어링 기초
 3. 시스템 프롬프트 잘 쓰는 법 (SOP 패턴)
 4. KV 캐시와 비용 최적화          ← 조회수 기대
 5. 컨텍스트 압축
 6. 유저 메모리 시스템
 7. RAG 제대로 만들기
 8. 도구 설계 + MCP
 9. 코딩 에이전트 만들기            ← 킬러 콘텐츠
10. 에이전트 평가(Eval) 하기
11. 멀티 에이전트 협업
12. 프로덕션 체크리스트
```

**조회수 기대 주제 TOP 5**

| 순위 | 제목(안) | 근거 |
|:--:|---|---|
| 1 | "클로드코드 직접 만들어보기" | `chapter5/coding-agent/` · 최고 관심사 |
| 2 | "AI API 비용 90% 줄이는 KV 캐시의 비밀" | `chapter2/kv-cache/` · 돈 얘기 |
| 3 | "AI가 '다 했어요' 거짓말하는 이유" | `skills/loop-engineering` · 공감 |
| 4 | "프롬프트 인젝션 실제로 해보기" | `chapter2/prompt-injection/` · 보안 |
| 5 | "AI 에이전트 5마리로 마피아게임" | `chapter10/voice-werewolf/` · 바이럴 |

**제작 워크플로**
```bash
cd slides
npm install
npm run generate           # lesson-*.md → Slidev 덱
npx slidev lesson-02.md    # 발표 모드

# 한국어화: lesson-*.md 또는 course.mjs 메타데이터 번역
# 녹화: OBS Studio (무료) — 슬라이드 + 터미널 + 웹캠
# 편집: DaVinci Resolve 또는 CapCut (무료)
```

**차별화 포인트**

| 다른 채널 | 이 채널 |
|---|---|
| "LangChain으로 챗봇 만들기" | "왜 LangChain 없이도 되는지, 왜 쓸 때도 있는지" |
| 이론만 설명 | **실험 109개를 실제로 터미널에서 실행** |
| 영어 자료 번역 | 한국어 원서급 깊이 |
| 데모만 보여줌 | "데모는 되는데 제품은 안 되는 이유" |

---

## 5. 수익화 아이디어 10선

### 법적 베이스라인

```
✅ Apache License 2.0 → 상업적 이용 가능
```

| 필수 | 예시 |
|---|---|
| 저작권 고지 포함 | `LICENSE` 파일 동봉 |
| 출처 표기 | "원작: 《深入理解 AI Agent》 by Bojie Li (github.com/bojieli/ai-agent-book)" |
| 변경 사항 명시 | "한국어로 재구성 및 확장" |
| 번역자 크레딧 | "한국어 번역: @JeongJaeSoon" |

| 금지 |
|---|
| ❌ 저자/프로젝트명을 공식 승인받은 것처럼 사용 (상표권) |
| ❌ 크레딧 삭제 후 자기 것처럼 판매 |
| ⚠️ 원본 PDF 그대로 유료 재판매 (법적으론 가능하나 무료 배포본이라 비현실적 + 평판 리스크) |

### 수익화 맵

| # | 아이디어 | 난이도 | 초기투자 | 수익잠재력 | 회수기간 | 적합도 |
|:--:|---|:--:|:--:|:--:|:--:|:--:|
| 1 | 🎬 유튜브 한국어 강의 | 🟢 | 시간 | 💰💰💰 | 6~12개월 | ⭐⭐⭐⭐⭐ |
| 2 | 🔌 Claude Code 플러그인 | 🟡 | ~0 | 💰💰 | 1~3개월 | ⭐⭐⭐⭐⭐ |
| 3 | 🌐 MCP 서버 (유료) | 🟡 | 서버비 | 💰💰💰 | 3~6개월 | ⭐⭐⭐⭐ |
| 4 | 📚 온라인 강의 | 🟡 | 시간 | 💰💰💰💰 | 3~6개월 | ⭐⭐⭐⭐⭐ |
| 5 | 💼 기업 교육/컨설팅 | 🔴 | 신뢰자산 | 💰💰💰💰💰 | 6~18개월 | ⭐⭐⭐⭐ |
| 6 | 🛠️ SaaS 제품 | 🔴 | 개발비 | 💰💰💰💰💰 | 12~24개월 | ⭐⭐⭐ |
| 7 | 📝 유료 뉴스레터 | 🟢 | 시간 | 💰💰 | 3~6개월 | ⭐⭐⭐⭐ |
| 8 | 🌟 OSS 기여 → 브랜딩 | 🟢 | 시간 | 💰 (간접) | 1~3개월 | ⭐⭐⭐⭐⭐ |
| 9 | 🏢 개발 에이전시 | 🔴 | 영업력 | 💰💰💰💰💰 | 6~12개월 | ⭐⭐⭐ |
| 10 | 🎓 오프라인 부트캠프 | 🔴 | 공간/운영 | 💰💰💰💰 | 6~12개월 | ⭐⭐ |

---

### 1️⃣ 유튜브 한국어 강의 채널 (최우선 진입점)

**왜 1순위**
- `slides/` 42강 완성본 존재 → 제작 비용 급감
- 실험 109개 = 타 채널이 못 하는 "실제로 돌려보는" 콘텐츠
- 한국어 번역본 존재 → 번역 비용 0
- 초기 투자 거의 0 (OBS 무료 + DaVinci 무료)
- 모든 다른 수익화의 유입 깔때기

**수익 구조 4층**
```
Layer 4: 기업 교육/컨설팅 ──── 회당 200~1,000만원
Layer 3: 온라인 강의 판매 ──── 월 300~3,000만원
Layer 2: 멤버십/후원 ───────── 월 20~200만원
Layer 1: 유튜브 광고 ───────── 월 0~500만원
```

**실행 로드맵**

| Phase | 기간 | 할 일 |
|---|---|---|
| 0. 준비 | 2주 | 슬라이드 빌드·품질 확인, OBS/DaVinci 세팅, 마이크(10만원대 이상 — 음질이 이탈률 결정) |
| 1. 파일럿 | 1개월 | 3편 업로드 (①에이전트란? 15분 ②도구 빼면 바보됨 실험 18분 ③코딩에이전트 만들기 25분) → 시청 유지율 40% 넘으면 GO |
| 2. 핵심 12강 | 3개월 | 플랜 B 커리큘럼, 주 1편 |
| 3. 수익화 전환 | 6개월~ | 구독 1,000 + 시청 4,000시간 → 광고 ON, 멤버십(월 4,900원), 온라인 강의 전환 |

**리스크 대응**

| 리스크 | 대응 |
|---|---|
| 42강 번아웃 | 12강으로 시작, 반응 보고 확장 |
| 한국 시장 규모 | 영어 자막 병행 (slides가 이미 영어) |
| 전문용어 난이도 | 쇼츠로 용어 하나씩 설명 (유입 겸용) |
| 데모 녹화 API 비용 | 무료 모델 / Ollama 사용 |

---

### 2️⃣ Claude Code 플러그인 패키징 (가성비 최고)

**핵심 아이디어**: `skills/` 22개는 현재 수동 설치 → 플러그인으로 원클릭화

```
현재: for d in skills/*/; do ln -sfn ... done
개선: /plugin install agent-book-ko
```

**구조**
```
agent-book-ko/
├── .claude-plugin/plugin.json
├── skills/                      22개 스킬 (한국어화) ★부가가치1
│   ├── context-engineering/SKILL.md
│   └── ...
├── commands/                    슬래시 커맨드 ★부가가치2
│   ├── agent-audit.md           "내 에이전트 설계 감사"
│   ├── eval-starter.md          "평가셋 10개 생성"
│   ├── context-doctor.md        "컨텍스트 팽창 원인 진단"
│   └── cost-check.md            "KV캐시 깨지는 지점 탐색"
├── hooks/                       자동 체크 ★부가가치3
│   └── pre-commit-agent-lint.js
└── README.md
```

**부가가치 3가지 (수익의 근거)**
1. **한국어화** — 원본 스킬은 중국어. 한국 개발자에게 장벽 제거
2. **슬래시 커맨드** — 원본에 없는 실무 액션 (감사/진단/평가셋 생성)
3. **최신화** — 책은 2.0 고정. 최신 모델/API 반영

**수익 모델**

| 모델 | 방식 | 예상 |
|---|---|---|
| 무료 + 브랜딩 | 공개 배포 → GitHub 스타 → 신뢰 자산 | 0원 (다른 수익의 기반) |
| Freemium | 기본 22스킬 무료 / Pro 커맨드·훅 유료 | 월 $5~15 × 구독자 |
| 기업판 | 사내 코딩 규칙 통합 커스텀 | 건당 300~1,000만원 |
| 리드 생성 | 무료 배포 → 강의/컨설팅 유입 | 간접 (가장 현실적) |

**즉시 실행 가능한 스캐폴드**
```bash
mkdir -p agent-book-ko/.claude-plugin
cp -R /path/to/ai-agent-book/skills agent-book-ko/

cat > agent-book-ko/.claude-plugin/plugin.json <<'EOF'
{
  "name": "agent-book-ko",
  "description": "AI 에이전트 설계 원리 22개 스킬 (한국어) — 《深入理解 AI Agent》 기반",
  "version": "0.1.0",
  "author": { "name": "bmshin94" }
}
EOF
```
> 평가: 직접 수익은 작지만 **투자 대비 효과가 압도적**. 1~2주 작업으로 GitHub 스타 + 신뢰도 확보 → 강의/컨설팅 연결.

---

### 3️⃣ MCP 서버 (유료) — "에이전트 설계 자문"

**아이디어**: 책 지식을 실시간 조회 가능한 MCP 서버로

```
개발자: "mem0랑 memobase 차이가 뭐야?"
   ↓ MCP 서버가 책 3장 + 실험 비교표 반환
   ↓ Claude가 그 근거로 설계 제안
```

**제공 도구(Tools) 설계**
```typescript
server.tool("search_agent_knowledge", { query, chapter? })
  // 책 본문 + 실험 README 벡터 검색 → 근거와 함께 반환

server.tool("get_experiment", { name })
  // 실험 코드 구조 + 실행법 + 검증 로그 반환

server.tool("audit_agent_design", { system_prompt, tools })
  // 책 체크리스트로 설계 감사 → 리스크 리포트

server.tool("suggest_eval_set", { domain })
  // 7장 원칙 기반 평가 태스크 10개 생성
```

**수익 모델**

| 티어 | 가격 | 내용 |
|---|---|---|
| Free | 0원 | 월 100 쿼리, 검색만 |
| Pro | 월 $19 | 무제한 검색 + 설계 감사 + 평가셋 생성 |
| Team | 월 $99 | 사내 문서 함께 인덱싱 + 팀 공유 |
| Enterprise | 협의 | 온프레미스 + 커스텀 지식베이스 |

**손익 시뮬레이션**
```
비용: 서버(Fly.io/Railway) $20/월 + 임베딩 API $10/월 ≈ 월 4만원
손익분기: Pro 구독자 2명
목표: Pro 50명 = 월 $950 ≈ 130만원
```

> ⚠️ 책 본문 전문을 그대로 제공하면 재배포 이슈 (Apache-2.0상 출처 표기하면 OK지만 저자와 상의 권장).
> 안전한 전략: **책 지식 + 독자적 가공(한국 사례, 최신 API, 실측 데이터)** 혼합.

---

### 4️⃣ 온라인 강의 플랫폼 (단기 수익 최대)

**플랫폼 비교**

| 플랫폼 | 수수료 | 특징 | 적합도 |
|---|:--:|---|:--:|
| 인프런 | ~30% | 개발자 압도적 1위, 자유 가격 | ⭐⭐⭐⭐⭐ |
| 패스트캠퍼스 | 기획료 | 선급금 + 마케팅 강력, 심사 있음 | ⭐⭐⭐⭐ |
| 클래스101 | ~40% | 취미 위주, 개발 약함 | ⭐⭐ |
| Udemy | 50~97% | 글로벌, 할인 폭탄 | ⭐⭐⭐ |
| 자체 판매 | 0% (+PG 3%) | 수익 최대, 마케팅 전부 자력 | ⭐⭐⭐⭐ |

**강의 패키지 3단 구성**

| 티어 | 가격 | 분량 | 내용 | 타겟 |
|---|---|---|---|---|
| 🥉 입문 | 55,000원 | 6시간(12강) | 1~2장 + chapter1 실험 2개 | 에이전트 처음 |
| 🥈 **실전** ⭐ | 165,000원 | 15시간(30강) | 2~5장 + 7장 + coding-agent 완성 프로젝트 | 현업 개발자 |
| 🥇 마스터 | 440,000원 | 30시간 + 라이브 Q&A 4회 | 전 챕터 + 1:N 코드리뷰 + 수료 프로젝트 | 팀 리드, 창업자 |

**수익 시뮬레이션 (인프런, 수수료 30% 가정)**

| 시나리오 | 수강생/월 | 월 매출 | 실수령 |
|---|---|---|---|
| 보수적 | 입문 20 + 실전 5 | 193만원 | **135만원** |
| 현실적 | 입문 50 + 실전 20 + 마스터 2 | 683만원 | **478만원** |
| 낙관적 | 입문 150 + 실전 60 + 마스터 10 | 2,165만원 | **1,515만원** |

**차별화 무기**
- 실험 109개 → 타 강의에 없는 "진짜 돌려보는" 실습
- `validation/` 증거 로그 → "검증된 결과"라는 신뢰
- 평가(Eval) 챕터 → 한국 강의 중 거의 유일
- 한국어 책 PDF 무료 제공 가능 (Apache-2.0) → 교재 포함 효과

> 강의는 한 번 만들면 계속 팔리는 자산(패시브 인컴). **유튜브 → 강의** 깔때기가 가장 강력.

---

### 5️⃣ 기업 교육 / 컨설팅 (단가 최고)

**왜 단가가 높은가**: 기업은 "직원 20명 × 3개월 헤매는 비용" > "교육비 500만원" → 명확한 ROI

**상품 라인업**

| 상품 | 기간 | 단가 | 내용 |
|---|---|---|---|
| 세미나 | 2시간 | 100~300만원 | "AI 에이전트 현황과 설계 원리" |
| 워크샵 | 1일(8h) | 300~600만원 | 실험 핸즈온 + 사내 과제 적용 |
| 집중 과정 | 3일 | 800~1,500만원 | 1~7장 전체 + 팀 프로젝트 |
| **설계 감사** ⭐ | 2~4주 | 1,000~3,000만원 | 기존 에이전트 진단 + 개선 로드맵 |
| 리테이너 | 월 단위 | 월 300~800만원 | 지속 자문 + 코드 리뷰 |

**최고 수익 상품: "에이전트 설계 감사" (7장 기반)**
```
기업 상황: "AI 챗봇 만들었는데 품질이 안 나오고 비용만 나간다"

수행 내용:
1. 현재 에이전트 평가셋 구축 (10~30 태스크)
2. 베이스라인 측정 → "현재 성공률 42%" ← 숫자로 제시
3. 실패 케이스 분류 (2·4·5장 패턴 카탈로그 활용)
4. 비용 분석 (KV 캐시 히트율, 토큰 낭비 지점)
5. 개선 로드맵 + 우선순위
6. 재측정 → "68%로 개선"

→ "컨설팅"이 아니라 "측정 가능한 성과" → 고단가 정당화
```

**시작 경로**: 유튜브/블로그로 신뢰 자산(6~12개월) → 무료/저가 세미나 1~2회로 레퍼런스 → 사례 공개(익명화) → 단가 인상

---

### 6️⃣ SaaS 제품 (장기 홈런)

#### A. "AgentLens" — 에이전트 관측/디버깅 대시보드
```
근거: extras/agent-lab/agent-trajectory.js + SCHEMA.md 존재
기능: 궤적 시각화, 도구 호출 타임라인, 토큰/비용 분석, 실패 패턴 자동 분류
스택: Next.js(React) + Postgres + ClickHouse
경쟁: LangSmith, Langfuse, Helicone
차별화: 한국어 UI + 국내 모델(Kimi/GLM/네이버) 지원 + 책 패턴 기반 자동 진단
가격: Free(월 10k 트레이스) / Pro $49 / Team $199
```

#### B. "EvalKit" — 에이전트 평가 자동화 ⭐ 추천
```
근거: chapter7/ 전체 (tau2-bench, Elo, 비용 분석)
기능: 평가셋 자동 생성 → 모델 A/B 비교 → 통계적 유의성 → 리포트
강점: 한국 시장에 공급이 거의 없는 영역 (수요는 큼)
가격: Free(월 100회) / Pro $39 / Team $149
```

#### C. "MemoryAPI" — 유저 기억 서비스
```
근거: chapter3/user-memory/, mem0/, memobase/ 비교 실험
기능: 대화 저장 → 중요 정보 추출 → 다음 세션 주입 (API 2개)
경쟁: mem0 (한국어 처리 약함)
차별화: 한국어 특화 + 개인정보 로그 마스킹 (chapter3/log-sanitization 활용)
가격: 사용량 기반 ($0.1/1k memories)
```

**현실 체크**: 기술만으론 안 됨(마케팅/영업/CS가 80%), 12~24개월 자금 필요. 단 유일하게 지수 성장.
→ 권장: 유튜브로 고객을 먼저 모으고 → 그 사람들의 실제 문제로 SaaS 설계

---

### 7️⃣ 유료 뉴스레터 / 멤버십

```
플랫폼: 스티비(국내) / Substack / Maily / 페이트리온
가격: 월 9,900원 ~ 19,900원

콘텐츠:
├─ 주간 "에이전트 논문/릴리즈 큐레이션 + 책 원리로 해석"
├─ 실험 1개씩 심층 해부 (109개 = 2년치 콘텐츠)
├─ 실무 트러블슈팅 사례
└─ 구독자 Q&A

수익: 100명 × 9,900원 = 월 99만원 / 500명 = 월 495만원
```
> 장점: 유튜브보다 훨씬 적은 구독자로 수익 발생. 영상 편집 불필요.

---

### 8️⃣ OSS 기여 → 개인 브랜딩 (직접 수익 X, 레버리지 최고)

**할 일**
1. 한국어 번역 품질 개선 PR (현재 번역이 중국어 원본보다 뒤쳐짐 — README 명시)
2. `skills/` 22개 한국어 번역 PR
3. 실험 버그 수정 / 한국 프로바이더(네이버 하이퍼클로바X 등) 추가 PR
4. "한국 개발자를 위한 보충 설명" 문서 추가

**왜 돈이 되는가**

| 얻는 것 | 효과 |
|---|---|
| "이 책 한국어 컨트리뷰터" 타이틀 | 강의/컨설팅 신뢰도 상승 |
| 저자와의 관계 | 공식 협업 가능성 |
| GitHub 프로필 | 채용/영업에서 강력한 증거 |
| 발표 기회 | 컨퍼런스 → 더 큰 신뢰 |
| **종이책 번역서 출판 기회** | 인세 + 최고 권위 |

> 보너스: 한국 출판사(한빛미디어, 인사이트, 제이펍)에 **번역서 출판 제안**.
> Apache-2.0이라 법적으로 가능. 저자 허락 시 더 유리. 인세 + "역자" 타이틀.

---

### 9️⃣ AI 에이전트 개발 에이전시

```
서비스: 기업 맞춤 에이전트 구축 (사내 챗봇, RAG, 업무 자동화)
단가: 프로젝트당 2,000만 ~ 2억원
근거: 실험 109개 = 재사용 가능한 패턴 라이브러리

차별화 (핵심):
"우리는 평가(Eval) 기반으로 개발합니다.
 납품 시 성공률 N%를 숫자로 보증합니다."   ← 7장 덕분에 가능
→ 대부분 업체가 못 하는 영역
```

---

### 🔟 오프라인 부트캠프 / 스터디

```
🟢 작게: 유료 스터디 (8주, 10명 × 30만원 = 300만원)
🟡 중간: 주말 집중반 (3주, 20명 × 80만원 = 1,600만원)
🔴 크게: 정부지원 과정(KDT) — 운영 부담 큼
```

---

## 6. 실행 로드맵

### 📅 0~3개월: 신뢰 자산 만들기 (수익 거의 0, 투자 단계)

```
[ ] 1. skills/ 설치해서 직접 써보기 (5분)
[ ] 2. chapter1/context + chapter5/coding-agent 실험 직접 실행
[ ] 3. "agent-book-ko" 플러그인 제작 → 무료 공개       (아이디어 2)
[ ] 4. 한국어 번역 개선 PR 2~3개                       (아이디어 8)
[ ] 5. 유튜브 파일럿 3편 업로드                         (아이디어 1)
```

### 📅 3~9개월: 첫 수익

```
[ ] 6. 유튜브 핵심 12강 완주 → 수익화 조건 달성
[ ] 7. 유료 뉴스레터 시작 (월 100만원 목표)             (아이디어 7)
[ ] 8. 인프런 "입문" 강의 출시 (55,000원)               (아이디어 4)
```

### 📅 9~18개월: 본격 수익

```
[ ] 9.  "실전" 강의 출시 (165,000원) — 월 400만원+ 목표
[ ] 10. 기업 세미나 1~2건 수주                          (아이디어 5)
[ ] 11. MCP 서버 또는 SaaS MVP 출시                     (아이디어 3/6)
```

### 💰 18개월 후 예상 포트폴리오

| 수익원 | 월 수익 (현실적) |
|---|---|
| 유튜브 광고 + 멤버십 | 100~200만원 |
| 온라인 강의 | 300~600만원 |
| 뉴스레터 | 100~300만원 |
| 기업 교육 (분기 1건) | 월평균 100~200만원 |
| **합계** | **월 600~1,300만원** |

### ⚠️ 원칙

| ✅ 이렇게 | ❌ 이러면 안 됨 |
|---|---|
| 하나씩 순서대로 | 10개 동시에 (실패 확률 높음) |
| 무료로 신뢰 먼저 | 처음부터 유료 |
| "내가 직접 해본 것" 콘텐츠 | 책 요약만 (가치 없음) |
| 출처·크레딧 당당히 표기 | 내 것처럼 포장 (평판 리스크) |
| 한국 시장 특화 | 단순 번역 (차별화 0) |
| 저자와 좋은 관계 | 무단 상업화 (관계 파괴) |

> **가장 중요한 것**
> 책 내용을 파는 게 아니라, 책을 기반으로 한 **본인의 경험과 해석**을 파는 것.
> 책은 무료고 누구나 읽을 수 있지만, **실험 109개를 직접 돌려본 사람**은 희귀하다.

---

## 7. 참고 링크 모음

### 📍 저장소

| 구분 | 주소 |
|---|---|
| **이 저장소 (포크)** | https://github.com/bmshin94/ai-agent-book |
| **원본 저장소 (upstream)** | https://github.com/bojieli/ai-agent-book |
| 자매편 《深入理解 AI Infra》 | https://github.com/bojieli/ai-infra-book |
| Issues (오탈자·버그·번역) | https://github.com/bojieli/ai-agent-book/issues |
| Discussions (질문·토론) | https://github.com/bojieli/ai-agent-book/discussions |
| Releases (PDF/EPUB 고정 버전) | https://github.com/bojieli/ai-agent-book/releases |

### 📖 읽기

| 구분 | 주소 |
|---|---|
| 온라인 리더 (다국어) | https://bojieli.github.io/ai-agent-book/astro/ |
| MkDocs 사이트 | https://bojieli.github.io/ai-agent-book/ |
| 사고력 문제 모범답안 | https://bojieli.github.io/ai-agent-book/book/reference-answers/ |
| 🇰🇷 한국어 PDF | https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-ko.pdf |
| 🇰🇷 한국어 EPUB | https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-ko.epub |
| 🇺🇸 영어 PDF | https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-en.pdf |

### 🔑 API 플랫폼

| 플랫폼 | 주소 | 특징 |
|---|---|---|
| OpenRouter | https://openrouter.ai/ | 🌍 전세계 모델, **무료 티어** |
| Google AI Studio (Gemini) | https://aistudio.google.com/ | 🌍 **무료 티어** |
| Ollama | https://ollama.com/ | 로컬, 완전 무료 |
| DeepSeek | https://platform.deepseek.com/ | 🌍+🇨🇳, 저렴 |
| OpenAI | https://platform.openai.com/ | 🌍 |
| Moonshot (Kimi) | https://platform.moonshot.cn/ | 🇨🇳 |
| 智谱 GLM | https://open.bigmodel.cn/ | 🇨🇳 |
| SiliconFlow | https://siliconflow.cn/ | 🇨🇳 |
| Atlas Cloud | https://www.atlascloud.ai/ | 🌍 |
| 모델 선택 가이드 (저자 추천) | https://01.me/2025/07/llm-api-setup/ | — |

### 🛠️ 제작 도구

| 도구 | 주소 | 용도 |
|---|---|---|
| uv | https://docs.astral.sh/uv/getting-started/installation/ | Python 환경 (lock 재현) |
| Slidev | https://sli.dev/ | 강의 슬라이드 |
| OBS Studio | https://obsproject.com/ | 화면 녹화 (무료) |
| DaVinci Resolve | https://www.blackmagicdesign.com/products/davinciresolve | 영상 편집 (무료) |
| 인프런 | https://www.inflearn.com/ | 강의 판매 |
| 스티비 | https://stibee.com/ | 뉴스레터 |

### 🙏 크레딧

| 역할 | 이름 |
|---|---|
| 원작자 | Bojie Li (李博杰) — [@bojieli](https://github.com/bojieli) |
| 🇰🇷 한국어 번역 | [@JeongJaeSoon](https://github.com/JeongJaeSoon) |
| 🇺🇸 영어 번역 | [@nsdevaraj](https://github.com/nsdevaraj), [@whanyu1212](https://github.com/whanyu1212) |
| 🇯🇵 일본어 번역 | [@eltociear](https://github.com/eltociear) |
| 라이선스 | Apache License 2.0 |

---

## 📌 핵심 체크리스트 (오늘 당장 할 수 있는 것)

```bash
# ① Skills 22개 설치 (5분, 가성비 1위)
cd /path/to/ai-agent-book
mkdir -p ~/.claude/skills
for d in skills/*/; do ln -sfn "$(pwd)/${d%/}" ~/.claude/skills/"$(basename $d)"; done
ls ~/.claude/skills/        # 22개 확인

# ② 한국어 책 읽기 시작
cat book-ko/chapter1.ko.md | less

# ③ 첫 실험 돌려보기 (무료 모델로 가능)
cp .env.example .env        # OPENROUTER_API_KEY 또는 OLLAMA_BASE_URL 설정
uv sync --locked --extra ch1
uv run python chapter1/context/main.py

# ④ 강의 슬라이드 확인
cd slides && npm install && npx slidev lesson-02.md
```

---

> 📝 이 문서는 `bmshin94/ai-agent-book` 저장소 전수조사 결과와 활용/수익화 전략을 정리한 것입니다.
> 수익 추정치는 한국 시장 일반 사례를 바탕으로 한 **추정**이며 보장된 수치가 아닙니다.
> 상업적 활용 시 Apache-2.0 라이선스 조건(저작권 고지·라이선스 사본·변경사항 명시)을 반드시 준수하세요.
