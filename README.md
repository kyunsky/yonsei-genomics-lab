# 연세대학교 의과대학 진단검사의학과 유전체 연구소 — 홈페이지

Hugo 정적 사이트 + GitHub Pages 자동 배포 스타터입니다.
Git/Markdown만으로 모든 콘텐츠를 관리할 수 있습니다.

## 1. 최초 설정 (한 번만)

1. GitHub에 새 저장소를 만듭니다. 예: `yonsei-genomics-lab`
2. 이 폴더 전체를 그 저장소에 push 합니다.
   ```bash
   git init && git add . && git commit -m "init"
   git branch -M main
   git remote add origin https://github.com/<github-id>/yonsei-genomics-lab.git
   git push -u origin main
   ```
3. GitHub 저장소 → **Settings → Pages → Source** 를 `GitHub Actions` 로 변경
4. `hugo.toml` 의 `baseURL` 을 실제 주소로 수정
   - 프로젝트 사이트: `https://<github-id>.github.io/yonsei-genomics-lab/`
   - 커스텀 도메인:   `https://lab.yonsei.ac.kr/` (+ `static/CNAME` 파일에 도메인 한 줄)
5. push 하면 Actions가 자동으로 빌드·배포합니다. (Actions 탭에서 진행 확인)

## 2. 로컬 미리보기 (서버 환경)

```bash
# Hugo extended 설치 후
hugo server -D
# http://localhost:1313 에서 확인
```

## 3. 콘텐츠 수정 방법

| 무엇을 | 어디를 |
|--------|--------|
| 연구소 소개 | `content/about.md` |
| 사이트 제목·통계·메뉴 | `hugo.toml` |
| 연구 분야 카드 | `data/research_areas.yaml` |
| 협력 기관 | `data/partners.yaml` |
| 구성원 추가 | `content/people/` 에 `.md` 파일 추가 (`role`: PI/교수/연구교수/박사후연구원/대학원생/연구원) |
| 논문 추가 | `content/publications/` 에 `.md` 추가 (`year` 기준 자동 정렬) |
| 프로젝트 추가 | `content/projects/` 에 `.md` 추가 (`status`: 진행중/완료) |

새 항목은 기존 파일을 복사해서 수정하는 게 가장 빠릅니다.
push 하면 1~2분 내 사이트에 자동 반영됩니다.

## 4. 디렉토리 구조

```
hugo.toml                 # 사이트 설정
content/                  # 모든 페이지 (Markdown)
  ├ about.md  contact.md
  ├ people/  projects/  publications/  partners/
data/                     # 연구분야·협력기관 (YAML)
layouts/                  # HTML 템플릿
assets/css/main.css       # 디자인
.github/workflows/        # 자동 배포
```
