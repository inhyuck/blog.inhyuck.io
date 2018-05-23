---
title: "한솥밥튜터링 | 알고리즘 Week 7"
date: 2018-05-24T00:16:49+09:00
lastmod: 2018-05-24T00:16:49+09:00
# draft: true
keywords: []
description: ""
tags: ["Algorithm", "mentoring", "hash", "hashTable"]
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

### Date 2018.05.24. | Time 18:00 - 20:30 | Place 1407

## 🏫 스터디 전 공지

- 지난시간 과제 - B Tree 삽입/삭제 각자 만든 문제 및 풀이 공유 | [드라이브](https://drive.google.com/drive/folders/1BLVcXCUVuzPN-hzWrGVYUg-nU6OsoeLP?usp=sharing)

  


## 📖 스터디

# Hash Table

## 1. Why Hash Table?

1. 저장/검색의 복잡도
2. What? : 원소가 저장될 자리가 원소의 값에 의해 결정되는 자료구조. 저장할 원소의 값으로 저장할 위치를 계산할 수 있다.
3. 평균 상수 시간에 삽입/삭제/검색 가능

## 2. Hash Table 구현

- 충돌 : 저장을 시도하려는 위치에 이미 다른 값이 저장되 있는 경우를 **충돌**이라 한다.

1. 저장할 위치 계산 방법

   1. Division Method : 저장할 값을 배열의 크기로 나눈 나머지를 저장할 위치로 배정
      - 배열의 크기가 소수(primary number) 이어야 저장할 위치가 골고루 분포됨
   2. Multiplication : 상수값 A를 정하고 저장할 값에 곱한다. 이 결과에서 소수점 아래자리만 꺼내고 배열의 크기를 곱한다. 마지막으로 소수점 아래자리를 버린값을 저장할 위치로 배정
      - 배열의 크기는 마음대로 정할 수 있다. 보통 2의 배수 크기로 정함

2. 충돌을 해결하는 방법

   1. Chaining : 저장할 리스트를 Linked List에 등록

   2. Open Addressing : 그 다음칸에 저장을 시도

      1. Linear probing 

         - 다음칸을 계산할 때 처음 저장할 위치에서 1, 2, 3, 4, … 뒤 칸을 순서대로 시도하는 방법이다.

         - 충돌이 발생한 경우, 최종 저장할 위치의 근처에 저장하게 됨 => 1차 군집 문제 발생(데이터가 몰려 있는 곳에서 충돌 발생 확률이 높고 충돌이 발생한 근처에 데이터가 쌓이게 된다)

      2. Quadratic probing

         - 다음칸을 계산할 때 처음 저장할 위치에서 1의 제곱, 2의 제곱, 3의 제곱, ... 뒤 칸을 순서대로 시도하는 방법이다.
         - Linear probing 방법보다는 조금 덜하지만, 2차 군집 문제 발생 => 충돌이 발생했을 때 건너 뛰는 폭이 매번 다른 것이 좋다 

      3. Double hashing

         - 저장할 값에 따라 건너뛰는 폭을 다르게 계산

3. 해시 테이블의 크기가 소수여야 하는 이유

   - 배열의 크기와 충돌시 건너뛸 간격이 서로소가 아니라면 계속해서 충돌시 동일한 위치를 계속해서 시도하게 된다. 따라서 배열의 크기를 소수로 정하고 건너뛸 간격을 배열의 크기보다 작게 만들면 모든 칸을 방문할 수 있다.

   - 해시테이블의 크기가 소수가 아니라면 건너뛸 간격이 소수여야 한다. 건너뛸 간격을 소수로 만드는 방법은 아래처럼 일대일 대응으로 건너뛸 간격을 소수에 대응시켜 주면 된다.

     ```java
     private static int getStepDistance(int value) {
         int r = 0;
         
         switch (value % 7) {
             case 0: r = 3; break;
             case 1: r = 5; break;
             case 2: r = 7; break;
             case 3: r = 11; break;
             case 4: r = 13; break;
             case 5: r = 17; break;
             case 6: r = 19; break;
         }
         return r;
     }
     ```

   

4. 해시 테이블의 크기 자동 증가 구현

   - 해시 테이블에 저장된 데이터가 어느 정도 수준을 넘으면, 충돌이 자주 발생하여 성능히 급격히 떨어진다.
   - Load factor = 저장된 값의 수 / 해시 테이블의 크기
   - 해시 테이블의 load factor 값이 미리 정한 기준(threshold)을 넘으면, 두 배 크기의 해시 테이블을 새로 만들고, 기존의 데이터를 전부 새 해시 테이블에 저장한다.
   - 해시 테이블의 크기를 두배로 확장하면 해시 테이블의 크기가 소수일 수 없다. 이때는 건너뛸 간격을 소수로 만드는 방법을 사용한다.

5. 기본자료형이 아닌 객체의 해시 테이블

   - java에서 모든 클래스의 부모인 Object의 클래스에 hashCode 메소드가 있다. 이 메소드는 해시 테이블에 저장할 주소를 계산할 때 필요한 정수를 리턴한다.

   - Java 클래스를 구현할 때, equals 메소드와 hashCode 메소드를 재정의 하는 것이 바람직하다. => java 표준 라이브러리의 여러 유용한 기능 활용 가능

     ```java
     import java.util.Objects;
     
     @Override
     public int hashCode() {
         return Objects.hash(변수1, 변수2, ...)
     }
     ```

     

# Red-Black Tree | [remind](http://blog.inhyuck.io/post/mentoring/mentoring_week_5/)

# B Tree | [remind](http://blog.inhyuck.io/post/mentoring/mentoring_week_6/)

## 👩🏼‍💻 과제

> 🐥 hash Table 사례 연습 => [드라이브 공유](https://drive.google.com/drive/folders/1Uim1ykanC5_U3iuRji1NhzASux6VR9dp?usp=sharing)
>
> 1. Open Addressing - Linear Probing
>    - 저장할 위치 : division method
>    - 배열의 크기 11
>    - 저장할 값 : [4, 9, 15, 2, 26, 20]
> 2. Open Addressing - Linear Probing
>    - 저장할 위치 : Multiplication (A = 0.6)
>    - 배열의 크기 11
>    - 저장할 값 : [4, 9, 15, 2, 26, 20]
> 3. Open Addressing - Quadratic Probing
>    - 저장할 위치 : division method
>    - 배열의 크기 17
>    - 저장할 값: [3, 7, 16, 20, 1, 24, 21, 17]
> 4. Open Addressing  - Double Hashing
>    - 저장할 위치 : division method
>    - 배열의 크기 17
>    - 건너뛸 간격 : (value % 7 + 1)
>    - 저장할 값: [3, 7, 16, 20, 1, 24, 21, 17]
> 5. **시험 공부📚**



---

참고자료 : 성공회대학교 소프트웨어공학과 이승진교수님 강의자료 - Hash Table