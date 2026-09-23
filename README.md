# 수열연구소

고난도 수열추리 연습 웹앱입니다. 6가지 복합 규칙으로 생성한 창작 문제 2,249개에서 10문항씩 풀고, 정답과 풀이 시간에 따른 점수를 리더보드에 등록할 수 있습니다. 풀이 화면 아래에는 그림판과 메모장이 있습니다.

SK 공식 서비스나 기출문제 모음이 아닙니다. 공개된 시험 유형 정보만 참고했고, 모든 수열과 해설은 규칙 생성기로 새로 만들었습니다.

## 구성

- `index.html`: GitHub Pages에 게시되는 단일 파일 웹앱
- `source.zip`: 프런트엔드, 문제 생성기, API, 데이터베이스 스키마의 소스
- 공용 기록 API: `https://sequence-lab-skct.lsm9434.chatgpt.site`

## 개발

`source.zip`을 풀고 Node.js 22 이상에서 `npm ci`를 실행합니다. `npm run build:pages`는 GitHub Pages용 단일 HTML을 `gh-pages-dist/index.html`에 만듭니다. `node scripts/generate-bank.mjs`는 문제 은행을 다시 생성합니다.

리더보드와 채점 API는 별도 서버와 D1 데이터베이스를 사용합니다. GitHub Pages는 정적 화면을 호스팅합니다.
