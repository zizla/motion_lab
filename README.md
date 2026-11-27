# Motion Lab — @zizla

움직임으로 읽는 데이터 과학. 알고리즘이 데이터 위에서 실제로 계산되는 과정을 Canvas 2D 모션으로 보여 주는 교육용 인터랙티브 웹앱 모음입니다.
외부 라이브러리·CDN·폰트 요청 없이 단일 HTML로 동작하며, GitHub Pages에서 바로 열립니다.

**라이브** — https://zizla.github.io/motion_lab/

## 구성

| 경로 | 내용 | 상태 |
| --- | --- | --- |
| `/` (`index.html`) | 통합 허브 — 두 앱으로 가는 카드와 각 앱의 모션 미리보기 | 배포됨 |
| `/ml9/` (`ml9/index.html`) | **9대 ML 알고리즘 모션** — 선형/로지스틱 회귀, SVM, KNN, PCA, k-Means, 결정 트리, 랜덤 포레스트, 가우시안 나이브 베이즈 | 배포됨 |
| `/eda/` (`eda/index.html`) | **탐색적 데이터 분석 EDA 모션** — 히스토그램, 결측값 대체, 마할라노비스 이상치, 피어슨 r, 계절성 분해, 상자그림 | 준비 중 (파일만 올리면 허브에서 바로 열림) |

## 9대 ML 알고리즘 모션 (`/ml9/`)

9개 카드가 각자의 데이터에서 실시간으로 학습·수렴하는 과정을 그립니다.

| # | 알고리즘 | 애니메이션 | 파라미터 |
| --- | --- | --- | --- |
| 01 | Linear Regression | 경사하강법으로 직선이 이동, 잔차선·손실 곡선 | 학습률 η |
| 02 | Logistic Regression | 시그모이드 경계 회전·이동, 배경은 예측 확률 | 학습률 η |
| 03 | SVM | 힌지 손실 하강, 마진 밴드·서포트 벡터 강조 | C |
| 04 | K-Nearest Neighbors | 쿼리 이동 → K개 이웃·거리 원·투표 | K |
| 05 | PCA | 주성분 축 회전 후 PC1 정사영 | 점 개수 n |
| 06 | k-Means | 할당 → 중심 이동 반복, 관성 표시 | 군집 수 k |
| 07 | Decision Tree | 지니 최소 분할선이 순차 등장, 영역 분할 | 최대 깊이 |
| 08 | Random Forest | 트리가 하나씩 추가되며 앙상블 경계 정교화 | 트리 수 T |
| 09 | Gaussian Naive Bayes | 1σ·2σ 등고선 타원 + 2차 결정 경계 + 확률 프로브 | 클래스 퍼짐 |

조작: 재생/일시정지, 리셋, 속도 0.25×–3×, 확대 보기↔9개 그리드, 한국어↔English, ∑ 수식·해설 모달.
키보드 `Space` · `←`/`→` · `Esc` · `G`. 카드를 클릭하면 확대되고 슬라이더로 파라미터를 바꿀 수 있습니다.

## 배포

`main`과 `gh-pages` 브랜치에 같은 커밋이 올라가 있고, GitHub Pages는 `gh-pages` 브랜치 루트에서 서빙합니다. `.nojekyll`로 Jekyll 빌드를 건너뜁니다.

```bash
git clone https://github.com/zizla/motion_lab.git
cd motion_lab && python3 -m http.server 8000   # → http://localhost:8000/
```

`qa/`에는 데스크톱·모바일·확대·모달 검증 스크린샷이 있습니다.
