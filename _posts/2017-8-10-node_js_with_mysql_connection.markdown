---
layout: post
title:  "[Node.js] How to get connection with MySQL"
date:   2017-8-10 17:58:30 +0530
categories: science
author: "Jin Woo Park"
---
# This post is based on my personal experiences.

prerequisite

1. npm install mysql

here is the sample codes
````Java-script

var mysql = require('mysql') // declear MySQL connection
var con = mysql.createConnection({
  host: "db Address",
  user: "write db ID",
  password: "write db Password"

  });

  con.connect(function(err) {
    if(err) throw err;
    consoloe.log("DB Connection worked");
    con.query("Write your own query", function(err, output){
      if(err) throw err;
      console.log("Query worked");

      });


  });
````
