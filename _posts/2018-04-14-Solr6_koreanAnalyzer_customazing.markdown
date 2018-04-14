---
layout: post
title:  "[Solr6] Korean Analyzer(아리랑) Customazing 1 (단어추가 방법)"
date:   2018-04-14

---

This post is focused on My Solr6 and Korean Analyzer named "Arirang" study

한글형태소 "아리랑" 관련된 부분은 기본적으로 아래 카페를 통해 많은 정보를 얻고 있습니다
http://cafe.naver.com/korlucene

이 글은 제가 직접 경험하면서 나온 결과값을 기록해 놓은것입니다.

### 단어 추가 방법

한글 형태소는 기본적으로 "사전 베이스"를 형태소 형태소 분석을 합니다
아리랑 한글 형태소 또한 기본적인 내용이 담긴 .dic 파일이 존재합니다.

위 카페를 통해 github에서 해당 프로젝트를 받고 "Arirang Morph Analyzer"에 사진 파일이 존재합니다 기본적으로 extension.dic 파일에 원하는 파일은 추가하면 아래와 같은 새로운 Output을 얻을수 있습니다.

#### 사전에 "피테라" 단어 추가 전
<img src="https://cdn-images-1.medium.com/max/1000/0*lZNGRLl-odF29Crv.">



#### 사전에 "피테라" 단어 추가 후
<img src="https://cdn-images-1.medium.com/max/1000/0*doNEb1skVKyI9PG2.">

단어 추가전에는 "피테라" 라는 단어가 분리 되어 결과값이 나왔지만, 단어 추가 후 정상적으로 분석이 되는것을 파악 할수 있습니다.
