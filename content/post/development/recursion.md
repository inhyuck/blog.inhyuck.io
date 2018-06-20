---
title: "재귀호출"
date: 2018-06-20T15:31:58+09:00
lastmod: 2018-06-20T15:31:58+09:00
# draft: true
keywords: []
description: ""
tags: ["Recursion", "Java"]
categories: ["Development"]
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

# 재귀호출 구현

- 종료조건이 반드시 존재해야 한다.
- 계산범위가 점점 줄어들어야 한다.

## 재귀호출의 3요소

> 1. 종료조건
> 2. 현단계에서의 작업
> 3. 재귀메소드 호출

## 재귀호출과 반복문

- 모든 재귀호출은 반복문으로 구현 가능하다 => 복잡한 경우에도 `Stack`을 이용하여 구현 가능!

### Factorial 과 Fibonaci 문제 재귀와 반복문 Java 구현

- Factorial By Recursion OR Loop

~~~java
public class Factorial {

	public static void main(String[] args) {
		System.out.println(factorialByRecursion(5));
		System.out.println(factorialByLoop(5));
	}
	static int factorialByRecursion(int n) {
		//종료조건: n 이 1일때
		if(n == 1) return 1;
		//현단계에서의 작업: n x factorial(n-1)
		//재귀호출 구현: factorial(n - 1)
		return n * factorialByRecursion(n - 1);
	}
	static int factorialByLoop(int n) {
		int num = 1;
		for(int i = 1; i < n + 1; ++i) {
			num = i * num;
		}
		return num;
	}
}
~~~



- Fibonacci By Recursion OR Loop

~~~java
public class Fibonacci {

	public static void main(String[] args) {
		System.out.println(fiboByRecursion(10));
		System.out.println(fiboByLoop(10));
	}
	static int fiboByRecursion(int n) {
		// 종료조건: 0 혹은 1일때
		if (n == 0) return 0;
		if (n == 1) return 1;
		// 현단계에서의 작업: 두개를 더하는것
		// 재귀호출 구현: fibo(n-1), fibo(n-2)
		return fiboByRecursion(n - 1) + fiboByRecursion(n - 2);
	}
	static int fiboByLoop(int n) {
		int num1 = 0, num2 = 1, num3 = 0;
		for (int i = 0; i < n + 1; ++i) {
			if (i == 0) num3 = 0;
			else if (i == 1) num3 = 1;
			else
				num3 = num1 + num2;
			num1 = num2;
			num2 = num3;
		}
		return num3;
	}
}
~~~



