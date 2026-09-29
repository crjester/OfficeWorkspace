# OfficeWorkspace

Microsoft 365 / SharePoint / OneDrive 기반 Office 프로젝트를 계정 단위로 관리하는 프로젝트 레지스트리입니다.

## 관리 원칙

- 최상위 경계는 Microsoft 계정 Identity입니다.
- 계정 폴더명은 가능한 한 실제 Microsoft 계정 풀네임을 사용합니다.
- 각 계정 폴더 아래에 프로젝트별 관리 SoT를 둡니다.
- 실제 Excel, Access, Word, PowerPoint 및 운영 데이터는 해당 SharePoint/OneDrive에 둡니다.
- 이 저장소에는 프로젝트의 목적, 설계 원칙, 로드맵, 개발 기록, 검증 결과와 외부 Office Workspace 연결 정보만 기록합니다.
- 비밀번호, 토큰, 쿠키, 인증서, 개인 키 등 credential은 기록하지 않습니다.
- 프로젝트별 실제 Office 파일의 상태는 연결된 SharePoint/OneDrive Runtime에서 확인합니다.

## 구조

```text
OfficeWorkspace/
├─ README.md
└─ <Microsoft Account>/
   ├─ README.md
   └─ <Project>/
      ├─ README.md
      ├─ 01_CONCEPT.md
      ├─ 02_DESIGN_CONSTITUTION.md
      ├─ 03_ROADMAP.md
      ├─ 04_DEVELOPMENT_NOTES.md
      └─ 05_RESULT.md
```

## Accounts

### yhsong@asflow2301.onmicrosoft.com

- Workspace: `./yhsong@asflow2301.onmicrosoft.com/`
- Current projects:
  - [MMSP](./yhsong@asflow2301.onmicrosoft.com/MMSP/)
