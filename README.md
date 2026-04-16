# UX Writing Skills for Claude Code

Claude Code에서 동작하는 UX 라이팅 검증·개선 스킬 모음입니다.

## Skills Overview

```
ux-writing-rule/          ← 범용 UX 라이팅 검증 (Base)
  SKILL.md

buzzvil-writing/          ← 버즈빌 도메인 특화 (Domain Layer)
  SKILL.md
  carrot_test1/           ← 꿀피드 C안 리라이팅 (Campaign Layer)
    SKILL.md
```

| Skill | 호출 방법 | 설명 |
|-------|-----------|------|
| **ux-writing-rule** | `/ux-writing-rule` | 토스 UX 라이팅 원칙 8가지 기반 문구 검증·개선 |
| **buzzvil-writing** | `/buzzvil-writing` | 버즈빌 광고 소재·인앱 메시징·리워드 문구 검증 |
| **carrot_test1** | `/carrot-test1` | 꿀피드 C안 템플릿 기준 광고 소재 리라이팅 |

---

## 1. ux-writing-rule (Base Skill)

입력 문구를 **5단계 파이프라인**으로 검증하고 최적화하는 범용 UX 라이팅 스킬.

### 검증 파이프라인

| Step | 역할 | 설명 |
|------|------|------|
| Step 0 | URL 맥락 요약 | URL 입력 시 페이지 크롤링 후 제품·타겟·톤 맥락 추출 |
| Step 1 | 원칙 분석 | UX 라이팅 원칙 8가지 준수 여부 검사 |
| Step 2 | 개선 추천 | 위반 원칙에 대한 개선 문구 1~3개 추천 |
| Step 3 | 재검증 | 추천 문구를 다시 원칙 8가지로 검증 |
| Step 4 | CTR 최적화 | 마케팅 심리 트리거 적용 (FOMO, 사회적 증명 등) |
| Step 5 | 중복 체크 | Title/Description 쌍의 어휘·의미·역할 중복 탐지 |

### UX 라이팅 원칙 8가지

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

### 분석 프레임워크

- **프레이밍 효과 기법 3가지**: 진입 장벽 해소(F1), 가능성 프레이밍(F2), 이득 중심 프레이밍(F3)
- **UX 심리학 법칙 10가지**: 힉의 법칙, 밀러의 법칙, 포스텔의 법칙, 피크엔드 법칙, 폰 레스토프 효과, 제이콥의 법칙, 테슬러의 법칙 등
- **마케팅 심리 트리거 7가지**: FOMO, 긴급성, 희소성, 사회적 증명, 손실 회피, 호기심 격차, 즉시 보상

### 사용 예시

```
/ux-writing-rule 지금 가입하면 최대 5만원 혜택을 받을 수 있습니다
```

```
/ux-writing-rule
Title: 매일 출석하면 포인트 적립
Description: 출석 체크하고 포인트를 받아보세요
```

---

## 2. buzzvil-writing (Domain Layer)

`ux-writing-rule`을 기반으로, 버즈빌 제품(BuzzBenefit/BuzzAd)에 특화된 **12가지 원칙**(UX 8 + 버즈빌 4)으로 문구를 검증합니다.

### 버즈빌 전용 원칙 (B 원칙)

| # | 원칙 | 기준 |
|---|------|------|
| B1 | 리워드 명확성 | 적립 포인트·혜택을 구체적 수치로 명시했는가? |
| B2 | 과금 모델 정합성 | CPC/CPA/CPQ에 맞는 행동을 유도하는가? |
| B3 | 참여 허들 최소화 | "~만 하면" 형태로 행동 비용을 낮게 인식시키는가? |
| B4 | 광고 피로도 고려 | 반복 노출 시 변주 가능한 문구인가? |

### 과금 모델별 문구 전략

| 과금 모델 | 목적 | CTA 방향 |
|----------|------|---------|
| **CPC** (클릭당) | 클릭 유도 | "자세히 보기", "확인하기" |
| **CPA** (행동당) | 전환 유도 | "지금 가입하기", "다운로드" |
| **CPQ** (쿼리당) | 참여 유도 | "참여하기", "응답하기" |

### 문구 유형별 가이드

| 유형 | 종류 | 권장 길이 |
|------|------|----------|
| 광고 소재 | Title / Description / CTA | 15~25자 / 25~45자 / 2~6자 |
| 인앱 메시징 | 푸시 / 배너 / 툴팁 / 바텀시트 | ~40자 / ~20자 / ~30자 / 15+60자 |
| 리워드 | 적립 완료 / 미션 안내 / 출석 체크 | ~15자 / ~25자 / ~20자 |

### 섹션 타이틀 자동 워싱

Unit ID를 입력하면 Ad Type Filters와 Ad Categories를 기반으로 최적의 섹션 타이틀을 자동 생성합니다.

```
/buzzvil-writing Unit ID: 422455685728323 섹션 타이틀 생성
```

### 사용 예시

```
/buzzvil-writing CPA 광고 소재: 지금 가입하면 포인트를 드려요
```

```
/buzzvil-writing
유형: 리워드 메시징
문구: 미션 완료! 보상이 지급되었습니다
```

---

## 3. carrot_test1 (Campaign Layer)

꿀피드 광고 소재를 **C안 템플릿**(Title + 후킹태그) 기준으로 자동 리라이팅합니다.

### C안 템플릿 구조

```
┌─────────────────────────────────────────────┐
│ [아이콘]  [Title]                   [포인트P]│
│           [후킹태그 (파란색)]                 │
└─────────────────────────────────────────────┘
```

| 슬롯 | 규칙 | 길이 |
|------|------|------|
| Title | `[브랜드 축약] + [액션]하기` | 15자 이내 |
| 후킹태그 | 조건 유도형 `~만하면` 또는 시간형 `~이면 끝` | 6자 이내 |
| 포인트 | 숫자 + "P" | — |

### 변환 사례

| AS-IS | C안 Title | 후킹태그 | 포인트 |
|-------|----------|---------|--------|
| KB국민 노리2 체크카드 미션 참여하면 | KB 체크카드 발급하기 | 최대 5분 | 11,250P |
| 쿠팡 로켓그로스 유튜브 구독하면 | 쿠팡 유튜브 구독하기 | 쉽고 빨리 | 100P |
| 투썸플레이스 카카오톡 채널 추가하면 | 투썸 카톡 채널 추가하기 | 쉽고 빨리 | 100P |

### 사용 예시

```
/carrot-test1
Title: 반려견 행복지수 높이기
Description: 미션 참여하면
포인트: 450P
```

---

## 스킬 계층 구조

```
ux-writing-rule (Base)
│
│  8가지 UX 원칙 + 프레이밍 기법 + 심리학 법칙
│  → 범용. 어떤 UX 문구에도 적용 가능
│
└── buzzvil-writing (Domain)
    │
    │  + B1~B4 버즈빌 원칙 (리워드·과금모델·허들·피로도)
    │  + 과금 모델별 전략 (CPC/CPA/CPQ)
    │  + 문구 유형별 가이드 (광고/인앱/리워드)
    │  → 버즈빌 제품 전체에 적용
    │
    └── carrot_test1 (Campaign)
        │
        │  + C안 템플릿 규칙 (Title 15자 + 후킹태그 6자)
        │  + 브랜드 축약 규칙
        │  + 후킹태그 자동 분류
        │  → 꿀피드 특정 캠페인에 적용
```

각 하위 스킬은 상위 스킬의 원칙을 `@reference`로 상속받아 사용합니다.

---

## Installation

### 전체 설치 (3개 스킬 모두)

```bash
# 디렉토리 생성
mkdir -p ~/.claude/skills/ux-writing-rule
mkdir -p ~/.claude/skills/buzzvil-writing/carrot_test1

# 파일 복사
curl -o ~/.claude/skills/ux-writing-rule/SKILL.md \
  https://raw.githubusercontent.com/zenithkim/UX-Writing-Rules/main/SKILL.md

curl -o ~/.claude/skills/buzzvil-writing/SKILL.md \
  https://raw.githubusercontent.com/zenithkim/UX-Writing-Rules/main/buzzvil-writing/SKILL.md

curl -o ~/.claude/skills/buzzvil-writing/carrot_test1/SKILL.md \
  https://raw.githubusercontent.com/zenithkim/UX-Writing-Rules/main/buzzvil-writing/carrot_test1/SKILL.md
```

### Base만 설치 (ux-writing-rule)

```bash
mkdir -p ~/.claude/skills/ux-writing-rule
curl -o ~/.claude/skills/ux-writing-rule/SKILL.md \
  https://raw.githubusercontent.com/zenithkim/UX-Writing-Rules/main/SKILL.md
```

## Requirements

- [Claude Code](https://claude.ai/code) CLI 설치 필요
- 관련 sub-skill (선택사항):
  - `ctr-hook-writer` — CTR 최적화 (Step 4)
  - `title-description-overlap-checker` — Title/Description 중복 체크 (Step 5)
  - `url-context-summarizer` — URL 맥락 요약 (Step 0)

## License

MIT
