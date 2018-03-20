---
layout: post
title:  "[Solr 6] Schema API"
date:   2018-03-20

---

This post is focused on Korean Users who wants to construct Apache Solr with Korean.

기본적으로 Apache 공식 튜토리얼을 따라 하면서 제가 느낀 부분을 남겨봅니다.

https://lucene.apache.org/solr/guide/6_6/schema-api.html


## Schema API ??

+ Solr schema를 HTTP API 형식으로 재시작없이 설정 추가, 삭제 및 변경을 가능하도록 허용 하는 API.

### Basic Format

+ http://<IP 주소>:<port 주소>/<Solr 이름>/<코어 이름>

### API Entry Points

+ <Basic Format>/schema >>>>> Schema 정보  
+ <Basic Format>/schema/fields >>>>> field 정보
+ <Basic Format>/schema/solrqueryparser/defaultoperation >>>>> Default Operator 관련 정보  

Schema API 실행을 위해 저의 경우 서버에서 curl 형식으로 API를 호출 했습니다.

### 기본 실행 방법

1. Solr를 가동합니다 (Default port:8983)
2. 아래 API 호출 예제중 "New Field 추가"를 서버에서 curl 형식으로 호출 (코어 이름은 new_core)
<img src="https://cdn-images-1.medium.com/max/880/1*wYdE41drpuCugse0co8Wzw.png">
3. Solr UI 에서 생성된 Field를 확인할수 있습니다
<img src="https://cdn-images-1.medium.com/max/880/1*9gZqykQ2ur4Nng5HsRINAA.png">

#### New Field 추가
````
curl -X POST -H 'Content-type:application/json' --data-binary '{
  "add-field":{
     "name":"JinField",
     "type":"string",
     "stored":true }
}' http://localhost:8983/solr/gettingstarted/schema
````

#### 기존 Field 삭제

````
curl -X POST -H 'Content-type:application/json' --data-binary '{
  "delete-field" : { "name":"JinField" }
}' http://localhost:8983/solr/gettingstarted/schema
````

#### 기존 Field 속성 변경

````
curl -X POST -H 'Content-type:application/json' --data-binary '{
  "replace-field":{
     "name":"JinField",
     "type":"date",
     "stored":false }
}' http://localhost:8983/solr/gettingstarted/schema
````

#### 다수 Fields 를 한번에 추가

````
curl -X POST -H 'Content-type:application/json' --data-binary '{
  "add-field":{
     "name":"JinField1",
     "type":"string",
     "stored":true },
  "add-field":{
     "name":"JinField2",
     "type":"string",
     "stored":true },
}' http://localhost:8983/solr/gettingstarted/schema
````
