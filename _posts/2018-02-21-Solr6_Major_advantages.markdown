---
layout: blog
title:  "[Solr 6] Major_advantages"
date:   2018-02-21
---

I'm planning to use Apache Solr 6 with a korean morpheme analyzer.

Before that,
This is my reason that why Solr6 is chosen to use.

Many English version of solr 6 blogs exist, hence here I will write my blog with korean.

### Stable
+ 현재 Solr7 (2018.02 기준) 버전이 나온 이후 Solr6 가 Stable 하다고 판단

### 한글형태소 연동 가능
+ 최신 버전의 한글형태소가 Solr6 까지 호환 되는것을 확인

### SQL Interface component
  + Solr에 Query를 보낼때 SQL 형식으로 사용 가능
  + ex) SELECT id from table1 order by psid desc limit 10
