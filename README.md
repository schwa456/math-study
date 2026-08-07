# math-study

연구에 필요한 수학을 목적지에서 거꾸로 짚어 정리한 학습 자료 웹입니다.
1층(계산 도구) → 본편(분포의 계보와 최대엔트로피) → 2층(측도론·복소해석·볼록최적화)
→ 3층(정보기하·변분추론) 순으로 쌓여 있고, `roadmap.html`이 통과 순서를 지정합니다.

## 구성

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
├── assets/
│   ├── style.css                  공용 디자인 토큰·레이아웃
│   └── tex-svg.js                 MathJax 3.2.2 (SVG 출력, 오프라인 번들)
├── .nojekyll                      GitHub Pages의 Jekyll 처리 비활성화
└── README.md
```

## GitHub Pages 배포

```bash
git init
git add .
git commit -m "학습 자료 웹 초기 커밋"
git branch -M main
git remote add origin https://github.com/<사용자명>/<저장소명>.git
git push -u origin main
```

저장소 **Settings → Pages → Build and deployment**에서
Source를 `Deploy from a branch`, Branch를 `main` / `/ (root)`로 지정합니다.
1~2분 뒤 `https://<사용자명>.github.io/<저장소명>/` 에서 열립니다.

## 로컬 확인

```bash
python3 -m http.server 8000
# http://localhost:8000
```

`file://`로 직접 열어도 동작하지만, 로컬 서버를 쓰는 편이 실제 배포 환경과 같습니다.

## 메모

- 모든 링크는 상대 경로이므로 저장소 이름이 무엇이든 그대로 동작합니다.
- MathJax는 CDN이 아니라 `assets/`에 번들돼 있어 오프라인에서도 수식이 렌더링됩니다.
  첫 페이지에서 한 번 내려받은 뒤에는 브라우저 캐시를 사용합니다.
- 도표는 전부 인라인 SVG이며 외부 이미지 파일이 없습니다.
- 문서를 추가하려면 `assets/style.css`의 토큰과 `.env` / `.checkpoint` 등의
  클래스를 그대로 쓰면 시각적 일관성이 유지됩니다.
