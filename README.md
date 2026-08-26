# CRM Screen Specs

CRM 기능별 화면정의서와 공유 이력을 관리하는 GitHub Pages 저장소입니다.

## 운영 원칙

- `main`은 현재 기준이 되는 공통 지침과 모든 확정 산출물을 보관합니다.
- 개발팀에 공유한 버전 경로(`features/{feature}/vN/`)는 수정·삭제하지 않습니다.
- 변경이 필요하면 기존 버전을 덮어쓰지 않고 `vN+1`을 추가합니다.
- `features/{feature}/`는 최신 버전으로 이동하는 가변 링크입니다.
- Jira·이슈·개발 요청에는 변경되지 않는 버전 링크를 기록합니다.
- 각 버전의 `index.html`은 ScreenSpec을 포함한 자체 완결 파일로 보관합니다.
- 강제 푸시와 이미 공유한 커밋 이력 재작성을 금지합니다.

## 폴더 규칙

```text
features/
└─ {기능 영문 슬러그}/
   ├─ index.html       최신 버전 이동용
   ├─ history.json     버전·상태·화면 ID 기록
   ├─ v1/index.html    변경하지 않는 1차 공유본
   └─ v2/index.html    변경하지 않는 2차 공유본
```

## 새 버전 추가 절차

1. ScreenSpec 적용 원본에서 자체 완결 HTML을 생성합니다.
2. `features/{기능}/vN/index.html`에 저장합니다.
3. `history.json`에 버전, 날짜, 변경 요약, 화면 ID를 추가합니다.
4. 기능 폴더의 `index.html`이 새 버전을 가리키도록 변경합니다.
5. 루트 `index.html`의 최신 버전과 변경일을 갱신합니다.
6. Pull Request 검토 후 `main`에 병합합니다.

커밋 예시:

```text
feat(inquiry): 문의관리 화면정의 v1 추가
feat(inquiry): 첨부파일 정책을 반영한 v2 추가
fix(catalog): 문의관리 최신 버전 링크 수정
```

## GitHub Pages 설정

이 폴더를 별도 `crm-screen-specs` 저장소의 루트로 올린 뒤 다음과 같이 설정합니다.

1. `Settings → Pages`
2. `Source → Deploy from a branch`
3. `Branch → main`, 폴더 `/(root)`

예상 주소:

```text
전체 목록: https://gani091.github.io/crm-screen-specs/
최신본  : https://gani091.github.io/crm-screen-specs/features/inquiry/
고정 v1 : https://gani091.github.io/crm-screen-specs/features/inquiry/v1/
```

