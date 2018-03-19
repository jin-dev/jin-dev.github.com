---
layout: post
title:  "[Solr 6] SolrCloud 기본 실행 방법 (basic Commands) 2"
date:   2018-03-19

---

This post is focused on Korean Users who wants to construct Apache Solr with Korean.

기본적으로 Apache 공식 튜토리얼을 따라 하면서 내가 느낀 부분을 남겨봅니다.
https://lucene.apache.org/solr/guide/6_6/solrcloud.html
지난 Post(https://jin-dev.github.io/blog/Solr6_SolrCloud/) 과 내용이 이어 집니다.

<img src="https://cdn-images-1.medium.com/max/880/1*08rCxKr38-dl5w6KkqCWdg.png">

지난 포스트를 바탕으로 새롭게 default port(8983, 7574)로 solrCloud를 가동 시켰습니다.

### solrCloud 전체 shard Querying

````
http://(IP주소):(port주소)/(solr 이름)/(코어 이름)/select?q=*:*
````

+ 위 형식으로 보낼 경우 전체 Shard에 query를 보냅니다. 현재는 데이터가 없어 0 으로 나옵니다.
+ 그 후 8983 port 코어의 documents로 이동(http://(IP주소):8983/solr/#/gettingstarted/documents)
+ 아래 Solr command 형식으로 실험용 데이터 추가 (나의 경우 id 123213)

```
<add>
  <doc>
    <field name="id">123213</field>
    </doc>
</add>
````

+ 똑같은 방식으로 7574 port 코어에 데이터 추가 (id 77777)

### 특정 shard 에 query 보내기

+ 아래 형식으로 query를 보낼 경우 solrCloud에 존재하는 특정 shard에 있는 데이터만 호출 할 수 있습니다.

````
http://(IP주소):(port주소)/(solr 이름)/(코어 이름)/select?q=*:*&shards=shard1
````

+ 위 형식으로 query를 보낼 경우, 아래와 같이 solr(port 7574) 코어에 저장한 id 77777 이 호출 됩니다.

<img src="https://cdn-images-1.medium.com/max/880/1*WBwM4GcZa9MhuXIvFrJoUA.png">

### 다수의 shard에 query 보내기

+ 아래 형식으로 query를 보낼 경우 solrCloud에 존재하는 다수의 shard에 있는 데이터를 한번에 호출 할 수 있습니다.

````
http://(IP주소):(port주소)/(solr 이름)/(코어 이름)/select?q=*:*&shards=shard1,shard2
````

+ 위 형식으로 query를 보낼 경우, 아래와 같이 다수의 solr 코어에 저장된 id 값들이 호출 됩니다.

<img src="https://cdn-images-1.medium.com/max/880/1*_pQ2-QpzeS1qkfKKPpnB2Q.png">
