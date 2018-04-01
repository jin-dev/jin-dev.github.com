---
layout: post
title:  "[Spring] JPA, Repository"
date:   2018-03-31

---

This post is focused on my Spring study

## JPA

+ Standard F/W of Java ORM
+ Mapping RDB as a instance

JDBC --> Infinite loop in sql query required, infinite loop for Connections(open & close)
Mybatis --> Infinite loop in sql query required, delegation for Connections(open & close)
JPA --> automata for sql query, delegation for Connections(open & close)

### Relationship with Hibernate

+ IF JPA is Dance then --> Hibernate is a dancer.
+ JPA is a one of APIs and it follows Java Platform RDMS.
+ Hibernate is a ORM library and it follows JPA Spec

## Repository

<img src="https://cdn-images-1.medium.com/max/1000/1*1wdFCK-ldG6WLlGaAbwqFQ.png">

### Description

1. Product class provides Getter and Setter
2. ProductRepository is extended with JPARepository<Product, String>
3. real methods perform in RepositoryApplication
4. extra setting is required(ex. H2 DB) in application.properties
