# 레퍼런스 — 무엇을 훔치고 무엇을 피하나

## 연구조직 / 자율과학
- **AutoScientists** (Harvard, arXiv 2605.28655) — 자기조직 에이전트 팀이 장기 과학실험. 훔칠 것: ① **critique-before-compute**(돈 쓰기 전 비평), ② **실패 공유 메모리**(dead-end), ③ 자기조직 + 정체 시 재조직. 피할 것: **permissionless 집행** → Esfera는 기계 게이트 유지.
- **Kimi Agent Swarm** (Moonshot K2.5/K2.6) — 학습된 오케스트레이터 + 동결 서브에이전트, 300 에이전트·4000 스텝. 훔칠 것: 똑똑한 오케스트레이터 1 + 값싼 워커 다수. 경계할 것: **직렬붕괴**·**가짜병렬**(에이전트 난사 = slop).
- **Sakana "The AI Scientist" v2** — 첫 AI 논문 피어리뷰 통과(Nature, 2026.3). 의미: 무인 연구가 *진짜 발행*까지 가능.
- **Google "AI co-scientist"** — Gemini 멀티에이전트, 가설 생성·토론·진화 (인간 협업형).
- **Autoscience** — 자율 연구랩 스타트업, $14M 시드(2026.3). 경쟁자, 단 ML 중심.

## Esfera의 차별점
위 시스템들은 대부분 *AI/ML/과학 자체*를 연구한다(레드오션). Esfera의 대상은 **비개발자의 하루를 돕는 에이전트**(Elnath) — 진짜 제품 + 진짜 사용자에 묶인, 덜 붐비는 wedge. 자율성 축에서도 Sakana(완전자동)와 Google(인간협업) **사이**: "있을 땐 PI, 없을 땐 무인".

## 링크
- AutoScientists: https://arxiv.org/abs/2605.28655 · https://github.com/mims-harvard/AutoScientists
- Kimi K2.6 Agent Swarm: https://www.marktechpost.com/2026/04/20/moonshot-ai-releases-kimi-k2-6-with-long-horizon-coding-agent-swarm-scaling-to-300-sub-agents-and-4000-coordinated-steps/
- Sakana AI Scientist (Nature): https://sakana.ai/ai-scientist-nature/
- Google AI co-scientist: https://deepmind.google/blog/co-scientist-a-multi-agent-ai-partner-to-accelerate-research/
- Autoscience: https://siliconangle.com/2026/03/19/autoscience-builds-automated-research-lab-machine-learning-models-14m/

## 플러밍 레퍼런스 (Elnath 제품 쪽, Esfera 연구조직엔 덜 직결)
Codex(샌드박스/승인), Claude Code(hooks/permission UX/KAIROS 저소음 능동성), Hermes(MCP sampling·kanban swarm), Oh My Pi(해시앵커 안전편집), GitHub MCP, Open Computer Use, Pipedream.
