# 부산 시민 AI 체험의 날

행사 홍보용 단일 HTML 웹페이지입니다.

GitHub Pages 공개 주소: [부산 시민 AI 체험의 날](https://edu8-coder.github.io/busan-event-webpage/)

- 행사 날짜: 2026년 12월 5일
- 장소: 사직야구장
- 실습 시간: 1시간
- 행사 시작·종료 시각 및 제공되지 않은 행사 정보: 미정

## 실행

`event_homepage.html`을 브라우저에서 열면 됩니다. HTML·CSS·SVG가 한 파일에 포함되어 있어 별도 설치나 빌드가 필요하지 않습니다.

## GitHub Pages 배포

저장소의 Settings → Pages에서 Source를 GitHub Actions로 설정합니다. `main` 브랜치의 웹페이지가 변경되면 `.github/workflows/deploy-pages.yml`이 실행됩니다.

배포 과정에서 `event_homepage.html`을 공개 사이트의 `index.html`로 복사합니다. 참고자료·기획 문서·검증 이미지 등은 배포하지 않습니다.

사용자가 제공하지 않은 행사 정보는 ‘미정’으로 표시하고, 행사 정보 변경 시 기획 내용과 페이지를 대조합니다.

배포 설정은 [GitHub Pages 공식 문서](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)를 따릅니다.

## Vercel 배포

공개 운영 페이지: [부산 시민 AI 체험의 날](https://111-xi-blond.vercel.app). Vercel 프로젝트는 `edu8-8241/111`입니다.

Node.js 24에서 `npm run build`를 실행합니다. 외부 패키지 설치 없이 원본 HTML을 `dist/index.html`과 `dist/event_homepage.html`로 복사합니다. Vercel은 `vercel.json`에 지정한 `dist` 폴더만 공개하며, 첫 화면과 `/event_homepage.html`에서 같은 페이지를 제공합니다.

`.vercelignore`는 HTML·빌드 스크립트·배포 설정만 업로드하도록 제한합니다. `data`, `outputs`, 개발 문서, 인증정보는 배포 파일에 포함하지 않습니다. 기존 GitHub Pages 설정은 별도로 유지됩니다.

배포할 Vercel 계정·팀과 프로젝트를 확인하고 `vercel link`로 연결한 뒤 `vercel project inspect --non-interactive`로 대상을 검증합니다. `vercel deploy --prod --skip-domain`으로 운영 빌드를 생성하고 실제 응답을 검증한 다음 `vercel promote <배포 URL>`로 공개합니다.

Vercel 설정 근거: [정적 배포 설정](https://vercel.com/docs/project-configuration/vercel-json).
