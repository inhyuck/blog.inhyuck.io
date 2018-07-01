---
title: "Kotlin Korea Meetup 2018"
date: 2018-06-26T09:04:54+09:00
lastmod: 2018-06-26T09:04:54+09:00
# draft: true
keywords: []
description: "Kotlin Korea Meetup 2018 참석후기"
tags: ["seminar", "kotlin"]
categories: ["Seminar"]
author: "inhyuck"

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: true
toc: true
autoCollapseToc: false
postMetaInFooter: false
hiddenFromHomePage: false
# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
contentCopyright: false
reward: false
mathjax: false
mathjaxEnableSingleDollar: false
mathjaxEnableAutoNumber: false

# You unlisted posts you might want not want the header or footer to show
hideHeaderAndFooter: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

<!--more-->

## Kotlin Korea Meetup 2018

### 2018-06-26(화)  9:00 ~ 12:00 AM, 디캠프 6F

[`Meetup 행사정보`](https://www.meetup.com/ko-KR/kotlinkr/events/251399066/comments/492399550/?read=1&_xtd=gatlbWFpbF9jbGlja9oAJDAyOWJkYWUyLTdiZTktNGI3Zi05MDVkLTU4MmI3ZGRiNmJjZg&_af=event&_af_eid=251399066&itemTypeToken=COMMENT&https=on)

![http](../../../images/seminar/img_kotlin_Korea_meetup_2018_1.jpg)

![http](../../../images/seminar/img_kotlin_Korea_meetup_2018_2.jpg)

## 1. Kotlin을 사용한 함수 프로그래밍(Functional Programming with Kotlin)

연사 : [`JetBrains Hadi Hariri`](https://github.com/hhariri)

> 화면을 통해 간단한 코틀린 코드 함께 보면서 진행(라이브 코딩!) 다행히 동시통역을 해줘서 조금은 알아들을 수 있었다. 중간중간 농담(샌드위치)도 해줘서 즐겁게 강연을 들었다. 코틀린의 문법 중 주목할 만한 것들에 대해 설명했다.

- 단순히 멋있기때문에(~~충분한 이유지만~~) 함수 프로그래밍을 하는것이 아니다. 코드에서 디테일한 부분을 추출할  수 있고 업무에 좀 더 집중할 수 있다. 

- 코틀린 반환값 Unit과 Nothing

- Lambda function

  

- Exception 처리

- Error 라이브러리 / Kategory 라이브러리 - Kotlin은 k를 써야한다 XD

- Option / .map / .flatMap

- binding / bind()
- 함수형프로그램은 코드를 간결하고 가독성 좋게 작성할 수 있다.
- Curry : 싱글 파라미터가 있는 함수
- partially
- either
- inline function / noinline function / crossinline
- Anoynymustsfsd Vs, Lambda
- Recursion을 효과적으로 사용가능. 중복계산을 피하게끔 할 수 있다 =>  tailrec



## 2. Kotlin으로 Domain Specific Language 만들기(Creating DSL’s with Kotlin)

연사 : [`JetBrains Hadi Hariri`](https://github.com/hhariri)

- DDD :  Domian driven design 소프트웨어를 디자인 할 떄 특정 도메인을 채택해야 한다.
- [Github - KotlinTest](https://github.com/kotlintest/kotlintest)
- DSL Marker

---

## 3. 코틀린 맛 빌드스크립트

연사 : [`Riid CTO 허재위`](https://github.com/hhariri)

[발표자료 - 코틀린 맛 빌드스크립트](https://speakerdeck.com/importre/kotlin-flavored-buildscripts) | [Github - Kotlin-Flavored BuildScript](https://github.com/importre/kotlin-flavored-buildscripts)

- 코틀린으로 그래들 플러그인 만들기 => 왜?? 계속 길어지는 build.gradle

- Kotlin - 빌드스크립트/플러그인/안드로이드 일원화 + 강력한 정적 타입의 프로그래밍 언어 

- 두가지 방법

  1. buildSrc 프로젝트
  2. 독립적인 프로젝트

- 이미 커진 스크립트를 한번에 gradle.build.kts로 옮기기에는 힘들다 => 하나씩 옮겨서 build.gradle 최소화

- 작아진 buildSrc 프로젝트 생성해서 조금씩 이주하는것을 제안!

- 독립적인 프로젝트 - 이미 buildSrc가 있거나 / 멋진 플러그인을 구현 및 공유 & 배포

  

- [Riid 채용홍보 !!](http://riiid.co/kr/)

> - 코틀린을 배워보지 않았지만 scala와 함께 언젠가 기회되면 꼭 배우고 싶은 언어 1순위 입니다. 게다가 스프링 5.0버전부터 코틀린언어도 채택했기 때문에 더욱 관심을 갖고 있습니다. 
>
>   
>
> - 예전 자바지기님 강의에서도 코틀린으로 코딩하면 간결한 코드를 작성할 수 있음은 물론 기존 Java로만 코딩했을 때와 또다른 생각의 전환을 할 수 있다 하셨습니다. 확실히 언어마다 특성이 있고 동일한 내용의 프로그램을 작성하더라도 각 언어마다 사고하는 방식이 달라지는 것 같습니다.
>
>   
>
> - 이번 행사를 들으면서 kotlin을 알고있었다면 훨씬 더 유익하고 재밌었을 것 같습니다. 코틀린의 아버지라 불리는 Hadi Hariri 님에게 강연을 듣는 기회는 앞으로도 흔치 않을 것 같아 더 아쉽습니다. 하지만 코틀린을 잘 모른다 하더라도 소개해준 문법중에 신기한 것들도 많았습니다. 확실히 간결한 코딩을 할 수 있고 그래서 더욱 더 배워보고 싶기도 합니다. 두번째 세션에서 Riid 허재위님이 소개해주신 코틀린으로 build.gradle 작성하기는 현재 진행중인 Spring 프로젝트에 적용해보려 합니다. 
>
> - 코틀린 언어를 몰라 이해하기 쉽지는 않았던 세미나였지만 코틀린이 왜 각광받는지 느낄 수 있었습니다. 얼른 Java를 좀 더 깊이 공부한 후 그다음으로는 1순위로 코틀린을 배워보고 싶어졌습니다. :D
>
> 