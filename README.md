# My Driving Skills — 성준희 운전 연습 시뮬레이터

웹캠으로 양손을 인식해 허공 핸들처럼 조향하는 Three.js 기반 3D 운전 연습 웹앱입니다. GitHub Pages에 그대로 배포할 수 있도록 정적 파일만 사용합니다.

시작 문구:

> 20세에 면허를 취득한 나 성준희. 베스트 드라이버가 되어보겠다아 !!

## 주요 기능

- 양손 웹캠 인식 기반 허공 핸들 조향
- 키보드 폴백: `←` `→` 조향, `↑` 가속, `↓` 또는 `Space` 브레이크
- 신호등, 정지선, 횡단보도, 제한속도, 커브 경고, 차선 유지 연습
- 과속, 신호 위반, 차선 이탈, 충돌 감점
- 점수, 실수 횟수, 최고 점수 저장
- 두 창 모드: 한 창은 조향 컨트롤러, 한 창은 시뮬레이션 화면

## 실행

웹캠 접근은 `https` 또는 `localhost`에서만 허용됩니다.

```bash
# Node를 사용할 때
npm start

# Python만 사용할 때
python3 -m http.server 8080
```

브라우저에서 아래 주소로 접속합니다.

```text
http://localhost:8080
```

## GitHub Pages 배포

별도 빌드 과정 없이 저장소 루트에 있는 파일을 그대로 배포하면 됩니다.

1. GitHub 저장소에 `index.html`, `styles.css`, `main.js`, `game.js`, `hands.js`, `wheel.png` 등을 업로드합니다.
2. Repository Settings → Pages로 이동합니다.
3. Source를 `Deploy from a branch`로 설정합니다.
4. Branch는 `main`, folder는 `/root`로 설정합니다.
5. 배포 주소가 생성되면 접속합니다.

## 파일 구조

```text
index.html   화면 구조, HUD, 시작/결과 오버레이
styles.css   네온 UI, 게임 포탈/워크 포탈 느낌의 패널 스타일
hands.js     MediaPipe HandLandmarker 기반 손 추적 입력
game.js      Three.js 운전 시뮬레이션, 신호/정지선/커브/제한속도/점수 로직
main.js      게임 루프, HUD 업데이트, 웹캠/키보드/두 창 모드 연결
wheel.png    핸들 이미지
```

## 참고

이 웹앱은 브라우저 기반 운전 감각 연습용 콘텐츠입니다. 실제 도로 주행 판단이나 실제 운전 교육을 대체하지 않습니다.


## 이번 최종본 메모

- 업로드된 정상 동작 기반 파일 구조를 그대로 유지했습니다.
- 포털 스타일 CSS와 게임/웹캠/키보드 로직을 갈아엎지 않았습니다.
- 휠 이미지만 Tesla-style 이미지로 교체했습니다.
- GitHub Pages용 루트 폴더명은 `my-driving-skills`입니다.
