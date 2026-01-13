# 배포 방법 변경 - GitHub 공식 액션 사용

## 🔄 변경 사항

`peaceiris/actions-gh-pages` 대신 GitHub의 공식 `actions/deploy-pages` 액션을 사용하도록 변경했습니다.

## ✅ 장점

1. **GitHub 공식 지원**: GitHub에서 직접 제공하는 액션
2. **더 나은 권한 처리**: GitHub Pages 전용 권한 시스템 사용
3. **더 안정적**: 공식 액션이므로 더 안정적이고 업데이트가 지속됨

## 📝 필요한 추가 설정

### GitHub Pages 설정 확인

1. **Settings** → **Pages** 이동
2. **Source** 섹션:
   - **Deploy from a branch** 선택
   - **Branch**: `gh-pages` 선택 (또는 자동으로 설정됨)
   - 또는 **GitHub Actions** 선택 (새로운 방법)

### GitHub Actions 권한 (이미 설정했다면 스킵)

1. **Settings** → **Actions** → **General**
2. **Workflow permissions**:
   - ✅ **Read and write permissions**
   - ✅ **Allow GitHub Actions to create and approve pull requests**

## 🚀 작동 방식

새 워크플로우는 두 단계로 나뉩니다:

1. **build**: 프로젝트 빌드 및 아티팩트 업로드
2. **deploy**: GitHub Pages에 배포

## 🔍 문제 해결

### 여전히 권한 오류가 발생하는 경우

1. **저장소 설정 확인**
   - Settings → Actions → General
   - Workflow permissions가 "Read and write"인지 확인

2. **Pages 설정 확인**
   - Settings → Pages
   - Source가 올바르게 설정되었는지 확인

3. **Actions 로그 확인**
   - Actions 탭에서 각 단계의 로그 확인
   - 어느 단계에서 실패하는지 확인

### 빌드는 성공하지만 배포가 실패하는 경우

1. **Pages 설정 확인**
   - Settings → Pages에서 "GitHub Actions" 옵션 선택 시도

2. **환경 변수 확인**
   - deploy 단계의 environment 설정 확인

## ✨ 완료 후

배포가 성공하면:
- Actions 탭에서 모든 단계가 ✅ 표시
- Settings → Pages에서 배포 상태 확인
- 사이트 접속: https://mosw626.github.io/ys-an.github.io

## 📚 참고

- GitHub 공식 문서: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow

