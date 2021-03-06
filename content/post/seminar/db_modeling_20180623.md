---
title: "SW 개발자/기획자도 알면 좋은 DB 모델링"
date: 2018-06-23
# draft: true
description: ""
tags: ["seminar", "database", "modeling"]
---

<!--more-->

# [리얼타임 EDU 03]SW 개발자/기획자도 알면 좋은 DB 모델링

### 2018-06-23(SAT) 1:00 ~ 06:00 PM

강사 [용영환](https://www.rocketpunch.com/@xenonix) (xenoniy@gmail.com)

| PHPKOREA. <개발자, 나를 말하다> 저자. 전 서울옥션블루 CTO / Web개발, Java, PHP

`정답이 아닙니다. 취업이나 승진을 보장하지 않습니다.`

### ERD를 그리면...

- 프로젝트를 쉽게 설명할 수 있다.
- 본인의 성과를 고급스럽게 티낼 수 있다.
- 세부적인 데이터를 안보더라도 ERD만 보고 그 구조를 쉽게 이해할 수 있다.

소프트웨어를 해부하면 크게 **동작**과 **데이터**로 나눌 수 있다. (프로그래밍 언어는 **데이터**를 제어하는 **수단**일 뿐이다)

`모델링` 사전적 의미. 모델을 보고 닮게 만드는 일 

`DB 모델링` 이해하고자 하는 소프트웨어에 대해서 머릿속에서 끄집어 내서 표현해낸 것

---

우리가 할 `모델링`은 만들고자 하는 머릿속 생각을 누구나 볼 수 있게 본을 뜨는 것. 객체나 데이터베이스를 그림으로 표현하는 것입니다.

`ERD`(개체 관계 다이어그램) : 데이터 간의 관계를 그림으로 표현한 것.

> 모델링을 하면 좋은점
>
> - 만들고자 하는 것을 명확히 이해
> - SW를 조금 더 잘 만들 수 있다.
> - 이해하고 소통하기 편하다.
> - 더불어 좋은 점 - 면접 볼 떄 좋다 / 뽐내기 좋다 / **만들고 나면 뿌듯하다!!**
> - **전체**를 볼 수 있다.

개발을 하다 보면 정말 실무에서 많이 씁니다 :)

## 기초적인 개념

### 논리모델과 물리모델

- 논리모델 : 개념적으로 모델링
- 물리모델 : 실제 DB 컬럼형태로 모델링

### ERD 표기법 : IE 표기법

### RDBMS 무결성 : RDBMS는 데이터 무결성(Data Integrity) 을 준수한다.

- 개체 무결성 : PK는 고유한 값이어야 한다.
- 참조 무결성 : 모든 외부식별자(FK) 값은 연관된 주식별자 값을 참조한다.
- 범위 무결성 : 정의된 범위 안에서 모든 열의 값이 보장되어야 한다. 예) integer, varchar, not null 등
- Identifying Relationship : 식별관계
- 실선 : 식별관계 - 부모 테이블의 PK가 자식테이블의 FK/PK가 되는 경우
- 점선 : 비식별관계 - 부모 테이블의 PK가 자식테이블의 일반속성이 되는 경우
- Mandatory : 필수 <-> Optional : 선택적
- Cascade : 폭포. 폭포처럼 떨어뜨리다. => 연쇄

FK Options | RESTRICT / CASCADE / SET NULL / NO ACTION : RESTRICT와 동일

**정규화** : 관계형 데이터베이스와 설계에서 중복을 최소화하게 데이터를 구조화하는 프로세스를 정규화하라 한다.



---

### MySQL Workbench 실습

**User Flow** : 테이블 만드는 순서는 실제 서비스 이용자의 흐름순으로 만드는 것이 좋다.(예: 유저는 회원가입을 한 다음 글을 쓰므로 users 테이블 먼저 만들고 posts테이블을 만든다.)

실습 : 트위터구조 ERD 그리기(점점 발전해서 쇼핑몰까지!)

- 일반적으로 테이블명은 복수로 쓴다.
- 외국에서는 ID 대신 username을 쓴다.
- password 라는 함수가 mySQL에 있다. 따라서 관행적으로 passwd 요렇게 쓰기도 한다.
- 실제 사람 이름은 realname이라고 말한다.

> DB 설계를 할 때 당장 완벽할 수는 없다. 초기에는 기본적인 기능이 될 수 있다고 생각하면 마무리 하자. 그 이후 개발하다 추가로 필요하면 그때 추가하면 된다!

- 설계는 계속해서 바꾼다. 실무에서도 계속해서 바뀐다.
- 설계하면서 계속 검증하는 과정을 거쳐야한다.
- 개발자도 기획의도, 서비스 방향을 잘 이해해야 한다.
- 전체 복잡도를 보는 눈은 계속해서 많이 봐야 늘어난다.
- 의존관계를 일부러 끊어줘야 할 때도 있다. 예를 들면 장바구니의 상품 데이터와 최종 주문의 상품데이터는 중복된다고 볼 수도 있지만 각각 다른 역할을 할 수도 있고 의존하고 있는 상품데이터가 변경된다고 주문된 상품데이터가 변경되서는 안되는 경우.
- 성능 향상 or 개발편의상 을 위해 데이터를 일부러 **중복화**. 이것이 역정규화!!!!!
- 디비 설계는 정규화와 역정규화를 계속 반복해서 맞춰나가는 것이다.
- 새로운 서비스를 접할때 ERD로 변환 후 전체 구조를 먼저 파악하는 것이 좋다
- FK가  다중키로서 PK역할을 같이해줄때도 있고 혹은 PK역할은 안하고 단순히 연결된 데이터를 의미할수도 있다.
- PK를 꼭 id로 해야하는 것은 아니다. 경우에 따라 다중키로  PK를 만들어 주는 것이 적합할 수 있다.(구조를 설계하고 검증을 하며 확인하는것이 중요!

![http](../../../images/seminar/img_db_modeling_20180623.png)

`정규화와 역정규화`

 정규화를 많이하면 데이터의 명확성은 좋아지지만 조인을 많이하고 쿼리수가 늘어나며 성능이 떨어진다. 옛날 책들이 만들어 지던 당시에는 트래픽이 높지 않았기 때문에 정규화를 되도록 많이 하라고 추천하지만 요즘같이 트래픽이 많아서 성능을 고려해야하는 이슈가 강할때는 마냥 정규화를 많이 한다고 좋은 것이 아니다 => 역정규화가 필요한 경우도 많다

=> 서비스 규모가 큰 회사에 가면 역정규화를 사용해야 하는 이유를 알게되고 경험을쌓을 수 있다. 첫 회사는 큰회사를 가는것이 좋다. 다루는 데이터 양에따라 개발실력 향상의 폭이 달라진다. ORM은 역정규화 개념이 없다. 서비스 규모가 커지면 ORM 쓰기가 힘들다. DBMS를 튜닝해줘야 하기 때문이다. 작은 규모의 회사가 빠른 시작을 위해 ORM을 사용한다. ORM에 한번 종속되면 벗어나기 힘들다.

설계를 잘하면 개발실력에도 도움이 많이 된다 DBMS의 동작원리를 이해하는 것도 중요하다.

들이는 시간만큼 성장한다. 집에 돌아가서 배송 프로세스를 추가해서 ERD그려볼 것.

> 생활코딩에 공유된 내용을 보고 며칠간 고민하다 신청을 했습니다. 평소에 프로젝트를 시작할때 DB 설계를 앞부분에 하게되는데 어떻게 해야할지 막막해야 했습니다. `용영환` 강사님은 실제 mySQL Workbench를 통해 ERD를 그려가며 현실적으로 부딪치는 애매한 부분들을 같이 검증하며 해결해나가는 식으로 가르쳐 주셨습니다. 강의 시작부터 웃음도 많고 유쾌하시며 자유로운 분위기 속에서 배울 수 있었습니다. 해당 강의를 듣는다고 해서 바로 DB설계를 한방에 딱! 할 수 있는건 아니지만 어떤식으로 접근해야할 지 감을 잡을 수 있었던 강의였습니다. 당장 현재 하고 있는 프로젝트에 얼른 적용해보고 싶네요. 마지막에는 서비스 규모가 큰 회사로 가야하는 이유를 설명해주시면서 멘토같은 느낌도 들었습니다. 여러모로 많은 것을 알려주신 `용영환` 강사님께 감사드립니다. :)



