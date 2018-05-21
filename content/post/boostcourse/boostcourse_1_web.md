---
title: "[Boostcourse] 1.웹프로그래밍 기초"
date: 2018-05-18T03:09:04+09:00
lastmod: 2018-05-18T03:09:04+09:00
# draft: true
keywords: []
description: ""
tags: ["Boostcourse", "Full-Stack Developer", "web", "http", "front-end", "back-end", "brower", "middleware", "WAS", "Web Server"]
categories: ["Boostcourse"]
author: ""

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: false
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
## 부스트코스  Full-Stack Web Developer

### Web 개발의 이해 - FB/BE

---

### 1) 웹 프로그래밍을 위한 언어들

>  저급언어(기계어, 어셈블리어) / 고급언어
>
> 웹 관련 인기있는 언어 - Python, PHP, JavaScript, JAVA, Ruby

---

### 2) 웹의 동작(HTTP 프로토콜 이해)

- 인터넷 - TCP/IP 기반의 네트워크가 전세계적으로 확대되어 하나로 연결된 네트워크들의 네트워크(네트워크의 결합체)

- HTTP는 서버와 클라이언트가 인터넷상에서 데이터를 주고 받기 위한 프로토콜(protocol)이다.

- HTTP 작동방식 - 서버/클라이언트 모델을 따른다.

  클라이언트와 서버가 계속 연결된 형태가 아니기 때문에 클라이언트와 서버 간의 최대 연결 수보다 많은 요청과 응답 처리가능. 연결을 끊어버리기 때문에 클라이언트의 이전 상황을 알 수 없다(무상태성 Stateless) => 쿠키등장

  > URL(Uniform Resource Locator)
  >
  > 인터넷 상의 자원의 위치. 특정 웹 서버의 특정 파일에 접근하기 위한 경로 혹은 주소

  ![http](../../../images/boostcourse/http.png)

  > 요청헤더에 포함되는 정보
  >
  > 요청메소드 / 요청URI(요청하는 자원의 위치) / HTTP 프로토콜 버전

  요청메소드

  - GET : 정보를 요청하기 위해서 사용한다. (SELECT)
  - POST : 정보를 밀어넣기 위해서 사용한다. (INSERT)
  - PUT : 정보를 업데이트하기 위해서 사용한다. (UPDATE)
  - DELETE : 정보를 삭제하기 위해서 사용한다. (DELETE)
  - HEAD : (HTTP)헤더 정보만 요청한다. 해당 자원이 존재하는지 혹은 서버에 문제가 없는지를 확인하기 위해서 사용한다.
  - OPTIONS : 웹서버가 지원하는 메서드의 종류를 요청한다.
  - TRACE : 클라이언트의 요청을 그대로 반환한다. 예컨데 echo 서비스로 서버 상태를 확인하기 위한 목적으로 주로 사용한다.

- HTTPS란 ? - HyperText Transfer Protocol over Secure Sockets Layer. HTTP의 보안이 강화된 버전. HTTPS는 소켓 통신에서 일반 텍스트를 이용하는 대신에, SSL 이나 TLS프로토콜을 통해 세션 데이터를 암호호화 한다. HTTPS의 기본 TCP/IP포트는 443이다_[위키](https://ko.wikipedia.org/wiki/HTTPS)

---

### 3) 웹 Front-End 와 Back-End

- 웹프론트엔드란? 사용자에게 웹을 통해 다양한 콘텐츠(문서, 사진, 동영상 등)를 제공.

  사용자의 요청에 반응해서 동작.

- 웹 프론트엔드의 역할

  - 웹콘텐츠를 잘 보여주기 위해 구조를 만들어야 함

    **HTML** | 문서의구조를 계층적으로 표현

  - 적절한 배치와 일관된 디자인 제공

    **CSS** | HTML태그를 꾸미기 위한 규칙

  - 사용자의 요청을 잘 반영

    **JavaScript** | HTML, CSS를 이리저리 움직이고 변경

    

- 백 엔드란? 정보를 처리하고 저장하며, 요청에 따라 정보를 내려주는 역할을 한다. 

- 백엔드 개발자가 알아야 할 것들

  - 프로그래밍 언어
  - 웹의 동작원리
  - 알고리즘, 자료구조, 등 프로그래밍 기반지식
  - 운영체제, 네트워크 등에 대한 이해
  - 프레임워크에 대한 이해
  - DBMS에 대한 이해와 사용방법

---

### 4) browser의 동작

- 브라우저는 월드와이드웹(WWW)에서 정보를 검색, 표현하고 탐색하기 위한 소프트웨어이다.

- Browser에는 데이터를 해석해주는 **파서** 와 데이터를 화면에 표현해주는 **랜더링엔진** 이 포함되어 있다.

- 인터넷에서 특정 정보로 이동할 수 있는 주소 입력창. / 서버와 HTTP로 정보를 주고 받을 수 있는 네트워크 모듈.

- 서버에서 받은 문서(HTML, CSS, JavaScript)를 해석하고 실행하여 화면에 표현하기 위한 Parser.

- **브라우저 구조**

  ![http](../../../images/boostcourse/layers.png)

  

- **동작과정**

  ![http](../../../images/boostcourse/webkitflow.png)

=> HTML을 해석해서 DOM Tree를 만들고, CSS를 해석해서 CSS Tree(CSS Object Model)을 만든다

이 과정에서 Parsing 과정이 필요하다 DOM Tree 와 CSS Tree는 연관되어 있으므로 Render Tree로 조합된다.

조합된 결과는 화면에 어떻게 배치할 지 크기와 위치정보를 담고있다. 이렇게 구성된 Render Tree정보를 통해서 화면에 어떤 부분에 어떻게 색칠을 할 지 Painting과정을 거치게 된다.

- [[참고링크] How Browsers Work: Behind the scenes of modern web browsers](https://d2.naver.com/helloworld/59361)
- [[참고링크] 브라우저는 어떻게 동작하는가?](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/#Introduction)

---

### 5) browser에서의 웹 개발

- head 태그 : 눈에 보이는것이 아닌 HTML문서의 추가적인 정보.
- body 태그 : 실제 눈에 보이는것들. 
- HTML은 계층적이다.
- HTML은 Tag를 사용해서 표현한다.
- 자바스크립트 코드가 html Tag 사이에 들어가면 랜더링에 방해가 될 수 있다. 따라서 가급적 문서 하단에 추가해주는것이 좋다.(/body 태그 바로 앞이나 뒤)
- css코드는 head 태그 안에 위치해서 렌더링 처리 시에 브라우저가 더 빨리 참고할 수 있게 하는 것이 좋다.
- [[참고링크] 웹에서 html, css, javaScript 실행 가능한 사이트](http://jsbin.com/?html,output)

---

### 6) 웹서버

- 웹 서버는 소프트웨어를 보통 말하지만, 웹 서버 소프트웨어가 동작하는 컴퓨터(하드웨어)를 의미하기도 한다.
- 웹 서버의 가장 중요한 기능은 클라이언트가 요청하는 HTML 문서나 각종 리소스를 전달하는 것이다.
- 웹 브라우저나 웹 크롤러가 요청하는 리소스는 컴퓨터에 저장된 정적(static)인 데이터이거나 동적인 결과가 될 수 있다.
- Apache웹 서버는 Apache Software Foundation에서 개발한 웹서버로 오픈소스 소프트웨어(Open-source Software)이며, 대부분 운영체제에서 설치 및 사용을 할 수 있다. (부동의 1위)
- Nginx는 차세대 웹서버로 불리며 더 적은 자원으로 더 빠르게 데이터를 서비스하는 것을 목적으로 만들어진 서버이며 Apache웹 서버와 마찬가지로 오픈소스 소프트웨어입니다. (가파른 성장세)

---

### 7) WAS(Web Application Server)

- 클라이언트/서버 구조 : 클라이언트는 서비스를 제공하는 서버에게 정보를 요청하여 응답 받은 결과를 사용.

- DBMS(DataBase Management System) : 다수의 사용자가 데이터베이스 내의 데이터에 접근할 수 있도록 해주는 소프트웨어.

- 미들웨어(MiddleWare) ![http](../../../images/boostcourse/middleware.png)

  : 클라이언트가 바로 DBMS로 접근하여 서비스하게 되면, 클라이언트 쪽에 비즈니스 로직이 많아질수밖에 없다. 이 경우 클라이언트 관리(배포, 보안문제)로 인해 비용이 많이 발생한다. 따라서 비즈니스 로직을 클라이언트와 DBMS사이의 **미들웨어 서버**에서 동작하도록 함으로써 클라이언트는 입력과 출력만 담당하도록 한다.

  

- WAS(Web Application Server)![http](../../../images/boostcourse/was.png)

   : 일종의 미들웨어로 웹 클라이언트(보통 웹브라우저)의 요청 중 웹 애플리케이션이 동작하도록 지원하는 목적을 가진다.

  - > WAS의 주요 기능
    >
    > 1. 프로그램 실행환경과 데이터베이스 접속기능을 제공한다. 
    > 2. 여러개의 트랜잭션(논리적인 작업단위)을 관리한다.
    > 3. 업무를 처리하는 비즈니스 로직을 수행한다.

- 웹 서버 vs WAS

  - WAS도 자체적으로 웹 서버의 기능을 내장하고 있다.(정적인 콘텐츠를 처리하는 데 있어서 성능상 큰 차이가 없다)

  - 대표적인 WAS Tomcat : Tomcat에 내장된 웹서버가 충분한 기능을 하고 있기 때문에 따로 Apache같은 웹서버를 설치하지 않고 Tomcat만 설치해도 서비스 가능하다.

  - > 규모가 커질수록 웹 서버와 WAS를 분리한다.
    >
    > - 자원 이용의 효율성 및 장애극복(failover), 배포 및 유지보수의 편의성
    > - 보통 웹서버가 WAS 앞단에서 동작하도록 하는 경우가 많다.

---
"기존에 두루뭉술하게 알고있던 개념을 하나씩 차근차근 배울 수 있어서 좋았습니다. 특히 HTTP와 브라우저의 동작원리, 웹서버와 WAS의 헷갈렸던 개념을 명확히 알 수 있었습니다. 학기중이라 보통 집에 돌아와 새벽시간에 많이 수강했는데 몸은 힘들지만 무언가 제대로 배우고 있다는 느낌이 들어 마음은 편했습니다. 앞으로도 쉽지는 않겠지만 포기하지 않고 꾸준히 수강하려 합니다. :D"

---

출처 : [부스트코스 Full-StackWeb Developer 과정](http://www.edwith.org/boostcourse-web/lecture/16666/)