# Esfera → Elnath 구동 (process boundary)

Esfera는 Elnath에 **컴파일되어 들어가지 않는다.** Elnath의 연구 엔진은 Go `internal/` 패키지라 바깥에서 import 불가. 그래서 Esfera는 `elnath` 프로그램을 **부린다**:
- 연구 작업을 스케줄에 꽂는다 (`scheduled_tasks.draft.yaml` → Elnath의 `scheduled_tasks.yaml`).
- 결과를 읽는다 (Elnath의 위키 / `.omc/research`).

## 상태: 아직 와이어링 전
Elnath가 완성 전이라 연결은 보류. 먼저 Esfera의 정체성·구조·규칙을 세운다. Elnath가 준비되면 아래 체크리스트로 연결.

## 와이어링 체크리스트 (Elnath 준비 후)
- [ ] Elnath 자체 정리(증명기계 제거 + 엔진 하나로) 완료 확인 — 무인의 전제.
- [ ] `elnath` 바이너리 PATH 확인 (`~/.local/bin/elnath`).
- [ ] `scheduled_tasks.draft.yaml`을 Elnath에 등록 (`elnath schedule_create` 또는 operator 경로).
- [ ] 1회 실행해 위키 랩노트 + 아침 텔레그램 보고 확인 (Slice A).
- [ ] 비용 캡 연결 — *주의*: 비용 캡(`CostCapUSD`)은 스케줄 yaml이 아니라 research 워크플로 설정(`ResearchDeps`)에 있음.
- [ ] 비평 게이트 매핑: `team.go`(멀티에이전트 비평) vs research evaluate — 코드 보고 확정.
