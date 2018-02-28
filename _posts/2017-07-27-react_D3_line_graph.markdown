---
layout: post
title:  "[React] simple line graph with D3.js"
date:   2017-7-27 13:30:30 +0530
categories: science
author: "Jin Woo Park"
---
# This post is based on my personal experiences.

prerequisite

1. npm install react-d3
2. npm install react-d3-cloud

the following code is my data file (lineData.jsx)
````Java-script

var React = require('react');
var lineData = [
  {
    name: "series1",
    values: [ { x: 0 , y: 10 }, { x: 2 , y: 12 }, { x: 4 , y: 6 }, { x: 6 , y: 15 }, { x: 8 , y: 20 }]
  },
  {
    name: "series2",
    values: [ { x: 0 , y: 20 }, { x: 2 , y: 24 }, { x: 4 , y: 30 }, { x: 6 , y: 15 }, { x: 8 , y: 5 }]
  }
];
module.exports = lineData;

````
create a line graph on main jsx file with previous data file.
````Java-script

var React = require('react');
var ReactDOM = require('react-dom');
var rd3 = require('react-d3');
var LineChart = require('react-d3/linechart').LineChart;
var lineData = require('./lineData.jsx');


  ReactDOM.render(
<LineChart
  legend={true}
  data={lineData}
  width='100%'
  height={400}
  viewBoxObject={{
    x: 0,
    y: 0,
    width: 500,
    height: 400
  }}
  title="Line Chart"
  yAxisLabel="Altitude"
  xAxisLabel="Elapsed Time (sec)"
  gridHorizontal={true}
/>, document.getElementById('line-user')
);
````
<my finaly result>
