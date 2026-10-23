# Level-Up-Together/.github

[![Metrics](https://img.shields.io/github/actions/workflow/status/Level-Up-Together/.github/metrics.yml?label=Metrics&logo=githubactions&logoColor=white)](https://github.com/Level-Up-Together/.github/actions/workflows/metrics.yml)
[![Update README](https://img.shields.io/github/actions/workflow/status/Level-Up-Together/.github/update-readme.yml?label=Update%20README&logo=githubactions&logoColor=white)](https://github.com/Level-Up-Together/.github/actions/workflows/update-readme.yml)

[Level Up Together](https://github.com/Level-Up-Together)의 GitHub 조직 프로필과 활동 메트릭을 관리하는 저장소입니다.

조직 메인 페이지(<https://github.com/Level-Up-Together>)에 보이는 내용은 `profile/README.md`에서 가져오며,
그 안의 **Recent Repositories** 표는 GitHub Actions가 매일 자동으로 갱신합니다.

## 구성

```text
.
├── profile/
│   └── README.md            # 조직 프로필 페이지에 렌더링되는 파일
├── github-metrics.svg       # lowlighter/metrics가 생성하는 활동 지표 이미지
└── .github/workflows/
    ├── update-readme.yml    # 최근 저장소 표 자동 갱신
    └── metrics.yml          # github-metrics.svg 재생성
```

## 워크플로우

| 워크플로우 | 트리거 | 하는 일 | 필요한 시크릿 |
|:--|:--|:--|:--|
| **Update README with Recent Repos** | 매일 00:00 UTC · `main` push · 수동 | 조직 public 저장소 중 최근 갱신 5개를 조회해 `profile/README.md`의 마커 사이 표를 교체하고 커밋 | 없음 (`GITHUB_TOKEN`) |
| **Metrics** | 매일 00:00 UTC · `main` push · 수동 | 조직 계정(`metrics.yml`의 `user`) 기준 활동·언어 통계를 `github-metrics.svg`로 렌더링하고 커밋 | `METRICS_TOKEN` |

### 프로필 README 수정 시 주의

`profile/README.md`에서 아래 두 마커 사이는 워크플로우가 덮어씁니다. 직접 수정해도 다음 실행 때 사라집니다.

```html
<!-- REPOS_START -->
...자동 생성 영역...
<!-- REPOS_END -->
```

마커를 지우면 표 갱신이 조용히 멈추므로, 섹션을 옮기더라도 마커 두 줄은 반드시 남겨 두세요.

Recent Repositories 표에는 **공개 저장소만** 나옵니다. 비공개 저장소는 Actions 기본 토큰으로 조회되지 않고, 방문자가 열 수도 없기 때문입니다.
표에 설명을 보이게 하려면 각 공개 저장소의 Description(About)을 채워 두세요.

### 수동 실행

```bash
gh workflow run "Update README with Recent Repos" --repo Level-Up-Together/.github
gh workflow run Metrics --repo Level-Up-Together/.github
gh run list --repo Level-Up-Together/.github --limit 5
```

### METRICS_TOKEN 관리

`lowlighter/metrics`는 Actions 기본 토큰으로는 사용자 통계를 읽지 못해 별도의 Personal Access Token이 필요합니다.
Metrics 실행 로그에 `Bad credentials`가 보이면 토큰이 만료된 것이므로 재발급 후 시크릿을 교체합니다.

- 종류: Personal access token (classic)
- 스코프: `public_repo`, `read:org`, `read:user` — 비공개 기여까지 집계하려면 `public_repo` 대신 `repo`
- 발급 계정: 조직 통계를 읽어야 하므로 Level-Up-Together 조직 멤버(소유자) 계정으로 발급
- 등록 위치: 이 저장소 **Settings → Secrets and variables → Actions → `METRICS_TOKEN`**

```bash
gh secret set METRICS_TOKEN --repo Level-Up-Together/.github
gh workflow run Metrics --repo Level-Up-Together/.github   # 교체 후 즉시 확인
```

## 관련 링크

- 조직 프로필: <https://github.com/Level-Up-Together>
- 서비스: <https://www.level-up-together.com>
- 문의: <ceo@pink-spider.io>
