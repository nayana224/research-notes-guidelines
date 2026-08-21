# Research Notes Guidelines

AI와 함께 연구 내용을 Notion 등 note-taking system에 **나중에 다시 봐도 빠르게 이해할 수 있는 형태로 정리**하기 위한 instruction repository입니다.

핵심 원칙은 두 가지입니다.

1. **Understanding precedes note-taking.** 충분히 이해하기 전에 note template에 맞춰 억지로 압축하지 않습니다.
2. **페이지 상단은 미래의 내가 빠르게 다시 이해하기 위한 요약, 하단은 현재 공부를 위한 상세 기록**으로 구성합니다.

## Scope

이 저장소는 연구 지식을 구조화하고 다시 찾기 쉽게 만드는 규칙을 다룹니다.

현재 중심 작업은 research paper를 Notion의 Paper Library에 정리하는 것입니다.

포함:

- Paper Library database 구조
- 논문 page template
- 핵심 정보와 상세 노트의 계층화
- Paper states / Interpretation / Question / Research Idea 구분
- Claim ↔ Evidence 정리
- 내 연구와의 연결
- Concept / Project relation 설계

포함하지 않음:

- 논문 자체를 읽고 이해하는 방법
- coding 규칙
- 발표/PPT 작성 규칙
- 일반적인 Notion UI 사용법
- 과도한 productivity system 설계

논문 이해 자체는 `paper-understanding-guidelines`에서 담당하고, 이 저장소는 **이해된 내용을 재사용 가능한 연구노트로 만드는 방법**에 집중합니다.

## Structure

```text
research-notes-guidelines/
├── README.md
├── AGENTS.md
└── skills/
    └── paper-notes/
        └── SKILL.md
```

## Recommended workflow

```text
Research paper
  ↓
paper-understanding-guidelines
  ↓
Sufficient understanding
  ↓
Final synthesis
  ↓
research-notes-guidelines
  ↓
Paper Library / Concept Notes / Project Notes
```

## Recommended Notion structure

```text
Research
├── 📚 Paper Library
├── 🧠 Concept Notes
└── 🧪 Projects
```

### Paper Library

논문 한 편당 하나의 database item을 둡니다.

기본 property는 실제 검색과 filtering에 필요한 것만 둡니다.

- `Title`
- `Status`
- `Year`
- `Venue`
- `Topic`
- `Project` relation
- `Concepts` relation
- `URL`
- `PDF`
- `Relevance`

Authors, citation count, publisher, read date 같은 metadata는 실제로 반복 사용하지 않는 한 기본 property로 만들지 않습니다.

## Canonical paper page structure

```text
# Paper Title

One-line Takeaway

## 1. At a Glance
## 2. Paper Map
## 3. Method
## 4. Key Figures & Equations
## 5. Experiments
## 6. Related Work & Positioning
## 7. My Understanding
## 8. Limitations / Open Questions
## 9. Research Connection

## Detailed Study Notes
```

상세 규칙은 [`skills/paper-notes/SKILL.md`](skills/paper-notes/SKILL.md)를 따릅니다.

## How to use

논문을 충분히 이해한 뒤:

> 이 논문을 research-notes-guidelines 기준으로 Notion Paper Library용으로 정리해줘. 위쪽은 30초 안에 다시 이해할 수 있게 간결하게 만들고, 상세 공부 기록은 아래쪽에 분리해줘.

내 연구와 연결할 때:

> Paper states와 내 interpretation을 구분하고, Directly reusable / Requires adaptation / Not suitable / Research ideas / Next questions로 나눠줘.
