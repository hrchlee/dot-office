# 도트 사무실

프로젝트마다 담당 직원이 책상에 앉아 있고, 비서가 전체 현황을 종합해 보고하는 픽셀 사무실입니다.
비서에게 지시하거나, 책상을 눌러 담당자에게 직접 지시할 수 있습니다.

## 파일
- `index.html` — 화면 전체
- `firebase-config.js` — Firebase 연결 값 (비워 두면 데모 모드)
- `firestore.rules` — Firestore 보안 규칙 (콘솔 > Firestore > 규칙에 붙여 넣기)

## 데이터 구조 (Firestore)
- `users/{uid}/projects/{id}` — `name, staff, status(idle|working|blocked|done), task, progress, createdAt`
- `users/{uid}/orders/{id}` — `target("secretary" 또는 프로젝트 id), text, status(new|doing|done), reply, createdAt`

다른 프로그램(예: 집 PC의 에이전트)이 같은 경로를 읽고 쓰면 사무실 화면에 실시간으로 반영됩니다.
