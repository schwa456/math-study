# math-study

고등학교 수학까지만 기억나는 상태에서 시작해 연구에 쓰이는 도구까지 이어지는
열여섯 편의 강의 자료입니다. 여섯 분야 × 세 난이도로 배치되어 있고,
`roadmap.html`이 격자와 커리큘럼 순서를 안내합니다.

초급 문서에는 학습 목표, 단계별 풀이가 붙은 예제, 자주 하는 실수,
연습문제와 해답이 포함되어 있습니다. 중급부터는 정리와 증명 중심입니다.

## 구성 (파일 18개)

```
.
├── index.html                     목차 (진입점)
├── roadmap.html                   분야 × 난이도 격자 · 커리큘럼 순서
│
│   ── 초급 ──
├── math-language.html             수학의 언어 (집합·논리·함수·증명)
├── calculus-basics.html           미적분 입문
├── linear-algebra-basics.html     선형대수 입문
├── probability-basics.html        확률·통계 입문
│
│   ── 중급 ──
├── linear-algebra.html            선형대수 (스펙트럴 정리·사영)
├── multivariable-calculus.html    다변수 미적분
├── real-analysis-intro.html       해석학 입문
├── prob-foundations.html          확률론 기초
├── primer.html                    측도·해석 프라이머
│
│   ── 고급 ──
├── distributions.html             분포의 계보와 최대엔트로피
├── measure-theory.html            측도론
├── complex-analysis.html          복소해석
├── convex-optimization.html       볼록최적화
├── information-geometry.html      정보기하
├── variational-inference.html     변분추론
│
├── assets/style.css               공용 디자인 토큰·레이아웃
└── README.md
```

수식은 MathJax 3.2.2를 jsDelivr CDN에서 불러와 SVG로 렌더링합니다.
도표는 전부 인라인 SVG이며 외부 이미지 파일이 없습니다.

## GitHub Pages 배포

파일을 저장소 루트에 올린 뒤
**Settings → Pages → Build and deployment**에서
Source를 `Deploy from a branch`, Branch를 `main` / `/ (root)`로 지정합니다.
모든 링크가 상대 경로이므로 저장소 이름과 무관하게 동작합니다.

HTML 16개는 루트에, `style.css`는 `assets/` 안에 있어야 합니다.

## 로컬 확인

```bash
python3 -m http.server 8000   # http://localhost:8000
```

## 부록 — 오프라인에서도 수식을 보려면

```bash
mkdir -p assets
curl -L -o assets/tex-svg.js https://cdn.jsdelivr.net/npm/mathjax@3.2.2/es5/tex-svg.js
sed -i 's#https://cdn.jsdelivr.net/npm/mathjax@3.2.2/es5/tex-svg.js#assets/tex-svg.js#' *.html
```

이 파일은 2.1MB의 한 줄짜리 압축 파일이라 GitHub 웹·모바일에서 미리보기가 되지 않습니다.
모바일에서 저장소를 관리한다면 CDN 방식을 그대로 두는 편이 낫습니다.
