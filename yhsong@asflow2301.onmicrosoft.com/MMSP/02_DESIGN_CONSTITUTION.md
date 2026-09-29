# 02 DESIGN CONSTITUTION — MMSP

## 1. Responsibility Separation

- SharePoint는 중앙 Office 파일과 배포/저장 위치를 책임집니다.
- Excel은 사용자 인터페이스와 업무 입력을 책임집니다.
- Access는 영속 데이터와 계산 계층을 책임집니다.
- GitHub OfficeWorkspace는 프로젝트 관리 기록을 책임집니다.

## 2. SharePoint Is Not an SMB Access Backend

SharePoint의 `.accdb` 파일을 네트워크 공유 Access DB처럼 직접 동시 편집하는 구조를 사용하지 않습니다.

Access 파일은 버전이 있는 중앙 데이터 스냅샷/엔진으로 다루며, 동기화와 충돌 통제가 별도로 필요합니다.

## 3. Identity and Data Keys

업무상의 `NO` 값은 중복 가능성이 확인되었으므로 데이터베이스 Primary Key로 사용하지 않습니다.

내부 고유키 `PO_ID`를 사용하고 `NO`는 업무 식별/reference 값으로 유지합니다.

## 4. Delta-Oriented Synchronization

저장 작업은 전체 행이나 전체 워크시트를 무조건 덮어쓰지 않고 변경된 레코드와 변경된 필드를 중심으로 처리하는 것을 기본 원칙으로 합니다.

## 5. Conflict Awareness

Client가 읽은 원본 값과 저장 시점의 서버 값을 비교할 수 있어야 하며, 서버에서 이미 변경된 동일 필드가 발견되면 충돌로 처리할 수 있어야 합니다.

동일 PO라도 서로 다른 필드에 대한 독립 변경은 가능한 한 공존할 수 있어야 합니다.

## 6. User Experience

최종 사용자는 최소한 다음 수준의 인터페이스로 업무를 수행하는 것을 목표로 합니다.

- 최신 데이터 불러오기
- 변경사항 저장

초기화 스크립트, Access 구조 변경, VBA 모듈 수동 import 등은 개발/검증 단계의 작업이며 일반 사용자 운영 절차가 아닙니다.

## 7. Mutation Boundary

SharePoint 수정 허용 범위는 `Documents/MMSP/**`입니다.

이 범위 밖의 SharePoint 항목은 프로젝트 작업 중 변경하지 않습니다.

## 8. Verification

문서상의 의도와 실제 Windows Office Runtime을 구분합니다.

Excel/Access/VBA 동작은 실제 Microsoft Office 환경에서 검증되기 전까지 완료된 결과로 기록하지 않습니다.
