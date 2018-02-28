---
layout: post
title:  "[React] simple word cloud with D3.js"
date:   2017-7-27 13:30:30 +0530
categories: science
author: "Jin Woo Park"
---
# This post is based on my personal experiences.

prerequisite

1. npm install react-d3
2. npm install react-d3-cloud

the following code is my data file (Data.jsx)
````Java-script

var React = require('react');
var wordData = [
  { text: 'Hey', value: 1000 },
    { text: 'Jin', value: 500 },
      { text: 'lol', value: 700 },
        { text: 'HAHA', value: 100 },
          { text: 'Nice', value: 16 },
          { text: 'Hi', value: 5000 },
            { text: 'Zoo', value: 5 },
              { text: 'whats up', value: 760 },
                { text: 'Instagram', value: 130 },
                  { text: 'There you are!!', value: 226 }
];
module.exports = wordData;
````
create word-cloud on main jsx file with previous data file.
````Java-script

var React = require('react');
var ReactDOM = require('react-dom');
var WordCloud = require('react-d3-cloud');
var wordData = require('./Data.jsx');

const fontSizeMapper = word => Math.log2(word.value) * 5;
const rotate = word => word.value % 360;

  ReactDOM.render(
<WordCloud
  data = {wordData}
  fontSizeMapper ={fontSizeMapper}
  rotate = {rotate}
/>, document.getElementById('word-cloud')
);
````
<my finaly result>

<img src="https://cdn-images-1.medium.com/max/800/1*iWV1kdxrWo_7KYntOk8w2A.png">
