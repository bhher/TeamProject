# React + Vite 프로젝트

영화 추천 및 맛집 추천 서비스

## 로컬 실행

```bash
npm install
npm run dev
```

## 빌드

```bash
npm run build
npm run preview
```

## GitHub Pages 배포

### 1. GitHub 저장소 설정

1. 저장소 Settings → Pages로 이동
2. Source를 **"GitHub Actions"**로 선택
3. Settings → Actions → General에서:
   - "Workflow permissions" → **"Read and write permissions"** 선택
   - "Allow GitHub Actions to create and approve pull requests" 체크

### 2. 자동 배포

- `main` 또는 `master` 브랜치에 푸시하면 자동으로 배포됩니다
- Actions 탭에서 배포 진행 상황을 확인할 수 있습니다
- 배포 완료 후 `https://bhher.github.io/TeamProject/` 에서 확인 가능

### 3. 수동 배포 (선택사항)

```bash
npm run deploy
```

## 주요 설정

- **Base Path**: `/TeamProject/` (vite.config.js)
- **Router**: HashRouter 사용 (GitHub Pages 호환)
- **배포 방식**: GitHub Actions 자동 배포 (더 이상 `gh-pages` 브랜치 사용 안 함)
