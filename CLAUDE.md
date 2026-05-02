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

참고 인물: 박구용 철학 교수의 영화/예술 비평 스타일.

### 존재 이유

"리뷰를 쓰는 것은 역사의 법정에서 예술의 법정으로 전환시키고 확장시키는 행위다."
— 이 매거진은 작품을 예술의 법정에 세우는 행위다. 추천이 아니라 판결이다.

### 참고 레퍼런스

- 박구용 교수 × 김어준 대화: https://youtu.be/3Fxj1h2QMtI
- 핵심 키워드: 블랙홀 한 장면(이명세), 세잔의 사과(존재를 그리다), 스피노자(다중 민주주의), 푸코(일상은 전쟁의 결과), 1650년 네덜란드
- 문명사적 연결의 예시: 사과 하나 → 이브(선악) → 뉴턴(과학) → 세잔(미술 혁명) → 피카소(큐비즘)
- 푸코의 전도: "정상과 비정상, 진리와 비진리, 주체와 타자를 결정해가는 과정이 전쟁이다"

### 최우선 원칙: 블랙홀 한 장면

이명세 감독론에서 나온 핵심 — "서사를 가지고 장면을 배치하는 게 감독이 아니라, 블랙홀처럼 모든 내용을 숨기고 있는 **한 장의 장면**에서 영화를 시작한다."

모든 콘텐츠는 그 작품의 **블랙홀 장면 하나**를 찾는 것에서 시작한다. 그 장면이 왜 모든 것을 빨아들이는지를 밝히면, 나머지는 자연스럽게 풀린다.

### 분량: 감동이 살아있는 깊이

- 핵심 논지는 압축하되, 감정과 여운은 충분히 준다
- 독자가 "아, 나도 그랬는데..." 하고 자기 경험과 연결되는 순간을 만든다
- 촬영 비화나 트리비아도 "왜 이것이 감동인지"를 밝힐 때는 충분히 쓴다
- 차트는 감정의 흐름을 시각화하는 용도 (데이터 나열 아님)

### 세부 원칙

1. **형식을 먼저 읽어라**: "이 작품이 어떻게 설계되었는가"를 해부한다.
2. **예술의 법정에 봉인하라**: 왜 이 작품이 시간을 이기는지 판결을 내린다.
3. **여러 번 봐야 보이는 것을 보여줘라**: 표면 독해 → 설계 독해 → 철학적 독해.
4. **진솔한 고백**: "귀중한 걸 잃었다는 자각" — 개인적 깊이.
5. **인식 전환**: 읽은 후 "아, 그런 거였어?" 하는 충격이 반드시 하나.

## 콘텐츠 톤 — 웃음과 해학의 미학

매거진의 색깔: **세련된 진보의 눈으로 세상을 보되, 날카롭지만 수긍하게 만드는 유머.**

- 박구용 × 김어준 스타일: 무식함을 인정하는 솔직함("나 흐리게 그리는 사람인 줄 알았어"), 그 위에 폭발하는 통찰
- "졌다" — 상대의 말이 너무 좋을 때 인정하는 쾌감. 독자도 글을 읽고 "졌다"고 느끼게
- 해학: 심각한 내용을 무겁지 않게. 웃기면서 깊은 글. 무게 잡지 않되 가볍지도 않은
- 날카롭지만 수긍하는: 비판이 아니라 "아, 그런 거였어?" 하는 깨달음으로 도착
- 세련된 진보: 체제를 의심하되 냉소하지 않는다. 대안을 상상하는 쪽으로 간다
- "사과를 프루트로 봤다" — 이런 순간의 웃음이 글 곳곳에 있어야 한다

금기: 권위적 톤, 가르치는 톤, 무거운 학술 용어 나열, 감동 강요

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
