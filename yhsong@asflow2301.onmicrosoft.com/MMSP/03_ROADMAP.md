# 03 ROADMAP — MMSP

## Phase 1 — Existing Workbook Analysis

Status: Substantially analyzed

- 기존 관리대장 구조 파악
- `PQ-영업`과 `PO` 역할 확인
- 수식 의존 영역과 수작업 진행정보 영역 구분
- 업무키 `NO` 중복 확인
- Access 내부키 `PO_ID` 필요성 결정

## Phase 2 — Access Persistence Prototype

Status: In progress

목표:

- Access DB 스키마 초기화
- Excel VBA에서 Access 연결 확인
- TEST 레코드 저장
- Excel 종료/재실행 후 저장 데이터 재조회

현재 검증 예정 순서:

1. `test/01_InitDatabase.vbs` 실행
2. `PO_Client.xlsm`에 prototype VBA module import
3. `MMSP_TestConnection`
4. `MMSP_TestPersistence`
5. Excel 재실행 후 `MMSP_ShowLatestTest`

## Phase 3 — Real Workbook Data Model

Status: Not started

- 실제 PO Source 구조를 Access schema로 매핑
- 진행정보 필드 구조 확정
- 기존 데이터 migration 전략 수립
- 계산 로직의 Excel → Access 이동 범위 결정

## Phase 4 — SharePoint Synchronization

Status: Not started

- 최신 중앙 DB 취득
- 변경사항 delta 저장
- 버전 관리
- lock / stale lock 처리
- 동시 저장 및 충돌 검증
- SharePoint 환경에서 가능한 atomic update 방식 검증

## Phase 5 — User Client

Status: Not started

- 일반 사용자용 Load/Save UI
- 기술 구성요소 은닉
- 오류/충돌 안내
- 사용자별 업무 흐름 검증

## Phase 6 — Migration and Operational Validation

Status: Not started

- 기존 실제 관리대장 데이터 migration
- 다중 사용자 테스트
- 성능 비교
- 장애/복구 테스트
- 운영 절차 확정

## Phase 7 — Completion

Status: Not started

- 검증된 최종 구조 기록
- 운영 문서 확정
- 기존 prototype/test 자산 정리
- 공개 가치가 있는 내용에 한해 BLOG publication 검토
