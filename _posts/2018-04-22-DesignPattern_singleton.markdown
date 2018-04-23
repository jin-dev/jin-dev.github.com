---
layout: post
title:  "[Design Pattern] Singleton Pattern"
date:   2018-04-22

---

### Singleton Pattern

+ 해당 class 의 instance가 하나만 만들어지고, 어디서든 그 instance에 접근할 수 있도록 하기 위한 패턴
+ DB 연결에 부분에 유효

#### 발생가능 문제점?
+ Multi Thread 환경에서는 동기화가 안돼 Instance가 여러개 만들어 질수 있음 이를 해결하기 위해 synchronized 선언을 해야됨

public class singleton {

  private static singleton instance;
  public static synchronized singleton getInstance() {

     if(instance == null) {
       instance = new singleton();
     }
     return instance;
   }
 }
