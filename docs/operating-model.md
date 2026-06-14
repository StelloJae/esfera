# Esfera 운영 모델

랩을 *조직도*가 아니라 *루프*로 운영한다.

## 한 라운드 (야간, 무인)
1. **백로그** → 주제 N개: Elnath dogfood 실패 + 시드 질문 + wildcard 1칸. (`research/backlog.md`)
2. **자기조직 팀**: 각 주제로 가설 에이전트들이 병렬 팀을 짠다 (AutoScientists식).
3. **비평 게이트 (critique-before-compute)**: 컴퓨트(돈) 쓰기 전 서로 비평 → 약한 가설 탈락. anti-slop + 비용절감.
4. **실험**: 통과한 가설만 `elnath`를 구동해 샌드박스에서 실행. 비용 캡.
5. **평가 → dead-end 공유메모리**: 채점, 실패는 공유 메모리에 기록(중복 차단·정체 시 재조직), 백로그로 역류.
6. **출력 두 갈래** (기계 게이트):
   - 공개(web): 과정·실패는 자유, *주장*만 비평 정족수 통과 후.
   - Elnath main: 그린 테스트 + 비평 통과해야 졸업 머지.

사람(PI)은 게이트가 막히거나 애매할 때만 아침 큐에서 본다 = **항소심**.

## 두 트랙 (한 랩)
리서치 트랙(빠름·실패OK) ↔ 제품 트랙 = Elnath(신뢰·dogfood). 졸업 + 역류 플라이휠. 별개 조직이 아니라 한 랩의 두 산출 트랙(품질 바·청중만 다름).

## v0 → v1 빌드 순서
- **사전**: Elnath 자체 정리(증명기계 제거 + 엔진 하나로) — 무인의 전제.
- **A**: `elnath` 스케줄에 research task 1개 → 랩노트 + 아침 보고 1회. (단일 루프)
- **B**: 백로그 + portfolio(2 grounded + 1 wildcard).
- **C**: 비평 게이트 + dead-end 공유메모리 → 팀으로. (= v1)
- **D**: 출력 두 갈래 + 기계 게이트.
- **E**: 공개 web surface.

## 확인 대기 (정직)
- 비평 게이트 = Elnath `team.go`(멀티에이전트 비평) vs research evaluate — 무엇으로 구현? (Elnath 완성 후 매핑)
- scheduled `research` task end-to-end (Slice A에서 1회 실행으로 검증)
