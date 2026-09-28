# Preclinical-to-Clinical Dose Design System

전임상 동물 데이터로부터 인체 등가 용량(HED)과 최대 권장 시작 용량(MRSD)을 계산하고, Phase 1/2 시험 설계와 용량 증량 전략을 한 화면에서 설계하는 웹 도구입니다.

*A web tool that translates preclinical animal data into human equivalent doses (HED) and a maximum recommended starting dose (MRSD), and drafts Phase 1/2 designs and dose-escalation strategies in one screen.*

> [!WARNING]
> **본 도구는 전임상 및 임상 관련 연구용입니다.** 실제 인체 투여 용량 결정이나 진단·치료 등 의료 행위의 근거로 사용할 수 없으며, 모든 결과는 반드시 전문가의 검토를 거쳐야 합니다.
>
> **For preclinical and clinical research use only.** It must not be used as the basis for actual human dosing decisions, diagnosis, treatment, or any other medical practice, and all results must be reviewed by qualified experts.

## 사용법

설치가 필요 없습니다.

1. 이 저장소의 [`index.html`](index.html)을 내려받습니다.
2. 브라우저(Chrome, Edge, Safari, Firefox)로 엽니다.

파일 하나에 모든 코드와 차트 라이브러리가 들어 있어 **인터넷 연결 없이도 작동**합니다.

## 주요 기능

**전임상 → 인체 용량 환산**
- 마우스, 랫드, 개, 원숭이의 NOAEL · MED · ED50 · STD10 / HNSTD 입력
- 체표면적(Km) 기반 HED 환산과 가장 민감한 종 자동 선택
- 안전계수(SF) 적용 MRSD 계산, 독성 우려사항에 따른 SF 가중
- 적응증별 경로: 건강인 대상 / 환자 대상 / 항암제(STD10/10 또는 HNSTD/6) / 바이오의약품(MABEL)

**임상 시험 설계**
- Phase 1a SAD: 코호트별 용량, 제형 조합, 위약 배정, 센티넬 투여
- Phase 1b MAD: 반복 투여, 정상상태(Css), 축적비(Rac), 부하 용량
- 용량 증량 방식: Modified Fibonacci · 3+3 Design · Accelerated Titration
- 코호트별 DLT 체크 → MTD, MAD, PK, Phase 2 용량 자동 재계산
- 식이 영향 PK 시험, Phase 2 용량군(저·중·고용량, RP2D) 제안
- 경구 / 정맥(IV) / 피하(SC) / 근육(IM) 투여 경로와 제형 규격 설정

**결과 확인과 내보내기**
- 용량 증량 곡선, 종별 HED 비교 차트, 인체 용량 범위 시각화
- 분석 결과에 따른 권고 사항
- CSV 내보내기, 시험 프로토콜 초안(텍스트), 인쇄 / PDF
- 샘플 데이터 10종: 이상적 · 항암제 · 펩타이드 · mAb · CNS · 심혈관 · 항생제 · 면역 · 당뇨 · 천연물

**다국어:** 한국어 · English · 日本語 · 中文. 화면 상단에서 언어를 바꿀 수 있고, 차트와 내보내기 파일에도 선택한 언어가 적용됩니다.

## 계산 근거

- HED 환산: FDA Guidance for Industry, *Estimating the Maximum Safe Starting Dose in Initial Clinical Trials for Therapeutics in Adult Healthy Volunteers* (2005)
  - Km 계수: 마우스 3, 랫드 6, 원숭이 12, 개 20, 사람 37
  - HED (mg/kg) = 동물 용량 (mg/kg) × (동물 Km ÷ 사람 Km)
- MRSD = HED(NOAEL) ÷ 안전계수(기본 10)
- 항암제 시작 용량: 설치류 STD10의 1/10 또는 비설치류 HNSTD의 1/6 (ICH S9가 권고하는 방식)

## 데이터와 개인정보

- 모든 계산은 브라우저 안에서만 이루어지며, 입력값은 어디로도 전송되지 않습니다.
- 입력값과 언어 설정은 사용 중인 브라우저의 로컬 저장소(localStorage)에만 저장됩니다.

## 기술 정보

- 단일 HTML 파일(HTML · CSS · JavaScript)
- 차트: [Chart.js](https://www.chartjs.org) 4.4.1 (MIT License). 파일 안에 포함되어 있으며 라이선스 표기를 유지합니다.

## 문의

SEIHWAN Inc. · seihwan2022@gmail.com

© 2025 SEIHWAN Inc. All rights reserved.
