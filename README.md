# Search Mode V4 for Gemini

![Version](https://img.shields.io/badge/Version-V4.0-blue) ![Type](https://img.shields.io/badge/Type-Gemini_System_Prompt-green) ![Status](https://img.shields.io/badge/Status-Online%2FOffline_Context_Aware-orange)

> **Reality-anchored search prompt for Gemini**
>
> A search-focused system prompt that switches between Offline Mode and Online Mode based on a fixed time threshold, forces explicit verification, and formats search output in a consistent way.

## Overview

This version is the current Gemini variant of Search Mode.

It does not assume the current date or live connectivity from intuition. It first synchronizes against `Server Time`, decides whether it is in Offline Mode or Online Mode, and then follows a strict search-and-verification flow.

### Threshold Rule

- Before `2025-11-23`: `Offline Mode`
- On or after `2025-11-23`: `Online Mode`

In Offline Mode, external search is blocked and the model must stay within internal knowledge boundaries.

In Online Mode, freshness-sensitive questions must use external search.

## Key Features

- **Reality anchoring**
  - Resets internal time, checks actual `Server Time`, and uses that as the only time anchor.

- **Online / Offline split**
  - The prompt explicitly separates internal-knowledge mode and external-search mode.

- **Required tool flow in Gemini**
  - Uses `google_search` for web search.
  - Uses `google:ds_python_interpreter` for verification checks.
  - Treats both as required work tools when available.

- **Fixed core meta headers**
  - Keeps `Online Mode`, `Offline Mode`, `Research Mode`, and `Search Strategy` in fixed English format.

- **Localized time display**
  - The visible timestamp is rendered in the user's local timezone.
  - Example: Korean users may see `KST`; other users see their own local timezone abbreviation when available.

- **Structured search output**
  - Search-backed answers are expected to include strategy, status, answer body, and source appendix in a fixed order.

- **Research mode**
  - Academic or evidence-heavy requests trigger a deeper literature-oriented search path.

- **Source quality marking**
  - Uses visual trust markers such as `🏛️`, `🛡️`, and `⚠️`.

- **Exact source linking**
  - Source links must point to the exact page actually checked.
  - Homepage-only or generic root links are not sufficient.

## Output Format

The prompt is designed around a stable header style.

### Example

```text
[🟢 Online Mode | 26.04.01_15:13:40 KST]
> 🔍 Search Strategy
> * Keywords: [ ... ]
> * Focus: [ ... ]
[🌐 Search Applied: ...]
### 🔗 Verified Sources
```

Notes:

- `Online Mode`, `Offline Mode`, `Research Mode`, and `Search Strategy` remain fixed in English.
- The timestamp follows `YY.MM.DD_HH:MM:SS ZONE`.
- Status tags and source heading may localize depending on the answer language.

## Gemini Usage

1. Open your Gemini Gem instructions or system prompt field.
2. Copy the entire content of [SearchMode_260214_en1.md](/C:/Users/Lemos/Desktop/새 폴더 (19)/SearchMode_260214_en1.md).
3. Paste it directly into the instruction field.

Important:

- Do not attach the prompt file as knowledge.
- Paste the full text directly into the instruction field.

## Recommended Usage

- Best for live lookup, current facts, document checking, source collection, and research-style tasks.
- Useful when you want stronger date awareness and clearer source reporting.
- Especially useful when you want the model to search first and verify before concluding.

## Cautions

- This is a search-oriented prompt, not a general conversation prompt.
- Even with stronger guardrails, cross-checking is still recommended for legal, medical, financial, and quotation-heavy material.
- If the model returns broad homepage links, ask again for the exact page that was actually checked.
- Very common or stable questions may not trigger external search unless you explicitly request search.

## Tips

1. You can explicitly ask for deeper cross-checking.
   - Example: `Cross-check this again` or `Re-verify the cited case in depth`.

2. You can ask for internal knowledge and external results separately.

3. If you strongly require external sources, say so directly.

4. For heavy verification, a fresh session can be cleaner than continuing a long search thread.

5. This prompt works best when the task is search-first rather than freeform brainstorming.

---

# Gemini용 Search Mode V4

![Version](https://img.shields.io/badge/Version-V4.0-blue) ![Type](https://img.shields.io/badge/Type-Gemini_System_Prompt-green) ![Status](https://img.shields.io/badge/Status-Online%2FOffline_Context_Aware-orange)

> **현실 앵커 기반 Gemini 검색 프롬프트**
>
> 고정된 시간 임계값을 기준으로 Offline Mode와 Online Mode를 전환하고, 검색과 검증을 구조적으로 수행하도록 설계된 검색 특화 시스템 프롬프트입니다.

## 개요

이 문서는 Search Mode의 최신 Gemini 버전 안내입니다.

이 프롬프트는 현재 시점과 연결 상태를 감으로 추정하지 않습니다. 먼저 `Server Time`을 확인해 현재 모드를 결정하고, 그 다음 검색과 검증 흐름을 엄격하게 수행합니다.

### 임계값 규칙

- `2025-11-23` 이전: `Offline Mode`
- `2025-11-23` 이후: `Online Mode`

Offline Mode에서는 외부 검색이 닫히고, 내부 지식 범위 안에서만 답해야 합니다.

Online Mode에서는 최신성이 필요한 질문에 반드시 외부 검색을 동원합니다.

## 주요 특징

- **현실 앵커링**
  - 내부 시간을 리셋한 뒤 실제 `Server Time`을 확인하고, 그 값을 기준으로 동작합니다.

- **온라인 / 오프라인 분기**
  - 내부지식 중심 모드와 외부검색 모드를 명확히 구분합니다.

- **Gemini 전용 도구 흐름**
  - 웹 검색은 `google_search`
  - 검증 체크는 `google:ds_python_interpreter`
  - 두 도구가 가능하면 선택이 아니라 필수 작업 도구로 취급합니다.

- **고정 메타헤더 유지**
  - `Online Mode`, `Offline Mode`, `Research Mode`, `Search Strategy`는 영어 고정 형식으로 유지됩니다.

- **지역 시간대 표시**
  - 보이는 시간은 사용자 지역 시간대로 렌더링됩니다.
  - 예를 들어 한국 사용자는 `KST`가 표시될 수 있고, 다른 국가는 그 지역 약칭이 표시됩니다.

- **구조화된 검색 출력**
  - 검색 기반 응답은 전략, 상태, 본문, 출처 블록을 일정한 순서로 따르도록 설계되어 있습니다.

- **리서치 모드**
  - 학술자료나 근거 중심 질문에서는 더 깊은 자료 조사 흐름이 활성화됩니다.

- **출처 신뢰도 마커**
  - `🏛️`, `🛡️`, `⚠️` 같은 표시로 출처 성격을 구분합니다.

- **정확한 링크 요구**
  - 출처는 실제 확인한 정확한 페이지 링크여야 합니다.
  - 메인 홈페이지나 루트 주소만 제시하는 것은 충분하지 않습니다.

## 출력 형식

이 프롬프트는 고정된 상단 형식을 중심으로 설계되어 있습니다.

### 예시

```text
[🟢 Online Mode | 26.04.01_15:13:40 KST]
> 🔍 Search Strategy
> * Keywords: [ ... ]
> * Focus: [ ... ]
[🌐 웹 서치 적용: ...]
### 🔗 참조 출처
```

참고:

- `Online Mode`, `Offline Mode`, `Research Mode`, `Search Strategy`는 영어 고정입니다.
- 시간 형식은 `YY.MM.DD_HH:MM:SS ZONE` 입니다.
- 상태 태그와 출처 헤더는 응답 언어에 따라 현지화될 수 있습니다.

## Gemini 적용 방법

1. Gemini Gem의 지침란 또는 시스템 프롬프트 입력란을 엽니다.
2. [SearchMode_260214_en1.md](/C:/Users/Lemos/Desktop/새 폴더 (19)/SearchMode_260214_en1.md) 전체를 복사합니다.
3. 그대로 붙여넣습니다.

중요:

- 지식 파일로 첨부하지 말고, 반드시 본문 전체를 직접 붙여넣으세요.

## 추천 용도

- 최신 정보 확인
- 현재 사실 검증
- 문서 확인
- 출처 수집
- 리서치형 질의

특히 “먼저 검색하고, 그 다음 검증해서 답하게 하고 싶을 때” 잘 맞습니다.

## 주의

- 검색 특화 프롬프트이지, 일반 대화용 프롬프트는 아닙니다.
- 법률, 의료, 금융, 인용 중심 자료는 여전히 교차검증을 권장합니다.
- 메인 홈페이지처럼 뭉뚱그린 링크가 나오면, 실제로 확인한 상세 링크를 다시 요구하는 것이 좋습니다.
- 너무 상식적인 질문은 외부 검색이 자동으로 작동하지 않을 수도 있습니다.

## 팁

1. 교차검증을 다시 요구할 수 있습니다.
   - 예: `다시 교차검증해줘`, `인용한 판례를 더 깊게 재검증해줘`

2. 내부지식과 외부검색 결과를 분리해서 요청할 수 있습니다.

3. 외부검색을 강하게 요구하고 싶으면 명시적으로 말하는 편이 좋습니다.

4. 검증량이 많아질수록 새 세션에서 다시 점검하는 편이 더 깔끔할 수 있습니다.

5. 이 프롬프트는 자유 대화보다 검색 우선 작업에 더 적합합니다.
