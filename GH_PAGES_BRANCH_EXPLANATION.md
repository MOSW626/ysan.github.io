# gh-pages 브랜치에 대해

## ✅ 좋은 소식: gh-pages 브랜치가 없어도 됩니다!

현재 사용 중인 **GitHub 공식 deploy-pages 액션**은 `gh-pages` 브랜치를 자동으로 생성하거나, GitHub Pages 설정에서 "GitHub Actions"를 선택하면 브랜치 없이도 작동합니다.

## 🔄 두 가지 배포 방법

### 방법 1: GitHub Actions 사용 (현재 설정) - 브랜치 불필요 ✅

**장점:**
- `gh-pages` 브랜치를 수동으로 만들 필요 없음
- GitHub Actions가 자동으로 배포
- 더 깔끔하고 관리하기 쉬움

**설정:**
1. Settings → Pages
2. Source: **GitHub Actions** 선택 (가능한 경우)
3. 또는 자동으로 설정됨

### 방법 2: gh-pages 브랜치 사용 (기존 방법)

만약 `gh-pages` 브랜치를 사용하고 싶다면:

**설정:**
1. Settings → Pages
2. Source: **Deploy from a branch** 선택
3. Branch: `gh-pages` 선택
4. `/ (root)` 선택

**브랜치 생성:**
- GitHub Actions가 자동으로 생성하거나
- 수동으로 생성 가능

## 🚀 현재 상태 확인

### GitHub Pages 설정 확인

1. https://github.com/MOSW626/ys-an.github.io → **Settings** → **Pages**

2. **Source** 섹션 확인:
   - **GitHub Actions** 옵션이 보이면 선택 (권장)
   - 또는 **Deploy from a branch** → `gh-pages` 선택

### Actions에서 자동 생성 확인

- GitHub Actions가 성공적으로 실행되면 `gh-pages` 브랜치가 자동으로 생성될 수 있습니다
- Code 탭 → 브랜치 목록에서 확인 가능

## 📝 요약

- **현재 워크플로우**: `gh-pages` 브랜치 없이도 작동합니다
- **GitHub Pages 설정**: "GitHub Actions"를 소스로 선택하면 브랜치 불필요
- **자동 생성**: Actions가 성공하면 필요시 자동으로 브랜치 생성

## 🔍 확인 방법

```bash
# 로컬에서 원격 브랜치 확인
git fetch origin
git branch -r | grep gh-pages

# GitHub에서 확인
# Code 탭 → 브랜치 드롭다운에서 확인
```

## ✨ 결론

**`gh-pages` 브랜치가 없어도 문제 없습니다!**

현재 설정으로 GitHub Actions가 자동으로 배포를 처리합니다. GitHub Pages 설정만 올바르게 되어 있으면 됩니다.

