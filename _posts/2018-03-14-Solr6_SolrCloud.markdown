---
layout: post
title:  "[Solr 6] SolrCloud 기본 실행 방법 (basic Commands)"
date:   2018-03-14

---

This post is focused on Korean Users who wants to construct Apache Solr with Korean.

기본적으로 Apache 공식 튜토리얼을 따라 하면서 제가 느낀 부분을 남겨봅니다.
https://lucene.apache.org/solr/guide/6_6/solrcloud.html

### SolrCloud ??
+ Solr가 Clustering 형식으로 구현된 방식
+ fault tolerance 와 high availability 을 보장
+ 결론 -->  Standalone 형식이 아닌 여러대의 Solr를 뭉쳐 확장성, 안정성을 확보

+ Zookeeper가 Internal 형식으로 solrcloud가 가동될때 같이 동작하나, External 형식으로 따로 설치해서 연동할 것을 추천하고 있음

### 기본 실행 방법

+ ../(Solr폴더)/bin 으로 이동
+ bash solr -e cloud 로 실행

실행하면 설정 부분 세팅을 해야 됩니다.
오른쪽 괄호[] 안이 기본 설정 부분을 참고해 진행합니다.

<img src="https://cdn-images-1.medium.com/max/880/1*oZ2BldIqkXbGenpjcoh0zA.png">

설정 완료 후, 아래 형식의 주소로 접속 합니다.

+ http://(IP 주소):(Port No)/solr/#/~cloud


아래와 같이 설정된 Cloud 확인이 가능합니다.


<img src="https://cdn-images-1.medium.com/max/880/1*08rCxKr38-dl5w6KkqCWdg.png">
