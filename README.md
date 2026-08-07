# math-study

연구에 필요한 수학을 목적지에서 거꾸로 짚어 정리한 학습 자료 웹입니다.
1층(계산 도구) → 본편(분포의 계보와 최대엔트로피) → 2층(측도론·복소해석·볼록최적화)
→ 3층(정보기하·변분추론) 순으로 쌓여 있고, `roadmap.html`이 통과 순서를 지정합니다.

## 구성 (파일 14개, 총 372KB)

```
.
├── index.html                     목차 (진입점)
├── roadmap.html                   학습 로드맵 · 의존 도면
├── prob-foundations.html          1층 · 확률론 기초
├── linear-algebra.html            1층 · 선형대수
├── multivariable-calculus.html    1층 · 다변수 미적분
├── real-analysis-intro.html       1층 · 실해석 입문
├── primer.html                    본편 · 측도·해석 프라이머
├── distributions.html             본편 · 분포의 계보와 최대엔트로피
├── measure-theory.html            2층 · 측도론
├── complex-analysis.html          2층 · 복소해석
├── convex-optimization.html       2층 · 볼록최적화
├── information-geometry.html      3층 · 정보기하
├── variational-inference.html     3층 · 변분추론
├── assets/style.css               공용 디자인 토큰·레이아웃
└── README.md
```

수식은 MathJax 3.2.2를 jsDelivr CDN에서 불러와 SVG로 렌더링합니다.
별도로 내려받아 넣어야 할 파일은 없습니다.

## GitHub Pages 배포

저장소에 위 파일들을 올린 뒤,
**Settings → Pages → Build and deployment**에서
Source를 `Deploy from a branch`, Branch를 `main` / `/ (root)`로 지정합니다.
1~2분 뒤 `https://<사용자명>.github.io/<저장소명>/` 에서 열립니다.

모든 링크가 상대 경로이므로 저장소 이름이 무엇이든 그대로 동작합니다.

## 로컬 확인

```bash
python3 -m http.server 8000   # http://localhost:8000
```

## 부록 — 오프라인에서도 수식을 보려면

인터넷 없이 열 일이 있다면 MathJax를 저장소에 직접 넣을 수 있습니다.

```bash
mkdir -p assets
curl -L -o assets/tex-svg.js https://cdn.jsdelivr.net/npm/mathjax@3.2.2/es5/tex-svg.js
sed -i 's#https://cdn.jsdelivr.net/npm/mathjax@3.2.2/es5/tex-svg.js#assets/tex-svg.js#' *.html
```

다만 이 파일은 2.1MB의 한 줄짜리 압축 파일이라 GitHub 웹·모바일에서 미리보기가 되지 않습니다.
모바일에서 저장소를 관리한다면 CDN 방식을 그대로 두는 편이 낫습니다.
