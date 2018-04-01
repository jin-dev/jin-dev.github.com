---
layout: post
title:  "[React.js] const & let"
date:   2018-03-31

---

This post is focused on my personal React.js study

## Description

+ var helloWorld = "Hello Jin" << Possible, but not in common way
+ In ES6 java-script variable decleration begins with const or let

### const

 + Impossible. const variable can not be changed after decleration.

const helloWorld = " Welcome to React world"

hellowWorld = "Welcome Jin"

 + following code is a possible way.

const helloWorld = {
    text: 'Hello'
};

helloWorld.text = 'Hi';


### let

+ following code is a possible way

let helloWorld = " Welcome to React world"
hellowWorld = "Welcome Jin"
