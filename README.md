# my-driving-skills

성준희의 운전 연습용 정적 웹앱입니다.

## 핵심 특징

- 게임 포탈/워크 포탈 계열의 네온 글래스 스타일
- Tesla 스타일 핸들 이미지를 포함한 조향 UI
- 웹캠 기반 허공 핸들 조작 지원
- 키보드 조작 지원
- 신호등, 정지선, 제한속도, 커브, 장애물, 차선 유지 연습
- GitHub Pages에 바로 배포 가능한 정적 파일 구조

## 실행 방법

```bash
python3 -m http.server 8080
```

브라우저에서 아래 주소로 접속합니다.

```text
http://localhost:8080
```

## GitHub Pages 배포

1. 이 폴더 안의 파일을 GitHub 저장소 루트에 업로드합니다.
2. `index.html`이 저장소 루트에 있어야 합니다.
3. Repository Settings → Pages로 이동합니다.
4. Source를 `Deploy from a branch`로 설정합니다.
5. Branch는 `main`, folder는 `/root`로 설정합니다.

## 버튼 오류 방지 구조

이번 최종본에서는 버튼 이벤트를 가장 먼저 등록하고, Three.js 시뮬레이터와 MediaPipe 웹캠 모듈은 버튼을 누른 뒤에만 동적으로 불러오도록 수정했습니다. 따라서 웹캠 모듈 또는 WebGL 로딩이 실패해도 버튼 자체가 먹통이 되는 문제가 발생하지 않도록 구성했습니다.

## 파일 구조

```text
index.html
styles.css
js/app.js
js/drive-scene.js
js/gesture-wheel.js
assets/tesla-wheel.png
```

## 주의

- 웹캠 모드는 `https` 또는 `localhost` 환경에서 사용하는 것이 가장 안정적입니다.
- GitHub Pages에서는 `https`로 배포되므로 웹캠 권한 요청이 가능합니다.
- 이 웹앱은 운전 감각 연습용 시뮬레이션이며 실제 운전 교육을 대체하지 않습니다.
