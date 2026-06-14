# My Driving Skills 🚗

웹캠 앞에서 **양손을 허공 핸들처럼** 움직여 조작하는 운전 연습 시뮬레이터입니다.
MediaPipe Hand Landmarker로 손을 추적하고 Three.js로 3D 도로를 렌더링하는 정적 웹앱이며,
카메라 영상은 서버로 전송되지 않고 **브라우저 안에서만** 처리됩니다.

작성: **성준희 (JoonHee)** · GitHub [@devCharlotte](https://github.com/devCharlotte)
저장소: [devCharlotte/my-driving-skills](https://github.com/devCharlotte/my-driving-skills)

## 조작 방법

| 동작 | 제스처 |
| --- | --- |
| 조향 | 양손을 핸들처럼 들고 좌우로 기울이기 |
| 가속 | 두 손을 주먹 쥐기 (꽉 쥘수록 가속↑) |
| 브레이크 | 두 손을 화면 위쪽으로 높이 들기 |

키보드 대체: `←` `→` 조향 / `↑` 가속 / `↓` 또는 `Space` 브레이크

## 연습 요소

신호등·정지선·횡단보도, 제한속도 표지, 커브 감속 구간을 지키며 주행합니다.
차선 이탈, 과속, 신호 위반, 충돌은 감점되고 안정적인 통과는 가점됩니다.

## 실행

```bash
npm start          # python3 -m http.server 8080
# 또는
python3 -m http.server 8080
```

브라우저에서 `http://localhost:8080` 접속 후 **웹캠 켜고 연습 시작**을 누릅니다.
(카메라 권한이 필요하며, HTTPS 또는 `localhost`에서만 동작합니다.)

### 두 창 모드

`🪟 두 창으로 플레이` 버튼을 누르면 핸들/웹캠 컨트롤러 창과 게임 화면 창이 분리됩니다.
한 창에서 손으로 조작하고 다른 창(예: 큰 모니터)에서 주행 화면을 띄울 수 있습니다.

## 기술 스택

- [Three.js](https://threejs.org/) 0.160 — 3D 렌더링
- [MediaPipe Tasks Vision](https://ai.google.dev/edge/mediapipe) 0.10.14 — 손 추적
- 빌드 도구 없는 순수 ES Module (import map)

## 배포

GitHub Pages / Vercel 등 정적 호스팅에 그대로 올릴 수 있습니다.
카메라 사용을 위해 `vercel.json`에 `Permissions-Policy: camera=(self)` 헤더가 설정되어 있습니다.

## 라이선스

MIT © 성준희 (devCharlotte)
