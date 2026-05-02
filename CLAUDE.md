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

## 콘텐츠 톤

- 따뜻하고 세련된 트렌드 잡지 스타일
- 주말에 편하게 읽을 수 있는 에세이 톤
- 개인적 감상과 객관적 분석의 균형
- 힐링과 교양을 동시에 제공
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

- 유튜브/Spotify 임베드로 OST, 인터뷰, 트레일러 삽입
- 이미지: 영화 스틸컷, 책 표지, 여행 사진 (저작권 주의, Unsplash/Wikimedia 활용)
- Audio: Spotify 플레이리스트 임베드 또는 추천 링크

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
