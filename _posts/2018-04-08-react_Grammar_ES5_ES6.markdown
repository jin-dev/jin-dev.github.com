---
layout: post
title:  "[React] different grammar between ES5 and ES6"
date:   2018-04-08

---

This post is focused on my React.js study


### ES5
const name ='Jin';

const user = {
name : name,
};

### ES6
const name = 'Robin';

const user = {
name,
};

### ES5
var userService = {
getUserName: function (user) {
return user.firstname + ' ' + user.lastname;
},
};

### ES6

var userService = {
getUserName (user) {
return user.firstname + ' ' + user.lastname;
},
};
