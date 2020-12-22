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
## 패키지 구조
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
  * [첫번째 클레스 다이어그램](#첫번째-클레스-다이어그램)
  * [프로젝트에서 맡은 주된 업무](#프로젝트에서-맡은-주된-업무)
    + [Front](#front)
    + [Back](#back)
  * [Spring Securtiy](#spring-securtiy)
  * [HTTPS](#https)
  * [Oauth2](#oauth2)
  * [왜 이 기술스택을 사용했나?](#왜-이-기술스택을-사용했나?)
  
## 도메인 설계
도메인 설계 할 때 도메인을 관심사 별로 묶고 **모듈 간의 의존성은 최소화하고, 응집성은 최대화** 할 수 있는 Layered Architecture 따라 설계를 하였습니다.

- DDD의 핵심 목표 중 하나인 "Loosely coupling" 은 복잡한 연관 관계가 적용되면 연관된 객체에 대해 변경의 일관성을 유지하기 힘듭니다. 따라서 객체 참조보다
Id 참조를 함으로써 연관 관계를 없애 일관성을 더 쉽게 유지고할 수 있다. 하지만 JPA를 학습하고 적용해보고 싶어 Spring data JDBC 와 Spring data JPA 중 JPA를 선택했습니다.

- 참고
    - [Domain-Driven Design and MVC Architectures](https://blog.fedecarg.com/2009/03/11/domain-driven-design-and-mvc-architectures/)
    - [카카오헤어샵의 DDD](https://brunch.co.kr/@cg4jins/7) 
    - [DDD 핵심만 빠르게](https://happycloud-lee.tistory.com/94)
    - [DDD, Aggregate](https://medium.com/@chanhyeonglee/ddd-aggregate-애그리거트-98d9c1313c23)
    - [애그리게잇 하나에 리파지토리 하나](https://medium.com/@SlackBeck/애그리게잇-하나에-리파지토리-하나-f97a69662f63)
    
## 첫번째 클레스 다이어그램
![Lv3도메인](images/Lv3_domain.png) 

## 프로젝트에서 맡은 주된 업무
### Front
- React Native, Expo, TypeScript, Recoil, Axios
    - 프론트는 팀원 모두 학습하며 진행해야 했기 때문에 이슈를 골고루 가져갔습니다.
### Back
- Spring Securtiy, Nginx, Https

프로젝트에서 혼자서 맡게 된 기술들입니다. 새로운 기술을 적용하면서 공부했던 방법과 내용, 고민들을 공유하겠습니다.

## Spring Securtiy
🔒[Spring Security란?](security/Security.md)

🔑[Spring Security Architectures](security/SecurityArchitectures.md)

## HTTPS

🔒[HTTPS](security/https.md)

## OAuth2

🔒[OAuth2](security/OAuth.md)

## 왜 이 기술스택을 사용했나?

🤵[왜 이 기술스택을 사용했나?](TroubleShoot.md)

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
