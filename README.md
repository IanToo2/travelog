<div align="center">

# ✈️ TravelLog

### 관광지 탐색 · 여행 계획 · 리뷰 공유 서비스 (Back-End)

</div>

> SSAFY 11기 관통 프로젝트(EnjoyTrip) 팀 저장소 [`11th-EnjoyTrip/Back-End`](https://github.com/11th-EnjoyTrip/Back-End)를 개인 포트폴리오용으로 옮긴 사본입니다.  
> 공개를 위해 설정 파일의 DB 접속 정보·JWT 키 등 민감 정보는 커밋 히스토리 전체에서 제거하고 환경변수 참조로 바꿨습니다.  
> 프론트엔드(Vue): [`11th-EnjoyTrip/Front-End`](https://github.com/11th-EnjoyTrip/Front-End)

## 🗓 진행 기간

2024.05.02 ~ 2024.05.23 (약 3주)

## 👥 팀원

| [김정인](https://github.com/IanToo2) | [남경민](https://github.com/nkyungm) | [yh-project](https://github.com/yh-project) |
|:---:|:---:|:---:|
| ![](https://github.com/IanToo2.png?size=100) | ![](https://github.com/nkyungm.png?size=100) | ![](https://github.com/yh-project.png?size=100) |

## 🙋 내 역할 (김정인)

- DB ERD 설계 및 MySQL(RDS) 스키마 설계 단독 담당
- Docker + Jenkins 기반 배포 파이프라인과 Nginx 리버스 프록시 구성 단독 담당
- 오브젝트 스토리지를 활용한 캐싱으로 이미지 로딩 시간을 약 2초에서 0.2초 수준으로 개선
- 회원/인증 API: 회원 CRUD, 로그인/로그아웃, 토큰 발급/재발급, 중복 체크, 비밀번호 관련 기능
- 리뷰 API: 리뷰 CRUD, 작성자/관광지 기준 조회, 좋아요 등록/취소/목록, Top 리뷰
- MyBatis DAO/DTO 구조 정리, 리뷰/회원 도메인 버그 수정, CORS/응답 DTO 안정화

## ⚒️ 주요 기능

| 도메인 | 기능 |
|---|---|
| 회원 (`/member`) | 회원가입, 로그인/로그아웃, JWT 토큰 재발급, 회원 정보 수정/탈퇴, 아이디·이메일·닉네임 중복 체크, 비밀번호 찾기 |
| 관광지 (`/attraction`) | 관광지 목록·상세 조회, 관광지 좋아요 |
| 여행 계획 (`/plan`) | 일자별 여행 계획 작성·수정, 계획 공유, 공유된 계획 조회, 계획 좋아요 |
| 리뷰 (`/review`) | 관광지 리뷰 작성·조회·수정·삭제, 리뷰 좋아요, 베스트 리뷰 |
| 게시판 (`/board`) | 게시글 목록·검색·작성·수정·삭제 |

## 📚 기술 스택

![Java](https://img.shields.io/badge/Java%2017-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot%203.2-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white)
![MyBatis](https://img.shields.io/badge/MyBatis-000000?style=flat-square)
![JWT](https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL%20%28RDS%29-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![Gradle](https://img.shields.io/badge/Gradle-02303A?style=flat-square&logo=gradle&logoColor=white)

## ▶️ 실행

```bash
cd travelog
./gradlew bootRun
```

필요한 환경변수:

| 변수 | 용도 |
|---|---|
| `DB_HOST` | MySQL 호스트 (기본값 `localhost`) |
| `DB_USERNAME` | MySQL 사용자 (기본값 `root`) |
| `DB_PASSWORD` | MySQL 비밀번호 |
| `JWT_SALT` | JWT 서명 키 |
