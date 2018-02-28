---
layout: post
title:  "[React] draw table with bootstrap-table"
date:   2017-8-10 14:58:30 +0530
categories: science
author: "Jin Woo Park"
---
# This post is based on my personal experiences.

bootstrap-table is simple and easy to draw tables for biginners(personal opinion)

before draw a table we have to install it with using npm

1. npm install bootstrap-table --save

and required decralations on your jsx file

````Java-script

//decralations
var React = require('react');
var createReactClass = require('create-react-class');
var ReactBsTable  = require('react-bootstrap-table');
var BootstrapTable = ReactBsTable.BootstrapTable;
var TableHeaderColumn = ReactBsTable.TableHeaderColumn;

var tableData = require('../data/tableData.jsx'); // contains table data


/// draw table with bootstrap
var ratingPage = createReactClass({

  render: function() {
    var style = {
    paddingTop: '200'
    };
      return (
  <BootstrapTable data={tableData} striped hover condensed>
        <TableHeaderColumn width='150' dataField='id' isKey={ true }>Rank</TableHeaderColumn>
        <TableHeaderColumn width='150' dataField='Networks'>Networks</TableHeaderColumn>
        <TableHeaderColumn width='150' dataField='Program'>Program</TableHeaderColumn>
        <TableHeaderColumn width='150' dataField='Genre'>Genre</TableHeaderColumn>
        <TableHeaderColumn width='150' dataField='Buzz'>Buzz</TableHeaderColumn>
        <TableHeaderColumn width='150' dataField='Demo'>Demo</TableHeaderColumn>
        <TableHeaderColumn width='150' dataField='Interests'>Interests</TableHeaderColumn>
        <TableHeaderColumn width='150' dataField='Engagement'>Engagement</TableHeaderColumn>
        <TableHeaderColumn width='150' dataField='TV'>Ratings</TableHeaderColumn>
        <TableHeaderColumn width='150' dataField='X'>Ratings2</TableHeaderColumn>
    </BootstrapTable>
      );
  }
});

module.exports = ratingPage;
````
Here is my sample table data for tableData.jsx
````Java-script
var React = require('react');

var products = [{
    id : 10,
    Networks : "123",
    Program : "unknown",
    Genre : "entertainment",
    Buzz : 20000,
    Interests : "unknwon,
    Engagement : "100",
    TV : "17.1",
    X : "18.9"

  },{
      id : 1,
      Networks : "314",
      Program : "Hello",
      Genre : "Personal one",
      Buzz : 20000,
      Interests : "unknwon",
      Engagement : "100",
      TV : "17.1",
      X : "18.9"
    },{
        id : 2,
        Networks : "777",
        Program : "Jin-Dev",
        Genre : "Yes we can",
        Buzz : 20000,
        Interests : "Yeahhh",
        Engagement : "100",
        TV : "17.1",
        X : "18.9"
      } .....
      ];

module.exports = products;

````
