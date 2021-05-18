---
layout: post
title: JDK 9 설치 후 이클립스 실행 오류
description: >
tags: [etc]
---

**오류 발생 케이스**

> JDK 9 와 이클립스 Neon 설치 한 후 JDK 7 버전의 프로젝트 작업 진행. 이클립스 재 실행 시 *An error has occurred. See the log file C:\workspace\.metadata\.log* 라고 팝업창 출력되고 실행되지 않음.

아래와 같이 javax.annotation 패키지가 클래스 패스에 존재하지 않는다는 에러 로그 확인 가능.

```java
!MESSAGE Application error !STACK 1 org.eclipse.e4.core.di.InjectionException: java.lang.NoClassDefFoundError: javax/annotation/PostConstruct at org.eclipse.e4.core.internal.di.InjectorImpl.internalMake(InjectorImpl.java:410) at org.eclipse.e4.core.internal.di.InjectorImpl.make(InjectorImpl.java:318) ... !MESSAGE FrameworkEvent ERROR !STACK 0 java.lang.NoClassDefFoundError: javax/annotation/PreDestroy at org.eclipse.e4.core.internal.di.InjectorImpl.disposed(InjectorImpl.java:450) at org.eclipse.e4.core.internal.di.Requestor.disposed(Requestor.java:156) ...
```
**오류 해결 1**
*C:\workspace\.metadata\.plugins\org.eclipse.core.resources* 하위 경로의 `.snap` 파일 삭제

**오류 해결 2**
eclipse.ini 파일 맨 위에다가 -clean 추가

**오류 해결 3**
eclipse.ini 파일의 -vmargs  아래에 **--add-modules=java.se.ee** 를 추가 후 실행. 웹 검색해보니 다양한 문제해결 방법이 있으나, 이번 케이스에서는 **오류 해결 3** 으로 문제 해결함.

