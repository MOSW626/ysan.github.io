# 프로젝트 설명 커스터마이징 가이드

## 📝 GitHub 프로젝트 설명 추가하기

### 방법 1: 수동 설명 추가 (권장)

`src/data/githubProjects.js` 파일을 열고 프로젝트 설명을 추가하세요:

```javascript
export const githubProjectDescriptions = {
  'mosw626.github.io': '개인 포트폴리오 웹사이트입니다. React를 사용하여 제작했습니다.',
  'mecha_ws': 'KAIST 메카트로닉스 시스템 설계 과목의 자율주행 로봇 프로젝트 워크스페이스입니다.',
  'segway': '2025 MR 프로젝트 - 다리형 세그웨이 로봇 개발 프로젝트입니다.',
  // 추가 프로젝트...
};
```

**장점:**
- 완전한 제어 가능
- 한글 깨짐 문제 없음
- 원하는 설명을 정확히 작성 가능

### 방법 2: GitHub 저장소에 description 추가

GitHub 저장소의 Settings → General에서 Description을 추가하면 자동으로 표시됩니다.

## 🔧 Projects 컴포넌트 수정하기

### 주요 파일 위치

- **GitHub 프로젝트 데이터**: `src/data/githubProjects.js`
- **Notion 프로젝트 데이터**: `src/data/notionProjects.js`
- **Projects 컴포넌트**: `src/components/Projects.js`
- **프로젝트 모달**: `src/components/ProjectModal.js`

### 프로젝트 추가/수정

1. **Notion 프로젝트 추가**: `src/data/notionProjects.js` 수정
2. **GitHub 프로젝트 설명**: `src/data/githubProjects.js` 수정
3. **스타일 변경**: `src/components/Projects.css` 수정

## 📚 참고

- 프로젝트 설명은 `githubProjectDescriptions`에 추가한 것이 최우선으로 표시됩니다
- 없으면 GitHub API에서 가져온 description 사용
- 그것도 없으면 저장소 내용을 분석하여 자동 생성

