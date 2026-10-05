# 레코드룸 — 에이전트 진입점

한 페이지 음악 플레이어. **`index.html` 한 파일**이 전부다 (HTML·CSS·JS, 빌드 없음). `main`에 푸시하면 GitHub Pages(`/`)로 바로 공개된다.

## 규칙

- 외부 라이브러리·CDN·글꼴·이미지 파일을 쓰지 않는다. 예외는 유튜브 재생 도구 `https://www.youtube.com/iframe_api` 하나
- 화면(캔버스)과 저장(움직이는 카드)은 **같은 그리기 함수**(`drawCover`·`drawLP`·`drawTape`)를 쓴다 — 하나를 고치면 둘 다 바뀐다
- 색 뽑기(`extractPalette`)는 trackpic과 같은 절차를 지킨다: 가운데 70% · MMCQ 25색 · 주색 색상 ±0.15 또는 채도 < 0.2 · 밝기순 5색(최소 밝기 차 25→15→8→5→3), 배경 = 가장 어두운 색
- 디자인: 평평한 면 + 층마다 아주 부드러운 그림자. 장식용 그라데이션을 늘리지 않는다

## 확인

- 화면: `chrome --headless=new --window-size=500,980 --screenshot=out.png "file:///…/index.html#v=<영상ID>&mode=lp"` (mode = cover · lp · tape)
- 저장 결과: 주소 끝에 `&selftest=gif` 또는 `webp` → `--dump-dom`의 `<pre id="selftest">`에 base64 결과 (Pillow로 열어 장 수 확인)
- 유튜브 재생은 `file://`에서 막힌다 — 공개 주소에서 확인한다
