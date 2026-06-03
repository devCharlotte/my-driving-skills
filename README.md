# my-driving-skills

성준희의 운전 연습용 GitHub Pages 정적 웹앱입니다.

## 포함 기능

- Tesla 스타일 핸들 이미지 적용
- 웹캠 권한 요청을 버튼 클릭 직후 바로 실행
- 웹캠 손 인식 기반 허공 핸들 조향
- 키보드 모드 지원
- 신호등, 정지선, 제한속도, 커브, 장애물, 차선 유지 연습
- 점수, 실수 횟수, 주행 거리, 최고 점수 표시

## 중요한 실행 조건

웹캠 권한 팝업은 브라우저 보안 정책상 아래 환경에서만 정상적으로 뜹니다.

```text
https:// 로 시작하는 GitHub Pages 배포 주소
http://localhost:8080
http://127.0.0.1:8080
```

아래 방식은 카메라 권한 팝업이 뜨지 않을 수 있습니다.

```text
file:// 로 index.html 직접 열기
일반 http:// 원격 주소
브라우저에서 이미 카메라 차단을 선택한 사이트
```

## 로컬 실행

```bash
python3 -m http.server 8080
```

접속 주소는 다음과 같습니다.

```text
http://localhost:8080
```

## GitHub Pages 배포

압축을 푼 뒤 `my-driving-skills` 폴더 안의 파일들을 저장소 루트에 올리면 됩니다.

```text
index.html
styles.css
js/app.js
js/drive-scene.js
js/gesture-wheel.js
assets/tesla-wheel.png
README.md
```

GitHub 저장소 이름이 `my-driving-skills` 또는 `my driving skills`여도 내부 경로는 상대 경로로 작성되어 배포가 가능합니다.

## 이번 최종 수정

- 웹캠 시작 버튼 클릭 직후 `navigator.mediaDevices.getUserMedia()`를 먼저 호출하도록 수정했습니다.
- 따라서 Three.js나 MediaPipe가 로딩되기 전에 카메라 권한 팝업이 먼저 뜹니다.
- MediaPipe 손 인식 모듈은 카메라 허용 이후 로딩합니다.
- Tesla 스타일 핸들 이미지를 `assets/tesla-wheel.png`, `tesla-wheel.png`, `wheel.png`에 중복 포함했습니다.
- 이미지 경로 실패 시 루트의 `tesla-wheel.png`로 자동 fallback되도록 설정했습니다.
