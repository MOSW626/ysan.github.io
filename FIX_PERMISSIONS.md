# GitHub Actions 권한 오류 해결 방법

## 🔴 문제
```
remote: Permission to MOSW626/ys-an.github.io.git denied to github-actions[bot].
fatal: unable to access 'https://github.com/MOSW626/ys-an.github.io.git/': The requested URL returned error: 403
```

## ✅ 해결 방법

### 방법 1: GitHub 저장소에서 권한 설정 (권장)

1. **GitHub 저장소로 이동**
   - https://github.com/MOSW626/ys-an.github.io

2. **Settings** 탭 클릭

3. **Actions** → **General** 이동

4. **Workflow permissions** 섹션에서:
   - ✅ **Read and write permissions** 선택
   - ✅ **Allow GitHub Actions to create and approve pull requests** 체크

5. **Save** 클릭

6. **다시 배포 트리거**
   - `main` 브랜치에 빈 커밋 푸시하거나
   - Actions 탭에서 "Re-run all jobs" 클릭

### 방법 2: 워크플로우 파일에 권한 명시 (추가 보안)

워크플로우 파일에 `permissions`를 명시적으로 추가할 수 있습니다.

## 📝 참고사항

- 이 설정은 GitHub Actions가 저장소에 푸시할 수 있도록 허용합니다
- `gh-pages` 브랜치에 배포하기 위해 필요합니다
- 보안상 안전하며, GitHub Actions는 자동으로 생성된 토큰을 사용합니다

## 🔄 설정 후 확인

1. Settings → Actions → General에서 설정 확인
2. Actions 탭에서 최신 워크플로우 실행
3. 배포가 성공하는지 확인

