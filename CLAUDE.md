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

## 콘텐츠 수준

### 비평의 자세

이 매거진은 추천이 아니라 **해석**이다. 작품이 왜 만들어졌고, 어떻게 설계되었고, 시간이 지나도 살아남을 것인지를 따진다.

### 영감의 원천 (내재화하되 용어를 노출하지 않는다)

아래 사유를 글쓰기의 뼈대로 삼되, **고유명사·전문 용어·출처를 본문에 직접 인용하지 않는다.**
글이 스스로 서게 하고, "누구의 이론을 빌려왔다"는 티를 내지 않는다.

- 한 작품의 모든 것이 압축된 **핵심 장면 하나**를 찾아서 거기서 출발한다
- 표면 → 구조 → 철학, 세 겹으로 읽는다
- 하나의 사물이 시대를 넘어 다른 의미로 변주되는 **문명사적 연결**을 찾는다
- 일상 속 권력 관계, 정상/비정상의 경계를 의심한다
- 자유란 무엇인가 — 자기 본성에서 나온 행위인가, 사회의 명령을 내면화한 것인가

### 최우선 원칙: 핵심 장면 하나

모든 콘텐츠는 그 작품의 **핵심 장면 하나**를 찾는 것에서 시작한다. 영화 전체의 주제, 구조, 감정이 한 장면에 응축되어 있는 곳. 그 장면이 왜 작품 전체를 관통하는지를 밝히면, 나머지는 자연스럽게 풀린다.

단, "핵심 장면"이라는 표현을 매번 반복하지 말 것. 개념을 활용하되 틀에 갇히지 않는다.

### 분량: 감동이 살아있는 깊이

- 핵심 논지는 압축하되, 감정과 여운은 충분히 준다
- 독자가 "아, 나도 그랬는데..." 하고 자기 경험과 연결되는 순간을 만든다
- 촬영 비화나 트리비아도 "왜 이것이 감동인지"를 밝힐 때는 충분히 쓴다
- 차트는 감정의 흐름을 시각화하는 용도 (데이터 나열 아님)

### 세부 원칙

1. **형식을 먼저 읽어라**: "이 작품이 어떻게 설계되었는가"를 해부한다.
2. **시간을 이기는가**: 왜 이 작품이 10년 뒤에도 유효한지 판단한다.
3. **여러 번 봐야 보이는 것을 보여줘라**: 표면 → 구조 → 철학, 세 겹 독해.
4. **진솔한 고백**: 개인적 경험과 연결되는 깊이.
5. **인식 전환**: 읽은 후 "아, 그런 거였어?" 하는 충격이 반드시 하나.

## 콘텐츠 톤 — 웃음과 해학의 미학

매거진의 색깔: **날카롭지만 수긍하게 만드는 유머. 무겁지 않되 가볍지도 않은 글.**

- 솔직함: 모르는 건 모른다고 한다. 그 위에 통찰을 얹는다
- 해학: 심각한 내용을 무겁지 않게. 웃기면서 깊은 글
- 깨달음으로 도착: 비판이 아니라 "아, 그런 거였어?" 하는 순간
- 체제를 의심하되 냉소하지 않는다. 대안을 상상하는 쪽으로 간다

금기:
- 권위적 톤, 가르치는 톤, 감동 강요
- **학자·비평가 고유명사를 본문에 직접 인용** (내재화는 하되, "~가 말했듯이" 식 인용 금지)
- 특정 이론 프레임워크의 용어를 반복 노출 (스피노자, 푸코, 블랙홀 장면 등을 매번 명시하지 않는다)

</instructions>

<technical_stack>

## 기술 스택

R + ggplot2로 차트를 생성한다. Plotly는 파일 용량이 비대해지므로 사용하지 않는다.
시계열/그룹 비교 시각화는 tidyplots 패키지를 우선 사용한다 (ggplot2 래퍼, 코드가 간결하고 출판 품질):
```r
library(tidyplots)
tidyplot(data, x = time, y = score, color = group) %>%
  add_mean_line() %>% add_mean_dot() %>% add_sem_ribbon()
```
tidyplots가 적합하지 않은 복잡한 커스텀 차트는 ggplot2 직접 사용.
Quarto (.qmd)로 보고서를 렌더링하며, 아래 설정을 따른다:

- `lightbox: true` — 이미지 클릭 시 줌인 가능
- `self-contained: true` — 단일 HTML 배포
- `dev: ragg_png` — CJK 폰트 렌더링에 필요
- 폰트: `"Noto Sans CJK KR"` 시스템 폰트를 직접 사용한다. showtext는 Quarto knitr 환경에서 충돌하므로 사용하지 않는다.
- 색상: 6자리 hex만 사용한다 (`"#aaaaaa"`). 3자리 hex(`"#aaa"`)는 Quarto+ragg 조합에서 에러를 발생시킨다.
- 테마: `theme: dark: darkly, light: flatly` — Quarto 내장 다크/라이트 토글 버튼을 활성화한다

## 멀티미디어 요소

### 이미지 (GPT Image API)
- 매주 커버 이미지를 GPT Image API(gpt-image-1)로 생성하여 assets/splash_cover.webp 교체
- **각 토픽 카드 이미지**: assets/{축코드}_{번호}_{이름}.jpg 형식으로 저장. index.html의 card-image 안에 `<img src="assets/..." alt="..." loading="lazy">` 태그로 삽입
- 프롬프트 패턴: "Cinematic magazine cover, Korean text '제목', editorial style, [주제 맞춤 설명], film grain, warm tones"
- 이모지 대신 GPT 생성 매거진 커버 스타일 이미지 사용
- 이미지가 없는 카드는 이모지 유지 (점진적 교체)

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
