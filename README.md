# my-driving-skills

성준희의 운전 연습용 정적 웹앱입니다.

문구
- 20세에 면허를 취득한 나 성준희. 베스트 드라이버가 되어보겠다아 !!

핵심 특징
- 게임 포탈/워크 포탈 계열의 네온 글래스 스타일
- Tesla 느낌의 핸들 이미지를 사용한 조향 UI
- 웹캠 기반 허공 핸들 조작 또는 키보드 조작 지원
- 신호등, 정지선, 제한속도, 커브, 장애물, 차선 유지 연습
- GitHub Pages에 바로 배포 가능한 정적 구조

이번 안정화 수정
- 시작 버튼을 일반 스크립트에서 먼저 등록하도록 변경했습니다.
- 웹캠 시작 버튼 클릭 직후 `navigator.mediaDevices.getUserMedia()`가 바로 실행됩니다.
- Three.js 시뮬레이터와 MediaPipe 손 인식 모듈은 카메라 권한 요청 이후에 동적 로딩됩니다.
- 카메라 권한 요청 실패 시 자동으로 멈추지 않고 상태 메시지를 표시합니다.
- Tesla 스타일 휠 이미지를 `assets/tesla-wheel.png`, `tesla-wheel.png`, `wheel.png`에 포함했습니다.

파일 구조
- `index.html` : 메인 화면
- `styles.css` : 전체 레이아웃과 스타일
- `js/app.js` : 버튼, 권한 요청, UI 연결, 게임 루프
- `js/drive-scene.js` : Three.js 주행 시뮬레이션
- `js/gesture-wheel.js` : MediaPipe 손 인식 제어
- `assets/tesla-wheel.png` : Tesla 스타일 핸들 이미지

실행 방법
```bash
python3 -m http.server 8080
```

브라우저에서 아래 주소로 접속합니다.

```text
http://localhost:8080
```

GitHub Pages 배포
1. 이 저장소 내용을 그대로 업로드합니다.
2. Repository Settings → Pages에서 배포 브랜치를 `main` / root 로 선택합니다.
3. 배포가 완료되면 `https://...` 주소에서 접속합니다.

주의
- `file://`로 직접 열면 카메라 권한 팝업이 정상적으로 뜨지 않을 수 있습니다.
- GitHub Pages 또는 localhost에서는 정상적으로 카메라 권한 요청이 실행됩니다.


최종 안정화 수정
- 버튼 클릭 시 inline bootstrap이 가장 먼저 getUserMedia({ video: true, audio: false })를 호출합니다.
- Three.js와 MediaPipe가 실패해도 카메라 권한 요청 자체는 먼저 실행됩니다.
- 카메라 실패 시 화면에 NotAllowedError, NotFoundError, NotReadableError 등 실제 오류명이 표시됩니다.
- Tesla 스타일 휠은 root와 assets 경로에 모두 포함되어 경로 문제를 줄였습니다.
