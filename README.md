# 🐳 JIKGORAE-Project-records
#### 본 저장소의 목적은 [우아한테크코스 팀 프로젝트](https://github.com/woowacourse-teams) 를 진행하면서 했던 내용들을 정리하는 것입니다.  

## 직고래 
당신이 속한 그룹 어디든 당신이 원하는 것을 사고 파세요. 조직 중고 거래, 직고래 🐳

> 따뜻한 교류가 있는 조직 벼룩시장을 꿈꾸다

- [직고래 Github](https://github.com/woowacourse-teams/2020-seller-lee-company)
- [직고래 소개](https://sites.google.com/woowahan.com/wooteco-demo/직고래)

## 기술 스택
![stack](images/stack.png)

## 프로젝트 아키텍처
![project_architectures](images/project_architectures.png)
## CI/CD
![CICD](images/CICD.png)
- CI
    - 정기적인 빌드 및 테스트(유닛테스트 및 통합테스트)를 거쳐 공유 레포지터리에 병합되는 과정
- CD
    - 레포지터리에서 실시간으로 프로덕션 환경으로 배포하는 작업을 자동화하는 것     

사용자의 피드백을 적극 반영하기 위해 짧은 주기로 서비스를 배포하고 있습니다.
잦은 빌드와 배포로 인해 번거로움을 느꼈고 CI/CD 환경을 구성하여문제를 해결하였습니다.

## My Task
- 게시글 전체 조회 시 JPA 연관 관계에 의해 나타나는 N+1문제를 발견해 성능 개선
    - 100개의 게시글 전체 조회 시(findAll) 201번의 쿼리를 만들었던 애플리케이션을 3번의 쿼리로 줄이는 성능 개선을 함
- 게시글 상세조회와 판매내역에 관한 HTTP API를 개발
- 회원가입/로그인 개발(Spring Security, Kakao OAuth)
    - Form 형식의 로그인을 OAuth로 변경
    - Spring Interceptor 기반이었던 JWT 인증 로직을 Filter로 변경
- 보안 서버 구축
    - Https 를 적용하고, Spring Security와 Nginx를 사용해 보안의 취약점을 파악하고 보안 수준을 높임
    - SSL server 등급을 측정할 수 있는 사이트에서 가장 좋은 스코어 획득
- docker 컨테이너를 이용해 무중단 서버 배포 구현
    - Blue-Green 방식의 배포전략을 사용해 무중단 배포 스크립트 작성
- React-Native(TypeScript)를 이용해 모바일 애플리케이션의 컴포넌트와 스크린을 개발
    - 닉네임 수정, 게시글 상세 조회, 태그, 판매상태 등 컴포넌트, 스크린 개발

## Layered Architecture
도메인 설계 할 때 도메인을 관심사 별로 묶고 **모듈 간의 의존성은 최소화하고, 응집성은 최대화** 할 수 있도록 Layered Architecture 따라 설계를 하였습니다.

```gherkin
api
  ├── article
  │   ├── application
  │   ├── domain
  │   ├── exception
  │   ├── presentation
  │   └── query
  ├── articlefavoritecount
  │   ├── application
  │   └── domain
  ├── articleorganization
  │   ├── application
  │   └── domain
  ├── chatroom
  │   ├── application
  │   ├── domain
  │   ├── presentation
  │   └── query
  ├── common
  │   ├── aop
  │   ├── config
  │   └── exception
  ├── favorite
  │   ├── application
  │   ├── domain
  │   ├── presentation
  │   └── query
  ├── member
  │   ├── application
  │   └── presentation
  ├── memberOrganization
  │   ├── application
  │   ├── domain
  │   ├── exception
  │   └── presentation
  ├── organization
  │   ├── application
  │   ├── domain
  │   ├── exception
  │   ├── presentation
  │   └── query
  ├── security
  │   ├── config
  │   ├── core
  │   ├── filter
  │   ├── handler
  │   ├── oauth2
  │   │   ├── authentication
  │   │   ├── provider
  │   │   └── service
  │   └── web
  └── trade
      ├── application
      ├── domain
      └── presentation
```
```gherkin
chat
  ├── config
  ├── message
  │   ├── application
  │   ├── domain
  │   └── presentation
  └── wholeMessage
      ├── application
      ├── domain
      └── presentation
```

# Level 3
  * [도메인 설계](#도메인-설계)
  * [기술스택을 선택한 이유](#기술스택을-선택한-이유)
  * [Spring Securtiy](#spring-securtiy)
  * [HTTPS](#https)
  * [Oauth2](#oauth2)
  
    
## 도메인 설계
![Lv3도메인](images/Lv3_domain.png) 

## 기술스택을 선택한 이유

🤵[기술스택을 선택한 이유](TroubleShoot.md)

## Spring Securtiy
🔒[Spring Security란?](security/Security.md)

🔑[Spring Security Architectures](security/SecurityArchitectures.md)

## HTTPS

🔒[HTTPS](security/https.md)

## OAuth2

🔒[OAuth2](security/OAuth.md)

# Level 4
 * [도메인](#도메인)
    + [추가된 도메인](#추가된-도메인)
 * [무중단 배포](#무중단배포)
## 도메인
![Lv4도메인](images/Lv4_domain.png)
### 추가된 도메인
![Lv4도메인](images/Lv4_additional_domain.png)

## 무중단 배포
- [무중단 배포](deploy/deploy.md)

### 변경해볼 사항 
멀티모듈로 인한 인증인가 문제 
