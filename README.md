# SKCT 수열 연구소

SKCT 수열추리 연습을 위한 비공식 창작 문제 서비스입니다. [문제 풀기](https://seokminlee-chris.github.io/skct-sequences/)

## 문제 은행

- 7,123개의 생성·검증된 창작 문제
- 12개 큰 유형, 24개 세부 규칙: 계차, 피보나치, 홀짝 분리, 연산 교대, 통분, 분자·분모, 소수점, 군수열, 제곱수, 소수(素數), 곱셈 성장, 부호 교대
- 문제마다 6~10개의 수가 보이며, 보기 5개와 해설을 포함합니다.
- 10문항마다 큰 유형이 겹치지 않도록 출제합니다. 20문항에서는 각 10문항 묶음마다 이 규칙을 적용하고, 두 묶음의 세부 규칙도 중복되지 않습니다.

공개된 [2026년 응시 후기](https://community.linkareer.com/employment_data/6396376)와 [분수·소수 유형 후기](https://community.linkareer.com/community/3541839)에서 언급된 유형을 참고했습니다. 실제 시험 문제나 상용 교재의 문항을 옮기지 않고 새 규칙과 숫자로 만들었습니다. SK그룹과 관련 없는 비공식 서비스입니다.

## 사용 방식

- 10문항 또는 20문항: 선택한 번호를 마우스로 누르고 다음 문제로 이동합니다. 마지막에 전체 해설을 확인합니다.
- 한 문제씩: 번호를 마우스로 누르고 정답 확인을 누르면 즉시 해설을 봅니다.
- 문제마다 그림판과 메모장을 사용할 수 있고, 다음 문제로 이동하면 내용이 초기화됩니다.
- 풀이 시간은 분·초로 표시됩니다. 10문항과 20문항 리더보드는 별도로 집계합니다.

## 개발

Node.js 22.13 이상이 필요합니다.

```sh
npm ci
node scripts/generate-bank.mjs
node scripts/validate-bank.mjs
npm run dev
```

`npm run build:pages`는 GitHub Pages용 단일 `gh-pages-dist/index.html`을 만들고, `npm run build`는 점수 API와 D1 리더보드용 Sites 빌드를 만듭니다. 정적 페이지는 GitHub Pages에, 공용 점수 API는 Sites에 배포되어 있습니다. API 주소는 `gh-src/index.html`에 설정되어 있습니다.

문제 생성은 고정 시드로 재현 가능합니다. `lib/bank.json`은 생성된 문제, `lib/bank-meta.json`은 유형별 통계입니다. `scripts/validate-bank.mjs`는 모든 문항의 수학 규칙, 정답, 보기, 중복을 검사합니다.
