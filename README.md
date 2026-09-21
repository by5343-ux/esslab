# Earth Science School Lab

배지구(bae_earth) 선생님의 지구과학 탐구 실험실.
2022 개정 교육과정 성취기준에 맞춘 지구과학 시뮬레이션을 과목별로 모아, 선생님이 수업에 골라 쓰는 사이트입니다.

## 폴더 구성

```
index.html          포털(첫 화면). 목록, 과목 분류, 학생용 링크·QR 만들기
sims/               시뮬레이션 파일
  enso.html                 ENSO 탐구 (워크북)          [12지구01-05]
  enso-sim.html             ENSO 시뮬레이션만
  geodex.html               GEODEX 게임                 [12지구02-05]
  geodex-workbook-1.html    GEODEX 인쇄용 워크북 1부
  geodex-workbook-2.html    GEODEX 인쇄용 워크북 2부
  plate-tectonics.html      판구조론 탐구 (워크북)      [12지시01-03]
  plate-tectonics-sim.html  판구조론 시뮬레이션만
  exoplanet.html            외계행성 탐사 연구소        [12행우01-05]
  exoplanet-sim.html        외계행성 시뮬레이션만
  cheongu-game.html         천구 레이저 관측대 게임     [12지실03-01]
  cheongu-sim.html          천구 관측실 (시뮬레이션만)
  cheongu-workbook.html     천구 레이저 관측대 인쇄용 워크북
  pressure-wind.html        기압과 바람 5E (워크북)     [9과13-07]
  pressure-wind-sim.html    기압과 바람 시뮬레이션만
  sundial.html              해시계 만들기 5E (워크북)   성취기준 외
  sundial-sim.html          해시계 시뮬레이션만
teacher/
  ENSO_수행평가_Code.gs     ENSO 수행평가 응답을 구글 시트로 받는 앱스 스크립트 (교사용, 사이트에는 안 쓰임)
.nojekyll           깃허브 페이지가 파일을 그대로 보여 주게 하는 빈 파일
```

## 새 시뮬레이션 추가하기

1. HTML 파일을 `sims/` 폴더에 올립니다. 파일 이름은 영어 소문자와 `-`만 쓰는 것이 안전합니다.
2. `index.html`을 열어 `const SIMS=[` 목록에 한 항목을 추가합니다.

```js
{id:'새아이디', title:'제목',
 codes:['12지구01-01'],            // 첫 번째가 주 성취기준, 나머지는 연계. 없으면 []
 desc:'한두 문장 설명',
 tags:['태그1','태그2'], time:'2차시',
 teacher:['교사용 안내 1','교사용 안내 2'],
 url:'', file:'sims/새파일.html',
 sim:{url:'', file:'sims/새파일-sim.html'}},   // 시뮬레이션만 버전이 있을 때만
```

과목은 성취기준 코드 앞부분(9과, 10통과, 12지구, 12지시, 12행우, 12지실)으로 자동 분류됩니다.
`url`은 claude.ai 미리보기용 주소라서 깃허브에서는 쓰이지 않고, `file` 경로가 쓰입니다.

## 알아 둘 점

- 깃허브 페이지에서 열면 '학생용 링크'와 QR 코드가 실제 사이트 주소로 만들어집니다.
- ENSO, 판구조론의 수행평가 제출은 이 사이트에서는 '연습 모드'로 동작합니다. 구글 시트로 받으려면 `teacher/` 폴더의 스크립트를 이용하거나, 각 파일 맨 위의 제출 주소 설정에 앱스 스크립트 웹 앱 주소를 넣으세요.
- 기압과 바람의 응답 공유 기능은 파일 안의 `SUBMIT_URL`, `READ_URL`을 채워야 작동합니다.
- GEODEX는 휴대폰 홈 화면 추가용 아이콘 파일(manifest.json, 아이콘)이 없어서 그 기능만 빠져 있습니다. 게임은 정상 작동합니다.
- 모형의 수치는 특별한 표시가 없는 한 상대값입니다. 실제 관측 자료의 출처는 각 시뮬레이션 안에 적혀 있습니다.
