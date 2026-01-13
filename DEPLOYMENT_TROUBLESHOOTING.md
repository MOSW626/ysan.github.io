# 배포가 deployment_queued에서 멈추는 문제 해결 가이드

## 🔴 문제 증상
GitHub Pages 배포가 `deployment_queued` 상태에서 계속 머물러 있습니다.

## 🔍 원인 분석

### 1. deploy job에 permissions 부족
- deploy job에 명시적인 `pages: write` 권한이 필요합니다
- ✅ **해결됨**: 워크플로우에 permissions 추가

### 2. GitHub Pages 설정 문제
- Settings → Pages에서 Source가 올바르게 설정되지 않았을 수 있습니다

### 3. build job이 완료되지 않음
- build 단계가 실패하거나 아직 실행 중일 수 있습니다

## ✅ 해결 방법

### 1단계: GitHub Actions 확인

1. **Actions 탭**으로 이동
   - https://github.com/MOSW626/ysan.github.io/actions

2. **최신 워크플로우 실행** 클릭

3. **각 단계 확인**:
   - ✅ **build** 단계가 성공했는지 확인
   - ⏳ **deploy** 단계 상태 확인
   - ❌ 실패한 단계가 있다면 에러 메시지 확인

### 2단계: GitHub Pages 설정 확인

1. **Settings** → **Pages** 이동

2. **Source** 섹션 확인:
   - **GitHub Actions** 선택 (권장)
   - 또는 **Deploy from a branch** → `gh-pages` 선택

3. **Build and deployment** 섹션:
   - Source: **GitHub Actions** 선택
   - Branch: 자동으로 설정됨

### 3단계: Environment 설정 확인

1. **Settings** → **Environments** 이동
2. **github-pages** 환경이 있는지 확인
3. 없으면 자동으로 생성됩니다

### 4단계: 권한 재확인

1. **Settings** → **Actions** → **General**
2. **Workflow permissions**:
   - ✅ **Read and write permissions** 선택
   - ✅ **Allow GitHub Actions to create and approve pull requests** 체크

## 🔧 워크플로우 수정 완료

다음 변경사항이 적용되었습니다:
- deploy job에 명시적인 `permissions` 추가
- `pages: write` 및 `id-token: write` 권한 명시

## 🚀 다음 단계

1. **새 커밋 푸시** (이미 완료됨)
2. **Actions 탭에서 새 워크플로우 확인**
3. **build 단계가 성공하는지 확인**
4. **deploy 단계가 진행되는지 확인**

## ⚠️ 여전히 문제가 발생하는 경우

### 대안 1: 수동 배포
```bash
npm run build
npm run deploy
```

### 대안 2: 간단한 워크플로우로 변경
`peaceiris/actions-gh-pages` 액션 사용 (이전 방법)

### 대안 3: GitHub Pages 설정 재설정
1. Settings → Pages
2. Source를 다른 옵션으로 변경 후 저장
3. 다시 GitHub Actions로 변경

## 📝 체크리스트

- [ ] Actions 탭에서 build 단계 성공 확인
- [ ] Settings → Pages에서 GitHub Actions 선택 확인
- [ ] Settings → Actions → General에서 권한 확인
- [ ] 새 워크플로우 실행 확인

## 🔗 참고

- GitHub Pages 문서: https://docs.github.com/en/pages
- GitHub Actions 문서: https://docs.github.com/en/actions

