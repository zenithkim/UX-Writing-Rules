# UX Writing Rule Skill for Claude Code

토스 UX 라이팅 원칙 8가지를 기반으로 문구를 자동 분석·검증·개선하는 Claude Code 스킬입니다.

## What it does

입력한 문구를 **5단계 파이프라인**으로 검증하고 최적화합니다:

| Step | 역할 | 설명 |
|------|------|------|
| Step 0 | URL 맥락 요약 | URL 입력 시 페이지 크롤링 후 제품·타겟·톤 맥락 추출 |
| Step 1 | 원칙 분석 | 토스 UX 라이팅 원칙 8가지 준수 여부 검사 |
| Step 2 | 개선 추천 | 위반 원칙에 대한 개선 문구 1~3개 추천 |
| Step 3 | 재검증 | 추천 문구를 다시 원칙 8가지로 검증 |
| Step 4 | CTR 최적화 | 마케팅 심리 트리거 적용 (FOMO, 사회적 증명 등) |
| Step 5 | 중복 체크 | Title/Description 쌍의 어휘·의미·역할 중복 탐지 |

## UX 라이팅 원칙 8가지

| # | 원칙 | 기준 |
|---|------|------|
| 1 | 명확하게 | 유저가 해야 할 액션을 직접 명시 |
| 2 | 간결하게 | 불필요한 수식어·중복 표현 제거 |
| 3 | 친근하게 | 딱딱한 문어체 지양, 구어체 사용 |
| 4 | 일관되게 | 동일 개념에 동일 용어 사용 |
| 5 | 단 하나의 핵심만 | 한 문구에 메시지 하나만 |
| 6 | 조건과 행동 구체적으로 | "~하면 ~된다" 형식 |
| 7 | 확실한 보상 약속 | 구체적 수치나 형태로 혜택 명시 |
| 8 | 자주 쓰는 말로 | 전문용어 없이 일상 언어 사용 |

## 추가 분석 프레임워크

- **프레이밍 효과 기법 3가지**: 진입 장벽 해소, 가능성 프레이밍, 이득 중심 프레이밍
- **UX 심리학 법칙 10가지**: 힉의 법칙, 밀러의 법칙, 피크엔드 법칙, 폰 레스토프 효과 등
- **마케팅 심리 트리거 7가지**: FOMO, 긴급성, 희소성, 사회적 증명, 손실 회피, 호기심 격차, 즉시 보상

## Installation

`SKILL.md` 파일을 Claude Code 스킬 디렉토리에 복사하세요:

```bash
# 스킬 디렉토리 생성
mkdir -p ~/.claude/skills/ux-writing-rule

# SKILL.md 복사
cp SKILL.md ~/.claude/skills/ux-writing-rule/SKILL.md
```

또는 직접 다운로드:

```bash
mkdir -p ~/.claude/skills/ux-writing-rule
curl -o ~/.claude/skills/ux-writing-rule/SKILL.md \
  https://raw.githubusercontent.com/zenithkim/UX-Writing-Rules/main/SKILL.md
```

## Usage

Claude Code에서 아래와 같이 호출합니다:

```
/ux-writing-rule 지금 가입하면 최대 5만원 혜택을 받을 수 있습니다
```

```
/ux-writing-rule https://example.com 무료체험 시작하기
```

Title + Description 쌍 입력 시 중복 체크(Step 5)도 자동 실행됩니다:

```
/ux-writing-rule
Title: 매일 출석하면 포인트 적립
Description: 출석 체크하고 포인트를 받아보세요
```

## Requirements

- [Claude Code](https://claude.ai/code) CLI 설치 필요
- 관련 sub-skill (선택사항):
  - `ctr-hook-writer` — CTR 최적화 (Step 4)
  - `title-description-overlap-checker` — 중복 체크 (Step 5)
  - `url-context-summarizer` — URL 맥락 요약 (Step 0)

## License

MIT
