# MMSP

Excel 중심 생산관리 업무를 SharePoint + Excel + Microsoft Access 구조로 재설계하는 프로젝트입니다.

## Source of Truth

이 GitHub 디렉터리는 MMSP의 프로젝트 관리 SoT입니다.

실제 Office Runtime과 업무 데이터의 책임 위치는 Microsoft 계정 `yhsong@asflow2301.onmicrosoft.com`의 SharePoint:

`Documents/MMSP/`

입니다.

## SharePoint Mutation Boundary

SharePoint 작업 시 수정 범위는 반드시 다음으로 제한합니다.

`Documents/MMSP/**`

상위 폴더, 형제 폴더 및 그 밖의 SharePoint 파일은 수정, 이동, 삭제, 이름 변경, 덮어쓰기 또는 생성하지 않습니다.

## Project Documents

1. [01_CONCEPT.md](./01_CONCEPT.md) — 목적과 문제 정의
2. [02_DESIGN_CONSTITUTION.md](./02_DESIGN_CONSTITUTION.md) — 설계 원칙과 제약
3. [03_ROADMAP.md](./03_ROADMAP.md) — 단계와 현재 진행 위치
4. [04_DEVELOPMENT_NOTES.md](./04_DEVELOPMENT_NOTES.md) — 결정, 실험, 실패, 테스트 기록
5. [05_RESULT.md](./05_RESULT.md) — 검증 완료된 결과

## Current Runtime Artifacts

SharePoint `Documents/MMSP/`에서 현재 관리 중인 주요 파일:

- `PO_Client.xlsm`
- `PO_Client.xlsx`
- `PO_Master.accdb`
- `test/`

실제 존재 여부와 최신 상태는 작업 시작 시 SharePoint에서 다시 확인합니다.
