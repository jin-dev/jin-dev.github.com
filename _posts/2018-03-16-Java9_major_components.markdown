---
layout: post
title:  "[Java 9] Major Components (내가 생각하는 좋은 점)"
date:   2018-03-16

---

This post is focused on Korean Users who wants to know Major Advantages of Java 9.

2017.09 Java 9 이 새롭게 나왔고 이와 비슷한 시기에 Spring 5가 출시 되었습니다.
이번 출시에서 Reactive Stream 기능이 기대 됩니다 --> 함수형 언어에서 가능했던 부분인 반응형 웹 개발이 가능
아래는 제가 생각하는 JAva 9 의 장점 입니다.

### Jshell - The Java shell

+ Test Project or Main Method 없이 code snippets이 가능
+ No more public static void main (String args[]) { .. }   

### HTML5 Javadoc

+ Javadoc은 HTML 형식의 API문서 생성이 가능 (기존 JDK의 경우 HTML 4)

### Diamond Operator

+ <> 형식의 방법이 Java 7 까지 제한적, 이번에는 anoymous Class에 대한 사용이 허용 됨

### Reactive Streams - Flow API

+ Java 9 는 상호 운영 가능한 public-subcribe 프레임워크를 지원
+ 그 정체가 바로 java.util.concurrent Flow의 Reactive Stream
+ Reactive Streams aims to improve concurrency workflows for developers by solving the pain of back-pressure(when fast data source doesn't overwhelm the stream destination)

<img src= "https://cdn-images-1.medium.com/max/1000/1*ojrFPMvKn8chXyD8peeP8Q.png">
