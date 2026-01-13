# GitHub Actions만 사용하는 배포 설정

## ✅ 변경 사항

### 1. 워크플로우 업데이트 완료

이제 `gh-pages` 브랜치 없이 GitHub Actions에서 직접 배포합니다:
- `actions/upload-pages-artifact@v3`: 빌드된 파일을 아티팩트로 업로드
- `actions/deploy-pages@v4`: GitHub Pages에 직접 배포

### 2. GitHub Pages 설정 변경 (필수!)

**Settings** → **Pages**에서:

1. **Build and deployment** 섹션:
   - ✅ **"GitHub Actions"** 선택
   - ❌ "Deploy from a branch" 선택 해제
2. **Save** 클릭

### 3. gh-pages 브랜치 삭제 (선택사항)

`gh-pages` 브랜치가 더 이상 필요하지 않으므로 삭제할 수 있습니다:

```bash
# 로컬에서 삭제
git branch -D gh-pages

# 원격에서 삭제
git push origin --delete gh-pages
```

## 🔍 작동 방식

1. `main` 브랜치에 푸시
2. GitHub Actions가 자동으로 트리거
3. React 앱 빌드
4. 빌드된 파일을 아티팩트로 업로드
5. GitHub Pages에 직접 배포
6. `gh-pages` 브랜치 불필요!

## ⚠️ 주의사항

- GitHub Pages 설정을 "GitHub Actions"로 변경해야 합니다
- 첫 배포 후 몇 분 정도 걸릴 수 있습니다
- `deployment_queued` 상태가 보일 수 있지만 정상입니다

## ✨ 장점

- `gh-pages` 브랜치 관리 불필요
- 더 깔끔한 저장소 구조
- GitHub의 최신 배포 방식 사용
- 자동 배포 완전 자동화

