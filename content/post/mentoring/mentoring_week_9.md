---
title: "한솥밥튜터링 | 알고리즘 Week 9"
date: 2018-06-05T00:01:10+09:00
lastmod: 2018-06-05T00:01:10+09:00
# draft: true
keywords: []
description: ""
tags: ["Algorithm", "mentoring", "Dynamic Programming"]
categories: ["mentoring"]
author: ""

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

### Date 2018.06.05. | Time 13:00 - 15:00 | Place SKHU. 3501

## 🏫 스터디 전 공지

- 보충주간 9주차 | 수고 많았어 튜티들!! XD



## 📖 스터디

# Dynamic Programming (동적 계획법)

## 1. 동적 계획법은 무엇?

- 재귀적 문제 : 큰 문제의 해답에 작은 문제의 해답이 포함되어 있는 문제

- [동적 계획법](https://namu.wiki/w/%EB%8F%99%EC%A0%81%20%EA%B3%84%ED%9A%8D%EB%B2%95) : 재귀적 문제를 재귀호출로 구현하면, 지나치게 재귀호출의 중복이 많이 발생하는 경우가 있다. 이 재귀호출의 중복을 해결하는 방법이 동적 프로그래밍이다. "어떤 문제를 풀기위해 그 문제를 더 작은 문제의 연장선으로 생각하고, 과거에 구한 해를 활용하는" 방식의 알고리즘을 총칭한다.

- 여기서 Dynamic은 우리가 생각하는 컴퓨터 프로그래밍 용어에서의 dynamic(컴퓨터의 실행 시간동안과 관련된)과 **전혀** 상관이 없다.

- [Memoization(메모이제이션)](https://namu.wiki/w/%EB%A9%94%EB%AA%A8%EC%9D%B4%EC%A0%9C%EC%9D%B4%EC%85%98) : 동일한 계산을 반복해야 할 경우 한 번 계산한 결과를 메모리에 저장해 두었다가 꺼내 씀으로서 중복 계산을 방지할 수 있게하는 기법. 동적 프로그래밍의 핵심이 되는 기술로서 결국 메모리라는 공간 비용을 투입해 계산에 소요되는 시간 비용을 줄이는 방식이다.

## 2. 동적프로그래밍은 어떤 문제에 적용하나? 

- 부분 문제 반복과 최적 부분 구조를 가지고 있는 알고리즘을 더욱 적은 시간 내에 풀 때 사용한다.

- 동적 계획법은 최단 경로 문제, 행렬의 제곱 문제 등의 최적화에 사용된다. 동적 계획법은 문제를 해결하기 위한 모든 방법을 검토하고, 그 중에 최적의 풀이법을 찾아내기 때문이다.

- [그리디 알고리즘](https://ko.wikipedia.org/wiki/%ED%83%90%EC%9A%95_%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98)과의 비교 : 그리디 알고리즘은 항상 최적해를 구해주지는 않지만, Minimum Spanning Tree 등의 여러 문제에서 최적해를 구할 수 있음이 입증되었다. 동적 계획법은 모든 상황의 경우의 수를 감안하여 최적해를 찾아내는 반면, 그리디 알고리즘은 전체 상황을 고려하지 않고 순간순간의 상황에서 가장 최적의 답을 찾아낸다. 동적 계획법을 통해 찾아낸 답이 최적해라고 장담할 수 있지만, 그리디 알고리즘은 항상 최적해를 찾아주지는 않는다. 즉 동적 계획법은 그리디 알고리즘에 비해 시간적으로 효율적이지 못할 수는 있어도, 그 결과에 대해서는 효율적인 값을 구할 수 있다.


## 3. 동적 프로그래밍으로 해결할 수 있는 문제들

- 피보나치수 구하기
- 행렬 경로 문제
- 조약돌 놓기 문제
- 행렬곱셈 순서문제
 

## 👩🏼‍💻 과제

> 🐥 이승진교수님 강의자료 문제 구현 코드 **분석**


------

참고자료
성공회대학교 소프트웨어공학과 이승진교수님 강의자료 - 동적 프로그래밍
위키 : 동적계획법, 메모이제이션, 탐욕 알고리즘(그리디 알고리즘)
