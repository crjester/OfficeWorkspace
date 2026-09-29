# 05 RESULT — MMSP

이 문서는 실제 검증이 끝난 결과만 기록합니다.

## Verified Results

### Existing Workbook Analysis

- `PQ-영업`이 통합 PO Source 역할을 합니다.
- `PO`가 운영 관리 sheet 역할을 합니다.
- 기존 workbook은 대량의 lookup/calculation formula에 의존합니다.
- `PO.NO`에는 중복값이 존재하므로 database Primary Key로 직접 사용할 수 없습니다.
- 내부 고유키 `PO_ID`가 필요합니다.

### Project Management

- GitHub `crjester/OfficeWorkspace`를 Office 프로젝트 관리 Registry로 사용합니다.
- Microsoft 계정 풀네임을 account boundary directory로 사용합니다.
- MMSP 관리 SoT 경로는 `yhsong@asflow2301.onmicrosoft.com/MMSP/`입니다.
- 실제 Office Runtime과 데이터는 SharePoint `Documents/MMSP/`에 유지합니다.

## Not Yet Verified

다음 항목은 아직 완료 결과가 아닙니다.

- Windows에서 Access prototype schema initialization 성공
- Excel VBA → Access 연결 성공
- Access 데이터 persistence 성공
- SharePoint 기반 동시 저장/lock/conflict 처리
- 실제 업무 workbook migration
- 다중 사용자 운영 검증
