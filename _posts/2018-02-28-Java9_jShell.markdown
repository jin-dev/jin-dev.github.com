---
layout: post
title:  "[Java 9] Java Shell "
date:   2018-02-28
---

In my personal opinion, one of most beautiful components of Java9 is Java shell.

## Advantages
+ no more "public static void main(String[] args)" method.
+ provideds immediate feeback for learning Java and its APIs.


## How to use
1. open your command prompt
2. type "jshell -v"


## How to create Hello method in JShell (Java Shell)

### Past java versions

````
public class Main {
  public sttic void main (String[] args) {
    System.out.println("Hello Jin");
  }
}
````
### In JShell
````
System.out.println("Hello Jin");
````
