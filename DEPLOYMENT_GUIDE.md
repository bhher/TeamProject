# 🚀 GitHub Pages 자동 배포 가이드

## 📋 사전 준비사항

### 1. 현재 설정 확인
- ✅ 저장소 URL: `https://github.com/bhher/TeamProject.git`
- ✅ Base Path: `/TeamProject/`
- ✅ GitHub Actions 워크플로우 설정 완료

---

## 🔧 Step 1: Git 저장소 초기화 및 설정

### 1-1. Git 초기화 (아직 안 했다면)
```bash
git init
```

### 1-2. 원격 저장소 설정
```bash
# 원격 저장소 추가
git remote add origin https://github.com/bhher/TeamProject.git

# 또는 기존 원격 저장소가 있다면 변경
git remote set-url origin https://github.com/bhher/TeamProject.git

# 확인
git remote -v
```

### 1-3. 브랜치 이름 확인 및 설정
```bash
# 현재 브랜치 확인
git branch

# main 브랜치가 없다면 생성
git checkout -b main

# 또는 master 브랜치 사용 시
git checkout -b master
```

---

## 📤 Step 2: 파일 커밋 및 푸시

### 2-1. 모든 파일 추가
```bash
git add .
```

### 2-2. 커밋
```bash
git commit -m "Initial commit: React + Vite 프로젝트 설정 및 자동 배포 구성"
```

### 2-3. GitHub에 푸시
```bash
# main 브랜치인 경우
git push -u origin main

# master 브랜치인 경우
git push -u origin master
```

---

## ⚙️ Step 3: GitHub 저장소 설정

### 3-1. GitHub Pages 활성화
1. GitHub 저장소 페이지로 이동: `https://github.com/bhher/TeamProject`
2. **Settings** 탭 클릭
3. 왼쪽 메뉴에서 **Pages** 클릭
4. **Source** 섹션에서:
   - **"Deploy from a branch"** 선택 해제
   - **"GitHub Actions"** 선택 ✅
5. 저장 (자동 저장됨)

### 3-2. GitHub Actions 권한 설정
1. 같은 Settings 페이지에서 **Actions** → **General** 클릭
2. **Workflow permissions** 섹션에서:
   - ✅ **"Read and write permissions"** 선택
   - ✅ **"Allow GitHub Actions to create and approve pull requests"** 체크
3. 맨 아래 **Save** 버튼 클릭

---

## 🔍 Step 4: 자동 배포 확인

### 4-1. Actions 탭에서 확인
1. GitHub 저장소 페이지에서 **Actions** 탭 클릭
2. "Deploy to GitHub Pages" 워크플로우가 실행되는지 확인
3. 워크플로우 클릭하여 진행 상황 확인
4. ✅ 초록색 체크 표시가 나타나면 배포 완료!

### 4-2. 배포된 사이트 확인
- 배포 완료 후 약 1-2분 후 접속 가능
- URL: `https://bhher.github.io/TeamProject/`

---

## 🎯 이후 업데이트 방법

### 코드 수정 후 자동 배포
```bash
# 1. 변경사항 확인
git status

# 2. 파일 추가
git add .

# 3. 커밋
git commit -m "변경 내용 설명"

# 4. 푸시 (자동으로 배포 시작됨)
git push origin main
```

---

## ⚠️ 문제 해결

### 배포가 안 될 때
1. **Actions 탭 확인**: 오류 메시지 확인
2. **Settings → Pages 확인**: Source가 "GitHub Actions"로 설정되어 있는지 확인
3. **Settings → Actions → General**: 권한 설정 확인
4. **브랜치 이름 확인**: `main` 또는 `master`인지 확인

### 카카오 지도가 안 보일 때
1. 카카오 개발자 콘솔 접속: https://developers.kakao.com/
2. 내 애플리케이션 선택
3. **플랫폼 설정** → **Web 플랫폼 등록**
4. 사이트 도메인에 추가:
   - `https://bhher.github.io`
   - `https://bhher.github.io/TeamProject`

---

## 📝 체크리스트

배포 전 확인사항:
- [ ] `package.json`의 `homepage`가 올바른지 확인
- [ ] `vite.config.js`의 `base` 경로가 `/TeamProject/`인지 확인
- [ ] `.github/workflows/deploy.yml` 파일이 있는지 확인
- [ ] 모든 파일이 커밋되었는지 확인 (`git status`)
- [ ] GitHub 저장소가 생성되어 있는지 확인
- [ ] GitHub Pages Source가 "GitHub Actions"로 설정되어 있는지 확인
- [ ] GitHub Actions 권한이 "Read and write"로 설정되어 있는지 확인

---

## 🎉 완료!

모든 설정이 완료되면 `main` 또는 `master` 브랜치에 푸시할 때마다 자동으로 배포됩니다!

