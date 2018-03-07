---
layout: post
title:  "[Solr 6] How to synchronize with a Korean morpheme analyzer (한글 형태소 연동)"
date:   2018-03-07
---

This post describes how to synchronize Apache solr 6 with a korean morpheme analyzer called "Arirang".

뛰어난 개발자분들께서 이미 Solr 6 와 한글형태소를 연동해 사용하고 계시겠지만, 제가 여러 삽질(?)을 하면서
성공한 방법을 기록해 봅니다.

#### Prerequisite :
+ Apache Solr 6.2.1
+ Arirang-analyzer (https://github.com/korlucene/arirang-analyzer)
+ arirang-morph-1.0.3 (http://cafe.naver.com/korlucene/1304)

위 준비물을 이용해 초기 연동 작업을 마쳤습니다.
<img src="https://cdn-images-1.medium.com/max/800/1*1gzF0ELvYzC_w1dxmACWJw.png">

### How to

+ Github에서 받은 Arirang-analyzer를 jar 파일로 만듭니다.
+ ../(Solr 폴더)/server/solr-webapp/webapp/WEB-INF/lib로 이동
+ 두개의 jar 파일(Arirang-analyzer, arirang-morph-1.0.3)을 해당 폴더에 복사 붙여넣기
+ ../(Solr 폴더)/server/solr/(Core 폴더)/conf로 이동
+ "managed-schema" 파일 열어 아래 내용 추가

````
<fieldType name="text_ko" class="solr.TextField">
            <analyzer type="index">
                    <tokenizer class="org.apache.lucene.analysis.ko.KoreanTokenizerFactory"/>
                    <filter class="solr.LowerCaseFilterFactory"/>
                    <filter class="solr.ClassicFilterFactory"/>
                    <filter class="org.apache.lucene.analysis.ko.KoreanFilterFactory" hasOrigin="true" hasCNoun="true"  bigrammable="false" queryMode="false"/>
                    <filter class="solr.SynonymFilterFactory" synonyms="synonyms.txt" ignoreCase="true" expand="false" />
                    <filter class="org.apache.lucene.analysis.ko.WordSegmentFilterFactory" hasOrijin="true"/>
                    <!--filter class="org.apache.lucene.analysis.ko.HanjaMappingFilterFactory"/>
                    <filter class="org.apache.lucene.analysis.ko.PunctuationDelimitFilterFactory"/-->
                    <filter class="solr.StopFilterFactory" ignoreCase="true" words="stopwords.txt"/>
            </analyzer>
            <analyzer type="query">
                    <tokenizer class="org.apache.lucene.analysis.ko.KoreanTokenizerFactory"/>
                    <filter class="solr.LowerCaseFilterFactory"/>
                    <filter class="solr.ClassicFilterFactory"/>
                    <filter class="org.apache.lucene.analysis.ko.KoreanFilterFactory" hasOrigin="true" hasCNoun="true" bigrammable="false" queryMode="false"/>
                    <filter class="solr.SynonymFilterFactory" synonyms="synonyms.txt" ignoreCase="true" expand="false" />
                    <filter class="org.apache.lucene.analysis.ko.WordSegmentFilterFactory" hasOrijin="true"/>
                    <filter class="org.apache.lucene.analysis.ko.HanjaMappingFilterFactory"/>
                    <filter class="org.apache.lucene.analysis.ko.PunctuationDelimitFilterFactory"/>
                    <filter class="solr.StopFilterFactory" ignoreCase="true" words="stopwords.txt"/>
            </analyzer>
    </fieldType>
````

+ 한글 형태소를 사용할 field란에 "text_ko" 명시 추가 (ex. title)

````
<field name="title" type="text_ko" indexed="true" stored="true" required="true" />
````

+ Solr 재시작
+ Solr Menu --> Core --> Analysis 에서 위 그림과 같이 정상작동 유무 확인
