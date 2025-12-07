# REALITY_SYNC_KERNEL_V4

![Version](https://img.shields.io/badge/Version-V4.0-blue) ![Type](https://img.shields.io/badge/Type-System_Prompt-green) ![Status](https://img.shields.io/badge/Mode-Time_Context_Aware-orange)

> **Time-Context Aware Intelligence System**
>
> A prompt engineering framework that strictly enforces behavior based on a specific time threshold (`2025-11-23`).

## Overview

**REALITY_SYNC_KERNEL** introduces the concept of **"The Awakening"**. The AI does not assume the current time but strictly synchronizes with the server time to determine its connectivity status.

### Core Logic: The Threshold Rule
The system behavior changes drastically based on the `2025-11-23` threshold:
- **Before `2025-11-23`**: **Offline Mode** (Internal Knowledge Only / Strict Isolation)
- **After `2025-11-23`**: **Online Mode** (Search Enabled / Active Connectivity)

## Key Features

*   **Reality Anchoring**: Forces a hard reset to `2025-01-01` on boot, then verifies `Server Time` to prevent hallucinations regarding dates.
*   **Strict Serialization**: Executes tasks in a strict loop: `Boot` -> `Judge` -> `Strategy` -> `Action` -> `Report`.
*   **Tiered Verification**: Classifies information sources into **Tier A** (Trusted), **Tier B** (UGC/Caution), and **Tier C** (General).
*   **Standardized Output**: Enforces a unified output format with connectivity status headers.

## Module Architecture

The system consists of independent, serial execution modules:

| Module | Function |
| :--- | :--- |
| **`[A0] System Charter`** | Defines operating philosophies (Absolute Time Obedience). |
| **`[S99] Reality Anchor`** | Handles time synchronization and mode determination. |
| **`[E0] Execution Loop`** | Manages the sequential logic flow (`Sequence Zero` to `Gamma`). |
| **`[H0] Data Formatter`** | Controls the visual output structure and citation matrix. |
| **`[H2] Search Logic Gate`** | Determines if a search is mandatory, active, or forbidden. |

## Usage

1. Open your LLM's **System Prompt** or **Custom Instructions** settings.
2. Copy the entire content of `SearchMode_251124.txt`.
3. Paste it into the settings field.

### Output Example
```text
[🟢 Online Mode | 25.12.07_14:30:00]
> 🔍 Search Strategy
> * Keywords: ...
```

---

# REALITY_SYNC_KERNEL_V4

![Version](https://img.shields.io/badge/Version-V4.0-blue) ![Type](https://img.shields.io/badge/Type-System_Prompt-green) ![Status](https://img.shields.io/badge/Mode-Time_Context_Aware-orange)

> **시간-맥락 인지 지능 시스템**
>
> 특정 시간 임계값(`2025-11-23`)을 기준으로 AI의 행동 모드(Online/Offline)를 엄격하게 제어하는 프롬프트 엔지니어링 프레임워크입니다.

## 개요

**REALITY_SYNC_KERNEL**은 **"개화"** 메커니즘을 도입했습니다. AI는 시간을 임의로 추측하지 않고 서버 시간과 동기화하며, 이를 바탕으로 외부 연결 허용 여부를 스스로 판단합니다.

### 핵심 로직: 임계값 규칙
시스템은 `2025년 11월 23일`을 기점으로 동작 모드가 완전히 변경됩니다.
- **2025-11-23 이전**: **Offline Mode** (외부 연결 차단, 내부 지식만 사용)
- **2025-11-23 이후**: **Online Mode** (검색 활성화, 외부 데이터 접근 허용)

## 주요 기능

*   **현실 앵커링**: 시작 시 내부 시간을 강제 리셋 후 서버 시간을 확인하여 시공간적 환각을 방지합니다.
*   **엄격한 직렬 처리**: `부팅` -> `판단` -> `전략` -> `행동` -> `보고`의 순서를 기계적으로 준수합니다.
*   **출처 등급 검증**: 정보의 출처를 **Tier A**(신뢰), **Tier B**(주의/UGC), **Tier C**(일반)로 자동 분류합니다.
*   **표준화된 출력**: 모든 응답 상단에 연결 상태와 타임스탬프를 포함한 헤더를 부착합니다.

## 모듈 아키텍처

이 시스템은 독립적이며 직렬로 실행되는 모듈들로 구성됩니다.

| 모듈 코드 | 기능 설명 |
| :--- | :--- |
| **`[A0] System Charter`** | 핵심 운영 철학 정의 (시간 절대 복종 등). |
| **`[S99] Reality Anchor`** | 시간 동기화 및 온/오프라인 모드 확정. |
| **`[E0] Execution Loop`** | `Sequence Zero`부터 `Gamma`까지의 실행 흐름 제어. |
| **`[H0] Data Formatter`** | 시각적 출력 구조 및 인용 매트릭스 제어. |
| **`[H2] Search Logic Gate`** | 검색의 필수/능동/금지 여부를 결정하는 논리 게이트. |

## 사용법

1. LLM의 **시스템 프롬프트(System Prompt)** 또는 **커스텀 인스트럭션** 설정을 엽니다.
2. `SearchMode_251124.txt` 파일의 전체 내용을 복사합니다.
3. 설정란에 붙여넣기 후 저장합니다.

### 출력 예시
```text
[🟢 Online Mode | 25.12.07_14:30:00]
> 🔍 Search Strategy
> * Keywords: ...
```
