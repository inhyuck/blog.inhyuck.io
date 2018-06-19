---
title: "한솥밥튜터링 | 알고리즘 Week 10"
date: 2018-06-19T10:32:49+09:00
lastmod: 2018-06-19T10:32:49+09:00
# draft: true
keywords: []
description: ""
tags: ["Algorithm", "mentoring", "Graph", "DFS", "BFS"]
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

### Date 2018.06.19. | Time 13:00 - 15:00 | Place SKHU. 1503

## 🏫 스터디 전 공지

- 마지막 튜터링 10주차 | 그동안 고생했어 😭



## 📖 스터디

# Graph | BFS, DFS

## 1. 그래프란 무엇?

- [그래프 관련 용어 참고 블로그](https://ratsgo.github.io/data%20structure&algorithm/2017/11/18/graph/)
- [그래프(Graph)](https://ko.wikipedia.org/wiki/%EA%B7%B8%EB%9E%98%ED%94%84) | 그래프란 일련의 정점(vertex, 노드 node) 집합 V와 간선(edge) 집합 E로 구성된 자료구조의 일종
- 정점에는 데이터가 담겨있고 간선은 정점과 점점사이의 관계를 나타낸다.
- 임의의 두 정점이 간선으로 연결되어 있을 경우, 두 정점들은 서로 인접(adjacent)하다고 한다.
- 유향 그래프 / 무향 그래프
- Graph? Tree? Forest? 


## 2. 그래프를 표현하는 방법(in Java) 

- 가중치 유무 / 방향성의 유무
- Adjacency Matrix | 2차원 배열로 구현
- Adjacency List | 링크드 리스트로 구현


## 3. 그래프의 탐색 방법

### BFS(Breadth-First-Search) 너비 우선 탐색 / 너비 우선트리

시작점으로부터 시작해서 가까운 순서로 방문한다.

* 반복문으로 `Queue` 를 이용하여 구현

### DFS(Depth-First-Search) 깊이 우선 탐색 / 깊이 우선트리

한쪽 경로로 갈 수 있을때까지 간 다음에 더 이상 못 가면 돌아오고 그 다음 경로를 시도하는 방식

* 재귀호출로 구현

* 반복문으로 `Stack` 을 이용하여 구현

  


## 👩🏼‍💻 과제

> 🐥 내일 알고리즘 시험 최선을 다해 준비하기!

------

참고자료
성공회대학교 소프트웨어공학과 이승진교수님 강의자료 - 그래프

[그래프 관련 용어 참고 블로그](https://ratsgo.github.io/data%20structure&algorithm/2017/11/18/graph/) - [ratsgo](https://ratsgo.github.io/)

[그래프 관련 위키백과](https://ko.wikipedia.org/wiki/%EA%B7%B8%EB%9E%98%ED%94%84)