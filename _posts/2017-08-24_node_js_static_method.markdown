---
layout: post
title:  "[node.js] static method "
date:   2017-8-24 23:01:30 +0530
categories: science
author: "Jin Woo Park"
---
# This post is based on my personal experiences.

create node.js file with express

```javascript
var express = require('express');
var app = express();
var bodyParser = require('body-parser');

app.listen(3000, function() { // when connection with port 3000 is linked then the hello message would be printed.
	console.log("Hello back-end");
});

app.use(express.static('public'))
app.use(bodyParser.json()) //to receive json format text
app.use(bodyParser.urlencoded({extended:true})) //to receive any format excluding json

app.get('/', function(req, res) {
	console.log('test');
	res.sendFile(__dirname + '/public/main.html')
});

app.get('/main', function(req,res) { // when connection with URL "../main" is linked then, the main.html page would be displayed with the console message.
	console.log("you are in main domain");
	res.sendFile(__dirname + '/public/main.html')
});

app.post('/email_post', function(req, res){ // lastly, this function works similarly as previous method. But, it prints received text on webpage.
	//to receive "post" we must declear body-parser;
	console.log("yes you are entered");
	console.log(req.body.email);
	res.send("<h1>welcome " + req.body.email + " </h1>")

})

````
