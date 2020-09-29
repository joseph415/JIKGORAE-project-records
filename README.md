# 🐳 JIKGORAE-Project-records
#### 본 저장소의 목적은 [우아한테크코스 팀 프로젝트](https://github.com/woowacourse-teams) 를 진행하면서 했던 내용들을 정리하는 것입니다.  

## 직고래 
당신이 속한 그룹 어디든 당신이 원하는 것을 사고 파세요. 조직 중고 거래, 직고래 🐳

> 따뜻한 교류가 있는 조직 벼룩시장을 꿈꾸다

- [직고래 Github](https://github.com/woowacourse-teams/2020-seller-lee-company)
- [직고래 소개](https://sites.google.com/woowahan.com/wooteco-demo/직고래/)

## Level 3
### 도메인 설계
도메인 설계를 하는데 많은 시간을 들였다. 우리 팀이 도메인 설계를 하면서 고민을 했던 부분입니다.
- 스프링 data 쓰다보면 Aggregate 개념을 적용하게 된다. 그래서 변경단위에 대한 고민이 있었다.
- 단방향을 생긴 문제들 cascade 같은 문제들을 어떻게 해결할까 라는 문제들

첫 도메인 설계때 많은 희의를 하였습니다. 그 중 가장 분분했던 것은 mvc 패턴을 적용하자 vs DDD 패턴을 적용하자 입니다.
기술스택 스팩트럼을 다양하게 잡은 우리 팀은 DDD 패턴을 알고있는 크루가 많이 없기 때문에 걱정을 하였습니다.
하지만 어떤 요청에 대한 변경단위를 생각했을때 패키지 분리를 Mvc 패턴보다 DDD 패턴이 좀더 Aggregate 개념을 적용하기 쉬웠고
결국 Mvc 도 DDD 의 일종이다 라는 한 크루에 말을 듣고 DDD 패턴의 형식을 따르기로 헀습니다.

<img src="/images/api_package_tree1.png" alt="My Image" width="70%" height="70%">
<img src="/images/api_package_tree2.png" alt="My Image" width="70%" height="70%">

패키지 분리를 하나의 변경단위에 대해 나눴고 그로 인해 나온 첫 클레스 다이어그램은 다음과 같았습니다.
![Lv3도메인](images/Lv3_domain.png) 

### 전반적인 기술 스택 학습
#### Front
- React Native, Expo, TypeScript, Recoil, Axios 학습
#### Back
- LogBack, Nginx, Spring Securtiy, JPA 학습

## Level 4
### 도메인 추가
