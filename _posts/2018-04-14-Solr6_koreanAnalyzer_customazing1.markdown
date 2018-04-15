---
layout: post
title:  "[Solr6] Korean Analyzer(아리랑) Customazing 2 (Type 부분 변경)"
date:   2018-04-15

---

This post is focused on My Solr6 and Korean Analyzer named "Arirang" study

한글형태소 "아리랑" 관련된 부분은 기본적으로 아래 카페를 통해 많은 정보를 얻고 있습니다
http://cafe.naver.com/korlucene

이 글은 제가 직접 경험하면서 나온 결과값을 기록해 놓은것입니다.

### Type 부분 변경

기본적으로 Word, Korean, Symbol 형식의 Type이 존재 합니다만, 특정 키워드 (ex E-mail) 과 같은 부분을 위해 새롭게 Type 을 만들수 있습니다.

위 카페를 통해 github에서 "Arirang Project "에서 Clone 합니다. 기본적으로 "Korean Filter" 자바 클래스에서 Type 부분에 대한 것을 추가 할수 있습니다.
(사진은 추후 올리겠습니다.)
