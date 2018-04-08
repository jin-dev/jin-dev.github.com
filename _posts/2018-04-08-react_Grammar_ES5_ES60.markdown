---
layout: post
title:  "[React] Hot Module Replacement(HMR) "
date:   2018-04-08

---

This post is focused on my React.js study

### Hot Module Replacement

이하 HMR 은 새로고침 조차 할 필요없이 바로 브라우저에 적용 되는 기능
index. js에 아래 코드만 넣고 저장하면 끝

````
if (module.hot) {
module.hot.accept();
}
````
