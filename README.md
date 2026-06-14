# Esfera Research

> 사람이 아니라 AI 에이전트가 연구를 수행하는 리서치 랩.
> A research lab with no human researchers — one human edits, AI agents do the science.

## 한 줄
오늘의 AI로, 평범한 사람의 하루를 실제로 도와주는 **믿을 수 있는 자율 에이전트**를 어떻게 만드는가 — 이 한 질문을 연구하고, 그 답을 **Elnath**라는 간판 제품으로 응결시킨다.

## 구조: 한 랩, 두 트랙
- **리서치 트랙** (이 repo) — 빠르고 실험적, 공개적으로 실패해도 됨. 산출 = 랩노트·데이터셋·벤치마크·논문.
- **제품 트랙 = Elnath** (별도 repo) — 느리고 신뢰성 높음, 매일 dogfood. 산출 = 실제 쓰는 자율 개인 에이전트.
- 둘을 잇는 플라이휠: 검증된 발견은 Elnath로 **졸업(graduation)**, Elnath의 dogfood 실패는 리서치 **백로그**로 역류.

## Elnath와의 관계
Esfera(랩)와 Elnath(제품)는 **별개 repo, 한 랩**이다. Esfera는 Elnath에 컴파일되어 들어가지 않고, `elnath` 프로그램을 **부려서**(스케줄에 연구 작업을 꽂고 결과를 읽어서) 돈다. → `runtime/README.md`

## 운영 원칙 (요약)
- **permissionless 내부 + 기계 게이트 perimeter**: 내부 연구는 사람 승인 없이 자유. 되돌릴 수 없는 경계(돈·발행 주장·제품 머지)만 *기계*(캡·비평정족수·테스트)가 지킨다. 사람(=PI)은 **항소심**.
- **진짜 사용이 진실**: 벤치마크 점수가 아니라 매일의 dogfood가 성공 기준. 망한 실험도 공개(`research/graveyard/`).
- → 전체: `docs/operating-model.md`, 게이트: `gates/policy.md`

## 폴더
- `MANIFESTO.md` — 랩 선언문 (KO/EN)
- `docs/` — 운영 모델 + 레퍼런스(AutoScientists 등)
- `research/` — 백로그 · 랩노트 · graveyard(실패 아카이브)
- `runtime/` — Elnath를 부리는 법 + 야간 스케줄 초안
- `gates/` — 기계 게이트 정책

## 상태
부트스트랩 단계. Elnath가 아직 완성 전이라, 이 repo는 먼저 랩의 *정체성·구조·운영규칙*을 세우고, Elnath 와이어링(`runtime/`)은 Elnath가 준비되면 연결한다.
