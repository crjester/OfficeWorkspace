# 04 DEVELOPMENT NOTES — MMSP

## 2026-09-29 — Project Management SoT Established

MMSP 프로젝트 관리 기록을 GitHub `OfficeWorkspace` 저장소로 분리했습니다.

관리 계층:

```text
OfficeWorkspace
└─ yhsong@asflow2301.onmicrosoft.com
   └─ MMSP
```

실제 Office Runtime과 데이터는 SharePoint `Documents/MMSP/`가 계속 책임집니다.

### Workbook Analysis

확인된 주요 사항:

- 원본 핵심 Source sheet: `PQ-영업`
- 운영/관리 sheet: `PO`
- `PQ-영업`: 약 18.8K rows
- `PO`: 약 18.6K rows
- `PO`에는 대량의 lookup/calculation formulas가 존재
- `PO.NO`에는 중복 업무키가 존재
- 따라서 Access 내부 PK로 `PO_ID` 사용 결정

### Prototype

SharePoint `Documents/MMSP/`에 다음 prototype 자산이 존재하는 것으로 이전 작업에서 확인되었습니다.

- `PO_Master.accdb`
- `PO_Client.xlsx`
- `PO_Client.xlsm`
- `test/01_InitDatabase.vbs`
- `test/02_MMSP_Prototype.bas`
- `test/TEST_GUIDE.md`

실제 최신 존재 여부는 다음 작업 시작 시 SharePoint에서 다시 검증해야 합니다.

### Prototype Schema

초기 prototype table:

- `T_PO_SOURCE`
- `T_PO_PROGRESS`
- `T_CHANGE_LOG`
- `T_SYSTEM`

prototype SchemaVersion: `0.1`

### Current Validation Point

현재 다음 Windows-side 검증이 남아 있습니다.

1. DB initializer 실행
2. Excel → Access 연결 확인
3. TEST record 저장
4. Excel 재실행
5. 이전 TEST record 지속성 확인

### Open Architecture Issue

SharePoint는 SMB 파일 공유가 아니므로 중앙 `.accdb`를 직접 동시 Access backend로 사용할 수 없습니다.

단순한 텍스트 lock만으로는 원자성이 보장되지 않으므로 SharePoint의 version/ETag/checkout 등 허용된 수단을 이용한 동시성 제어 방식을 향후 실제 검증해야 합니다.
