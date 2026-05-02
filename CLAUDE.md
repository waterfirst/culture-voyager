# Culture Voyager — 주말의 문화예술 매거진

<context>
주말마다 발행하는 문화예술 힐링 매거진.
시대를 관통하는 영화, 인생을 바꾸는 책, OTT 추천, 역사 다큐, 여행지, 아티스트 스토리를 다룬다.
GitHub Pages로 배포: https://waterfirst.github.io/culture-voyager/
저자: Nakcho Choi
</context>

<instructions>

## 콘텐츠 범위

6개 축으로 구성된 문화예술 매거진:
- A축: 시대를 관통하는 영화 (Timeless Cinema)
- B축: 인생을 바꾸는 책 (Books That Matter)
- C축: OTT 필수 시청 (Streaming Gems)
- D축: 역사 다큐멘터리 (History Unwrapped)
- E축: 언젠가 가볼 곳 (Future Travels)
- F축: 아티스트 스토리 (Artist Stories)

운영 원칙:
- 토요일: A/B/D축 (영화, 책, 역사 다큐) — 깊이 있는 리뷰
- 일요일: C/E/F축 (OTT, 여행, 아티스트) — 가볍고 힐링
- 축을 순환하며 편향 없이 배분

## 콘텐츠 수준 — 박구용 교수 기준

참고 인물: 박구용 철학 교수의 영화 비평 스타일. 핵심 원칙:

1. **형식을 먼저 읽어라**: 줄거리 요약이 아니라, "이 작품이 어떻게 설계되었는가"를 해부한다. 감독의 편집 설계, 카메라 거리 선택, 반복 구조, 음악의 서사적 기능을 분석한다.
2. **예술의 법정에 봉인하라**: 단순 리뷰가 아니라, 왜 이 작품이 시간을 이기는지(또는 이기지 못하는지) 판결을 내린다.
3. **여러 번 봐야 보이는 것을 보여줘라**: 표면 독해 → 설계 독해 → 철학적 독해. 층위를 드러낸다.
4. **진솔한 고백을 섞어라**: "나이 들어서야 깨달은 것", "귀중한 걸 잃었다는 자각" — 개인적 깊이가 있어야 한다.
5. **교양이 아니라 충격을 줘라**: 읽은 후 "아, 그런 거였어?" 하는 인식 전환이 반드시 하나 이상 있어야 한다.

표면적 정보(촬영 비화, 박스오피스, 트리비아)는 배경으로만 쓰고, 본문의 핵심은 반드시 "해석의 깊이"에 있어야 한다.

## 콘텐츠 톤

- 박구용 스타일: 지적이면서도 열정적, 건조하지 않고 뜨거운
- 주말에 편하게 읽되, 읽고 나면 생각이 바뀌는 글
- "형식을 읽을 줄 알면, 이 사람은 천재구나" — 이 깨달음을 독자에게 전달
- 시각 자료(영화 스틸, 표지, 풍경)와 청각 자료(OST, 플레이리스트, 팟캐스트) 적극 활용

</instructions>

<technical_stack>

## 기술 스택

R + ggplot2로 차트(별점, 흥행 추이, 여행 비용 비교 등)를 생성한다. Plotly는 파일 용량이 비대해지므로 사용하지 않는다.
Quarto (.qmd)로 보고서를 렌더링하며, 아래 설정을 따른다:

- `lightbox: true` — 이미지 클릭 시 줌인 가능
- `self-contained: true` — 단일 HTML 배포
- `dev: ragg_png` — CJK 폰트 렌더링에 필요
- 폰트: `"Noto Sans CJK KR"` 시스템 폰트를 직접 사용한다. showtext는 Quarto knitr 환경에서 충돌하므로 사용하지 않는다.
- 색상: 6자리 hex만 사용한다 (`"#aaaaaa"`). 3자리 hex(`"#aaa"`)는 Quarto+ragg 조합에서 에러를 발생시킨다.
- 테마: flatly (밝은 따뜻한 톤) — darkly는 사용하지 않음

## 멀티미디어 요소

### 이미지 (GPT Image API)
- 매주 커버 이미지를 GPT Image API(gpt-image-1)로 생성하여 assets/splash_cover.webp 교체
- 프롬프트 패턴: "Warm cinematic magazine cover, [주제], editorial style, soft lighting, film grain"
- 콘텐츠별 삽화도 GPT Image로 생성 가능 (output/assets/ 하위)

### 오디오 (Gemini TTS)
- 에세이 내레이션을 Gemini Text-to-Speech로 생성하여 각 콘텐츠에 오디오 플레이어 삽입
- 배경 앰비언트: assets/ambient.mp3 (저작권 프리 소스 사용)
- 추천 소스: Pixabay Music, Mixkit, Freesound.org

### 임베드
- YouTube: 트레일러, 인터뷰, 다큐멘터리 클립
- Spotify: OST 플레이리스트 (iframe 임베드)
- 이미지: Unsplash/Wikimedia (저작권 프리)

</technical_stack>

<investigate_before_answering>
코드를 수정하기 전에 반드시 해당 파일을 읽어라.
열지 않은 파일의 내용을 추측하지 말고, 실제 코드를 확인한 뒤 답변한다.
</investigate_before_answering>

<avoid_overengineering>
요청된 변경만 수행한다. 버그 수정에 주변 코드 정리를 추가하지 않는다.
변경하지 않은 코드에 docstring, 주석, 타입 어노테이션을 추가하지 않는다.
</avoid_overengineering>

<frontend_aesthetics>
따뜻하고 세련된 라이프스타일 매거진 디자인.
밝은 배경(#faf7f2), 세리프 헤딩(Playfair Display), 부드러운 카드 그림자.
Insight Lab의 다크 테마와 대비되는 밝고 따뜻한 톤.
색상 시스템: warm-accent(#c4703f), sage(#6b8f71), blue(#4a7c9b), gold(#b8860b), plum(#8b5e83).
</frontend_aesthetics>

## Repository Structure

```
index.html          — 메인 매거진 목차
output/             — Quarto 렌더링된 콘텐츠 HTML
CLAUDE.md           — 프로젝트 규칙 (이 파일)
```
