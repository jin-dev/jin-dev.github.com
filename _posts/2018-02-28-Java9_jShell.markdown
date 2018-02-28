---
layout: post
title:  "[Java 9] Java Shell "
date:   2018-02-28
---

In my personal opinion, one of most beautiful components of Java9 is Java shell.

## Advantages
+ no more "public static void main(String[] args)" method.
+ provides a Read Eval Print Loop(REPL) shell for Java.
+ provideds immediate feeback for learning Java and its APIs.

### How to use
1. open your command prompt
2. type "jshell -v"

### Hello Method in JShell

Past java versions
````
public class Main {
  public sttic void main (String[] args) {
    System.out.println("Hello Jin");
  }
}
````
#### In JShell
<img src="https://cdn-images-1.medium.com/max/800/1*udlQwFkgMyAz83csRhqMGQ.png">
