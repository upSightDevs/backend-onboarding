# 🏢 **업사이트 백엔드 온보딩**

안녕하세요!  
업사이트 팀의 백엔드 개발자로 합류하신 것을 진심으로 축하드립니다! 🎉  
이 문서는 빠르게 팀의 개발 환경과 방향에 익숙해질 수 있도록 돕기 위해 작성되었습니다.

---

## 📚 **테크 스펙**

| **기술 스택**         | **버전** |
|-----------------------|----------|
| Python               | 3.10     |
| Django               | 4.2.9    |
| Django REST Framework | 3.15.1   |
| PostgreSQL           | 16.4     |
| pytest-django        | 4.8      |
|djangorestframework-simplejwt|5.3.1 |
---

## 📏 **컨벤션**

- 팀의 코드 작성 규칙은 아래 링크를 참고해주세요:  
  [코드 컨벤션 문서 바로가기](https://www.notion.so/9dfc3389347c4e608f9622799a0197e3)

---

## 🛠 **기능 요구사항**

### 1️⃣ **카테고리 관리**
- 사용자는 게시글 작성 시 특정 카테고리를 선택하거나 새 카테고리를 생성할 수 있습니다.
- 카테고리는 **계층 구조**를 가질 수 있습니다.  
  예: `IT > 프로그래밍 > Python`
- 카테고리는 **공개/비공개** 상태를 설정할 수 있습니다.
  - **공개 카테고리**: 모든 사용자가 접근 가능.  
  - **비공개 카테고리**: 작성자 본인만 접근 가능.  

### 2️⃣ **게시글 관리**
- 사용자는 게시글을 **작성/수정/삭제**할 수 있습니다.
  - 본인이 작성한 게시글만 수정/삭제 가능합니다.
- 게시글은 카테고리의 **공개/비공개 상태를 기본적으로 따릅니다**.  
  단, 개별 게시글 설정으로 이를 덮어쓸 수 있습니다.
- 게시글 이동 가능: 게시글을 다른 카테고리로 이동할 수 있습니다.
- 카테고리가 삭제되면, 해당 카테고리에 속한 게시글은 **'미분류' 카테고리**로 이동됩니다.
- **소프트 삭제** 기능 지원:  
  삭제된 게시글은 '삭제됨' 상태로 표시됩니다.

### 3️⃣ **게시글 조회**
- 사용자는 카테고리별로 게시글을 조회할 수 있습니다.
  - 상위 카테고리를 조회하면, **하위 카테고리의 게시글도 함께 표시**됩니다.  
    예: `IT` 카테고리를 조회 → `IT > 프로그래밍`, `IT > 프로그래밍 > Python` 게시글 포함.
- **정렬/검색 기능 지원**:
  - 정렬: 날짜 순, 제목 순
  - 검색: 제목 및 내용
- 게시글 조회 시, 기본적으로 **20개씩 Pagination** 처리됩니다.

### 4️⃣ **댓글 관리**
- 사용자는 자신이 작성한 댓글만 수정/삭제할 수 있습니다.
- 댓글에도 **소프트 삭제** 기능이 적용됩니다.

---

## 📜 **제약사항**
- [ ] **JWT 인증 시스템**을 사용한 로그인 구현.
- [ ] RESTful API 설계 원칙을 준수.
- [ ] **pytest-django**를 활용하여 테스트 코드 작성 (테스트 커버리지 90% 이상).
- [ ] API 문서를 **README.md**에 포함.
- [ ] **개발 환경**과 **배포 환경**이 분리된 구조로 설계.

---

## 🧪 **테스트 요구사항**
[ ] 모든 기능은 **pytest-django**로 테스트되어야 합니다.
[ ] 테스트 커버리지는 90% 이상이어야 합니다.

---

## 🚀 **개발 및 배포**

### **1. 로컬 개발 환경 구성**
1. **Python 가상환경 설정**:
   ```bash
   python -m venv venv
   source venv/bin/activate
