---
layout: post
title:  "[Solr 6] How to run Solr and Core creation ( Solr 시작과 Core 생성 방법)"
date:   2018-03-07
---

This post describes How to run solr and create Core.


### How to

+ Solr 6.2.1 압축 풀기
+ 생성된 Solr 폴더에 Core 폴더 생성
  1.  ../(Solr 폴더)/server/solr/Core 폴더
  2.  ../(Solr 폴더)/server/solr/configsets/data_driven_schema_configs안에 있는 conf 폴더를 생성된 Core 폴더에 복사

+ ../(Solr 폴더)/bin 에서 명령어(bash solr start)로 Solr 가동
+ 접속 (localhost:8983/solr)
+ Solr Menu --> Core Admin --> Add core 순으로 클릭
+ instanceDir 에 위에서 생성한 Core 폴더명 입력
+ "Add Core" 클릭
+ 생성된 코어를 확인

<img src="https://cdn-images-1.medium.com/max/800/1*vhhhT91P-rj6y0qCmJvh2Q.png">
