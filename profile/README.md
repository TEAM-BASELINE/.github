<div align="center">
  
  # AgentSec Twin
  
</div>
<div align="center">
  AI 에이전트의 권한 경로를 시뮬레이션하는 Security Ontology 기반 디지털 트윈
</div>
<div align="center">
  　
</div>
<div align="center">
  
<img width="800" height="450" alt="Animation1" src="https://github.com/user-attachments/assets/b71c7d31-0274-45aa-af09-3ef61e9206b3" />
</div>




---
## ✍️프로젝트 개요
- 프로젝트명: AgentSec Twin
- 프로젝트 기간 2026-04-01~2026-05-26
- 핵심 목적: AI 에이전트 도입 전후의 보안 영향과 경로 변화를 시뮬레이션해 의사결정을 지원
- 주요 사용자: 보안 담당자, 플랫폼 운영자, AI 도입을 검토하는 개발/운영 조직
- 핵심 차별점: 사람, AI, 도구, 데이터, 시크릿, 정책, MCP 서버를 하나의 보안 온톨로지로 모델링
---
## ✍️프로젝트 소개
AI 에이전트가 실제 업무 도구와 SaaS에 연결되기 시작하면서 보안 검토의 초점도 단순 권한 점검에서 AI 에이전트의 도달 경로를 관측하는 일로 이동하고 있다.  
AgentSec Twin은 이 문제를 해결하기 위해 사람, AI, 도구, 데이터, 비밀정보, 정책, MCP 서버 연결을 보안 온톨로지로 모델링하고, 사건을 주입해 결과를 시뮬레이션하는 웹 기반 MVP다.

이 프로젝트는 다음과 같은 질문에 답하는 것을 목표로 한다.
- 이 AI 에이전트에게 특정 권한을 주면 어디까지 도달할 수 있는가?
- 담당자가 퇴사하거나 소유권이 바뀌면 어떤 연결이 ownerless 상태가 되는가?
- 시크릿 또는 링크 하나가 노출되면 어떤 자산까지 연쇄 확산되는가?
- 정책을 바꾸면 어떤 경로가 닫히고 어떤 위험은 그대로 남는가?
- MCP 서버를 연결했을 때 새롭게 열리는 접근 경로와 외부 반출 경로는 무엇인가?
---
## ✍️무엇을 해결하는가

기존 보안 도구는 탐지와 차단에는 강하지만 권한과 연결 구조가 만드는 실제 경로를 사전에 계산하고 비교하는 경험은 약하다.  
AgentSec Twin은 이 공백을 메우기 위해 다음 흐름으로 동작한다.
1. 조직의 사람, AI, 자산, 도구, 정책, 시크릿, MCP 서버를 그래프로 모델링한다.
2. 권한 부여, 퇴사, 시크릿 노출, MCP 서버 연결 같은 사건을 주입한다.
3. 사건 전후의 접근 경로, 도달 가능한 중요 자산, 외부 반출 가능성을 계산한다.
4. 결과를 그래프, diff, 자연어 리포트로 함께 제시해 의사결정을 돕는다.
---
## 📌핵심 기능

### 1. Workspace Home

- 합성 조직 템플릿 기반 워크스페이스 진입
- 주요 에이전트, 자산, 최근 실행 내역 요약

### 2. Ontology Builder

- 사람, AI, 도구, 데이터, 시크릿, 정책, 자산을 객체/관계 단위로 모델링
- 보안 디지털 트윈 구조를 시각적으로 확인

### 3. Agent Catalog

- 에이전트별 권한, 소유자, 연결 도구, 위험 상태 조회
- 어떤 AI가 어떤 경로를 통해 자산에 도달할 수 있는지 확인

### 4. Scenario Studio

- 사건 유형 선택 및 입력값 설정
- 권한 추가, 소유권 변경, 시크릿 노출, MCP 서버 연결 시나리오 실행

### 5. Run Summary / Graph / Diff / Report / Evidence

- 시뮬레이션 결과 요약
- 새롭게 열린 경로와 영향 범위 시각화
- 정책 변경 전후 차이 비교
- 설명형 자연어 리포트와 근거 제공
---
## 대표 시뮬레이션 시나리오
- `grant`: AI 에이전트에 권한을 부여했을 때 새롭게 열리는 접근 경로를 계산
- `offboarding`: 퇴사 또는 소유권 변경 이후 ownerless 연결과 잔여 위험을 확인
- `secret_exposure`: 시크릿/링크 노출 시 확산 가능한 경로와 도달 자산을 분석
- `mcp_attachment`: MCP 서버 연결 시 도구 접근 범위, 자격 증명 의존성, 외부 반출 가능 경로를 시뮬레이션
---
## 프로젝트의 차별점
| 비교 관점 | 일반 보안 도구 | AgentSec Twin |
| --- | --- | --- |
| 중심 질문 | 공격을 탐지/차단하는가 | 이 권한과 연결이 어떤 경로를 여는가 |
| 핵심 방식 | 이벤트 탐지, 정책 집행 | 상태 모델링, 사건 주입, 경로 계산, diff 비교 |
| 결과 형태 | 경보, 차단 로그 | 그래프, 영향 범위, 정책 전후 차이, 자연어 리포트 |
| AI 보안 맥락 | 개별 이벤트 대응 중심 | AI 권한, 소유권, 시크릿, MCP 서버를 함께 고려 |
---
## 🧑‍💻팀원 소개
| 이름  | 역할  |
| --- | --- |
| 유희현 | 팀장/PM, FE/BE, AI |
| 권준현 | FE/BE, Infra |
| 이서현 | BE, QA, 보안 연구 |
---
## ⚙️기술 스택
| 영역  | 기술  |
| --- | --- |
| Frontend | Next.js 16, React 19, TypeScript, Tailwind CSS, React Flow, Dagre |
| Backend | FastAPI, Pydantic, SQLAlchemy, Uvicorn |
| Data / Storage | 합성 워크스페이스 시드, 관계형 저장소(PostgreSQL 기준 설계), 리포트/온톨로지 규약 패키지 |
| Analysis | 그래프 기반 경로 분석, 정책 diff, 시나리오 실행 엔진 |
| AI / Explain | OpenAI-compatible API 연동 구조, 자연어 결과 요약 리포트 |
| Infra / Tooling | npm workspace, Python virtualenv, Docker 기반 백엔드 실행 옵션 |
---

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/418ab2fa-9d61-4a4a-b2b3-33179e13bd5f" />

