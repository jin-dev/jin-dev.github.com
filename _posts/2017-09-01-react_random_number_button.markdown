---
layout: post
title:  "[React] get random number "
date:   2017-09-01 00:01:30 +0530
categories: science
author: "Jin Woo Park"
---

create react project with 'create-react-app' command.

and modify app.js, here is my codes

````javascript
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';

class App extends Component {
  render() {
    return (
      <div className="App">
        <div className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h2>Component life cycle</h2>
        </div>
      <Body />
      </div>
    );
  }
}


class Body extends Component {
  constructor(props){
    super(props);

    this.state = {
      r: 0

    };
    this.getRandomNumber = this.getRandomNumber.bind(this);
  }

getRandomNumber() { //random number method
  //console.log("The random number is called");
  this.setState({
    r : Math.floor(Math.random() * 10) // it will print a number within 10.

  })
}
  render(){
    return(
      <div>
      <p className="App-intro">
        To get started, edit <code>src/App.js</code> and save to reload.
      </p>//when mouse clicked, it will display random number
      <button onClick={this.getRandomNumber}> Random Number</button>

      <Numbers myNumber={this.state.r}/>

      </div>
    );
  }
}

class Numbers extends Component {

 // test method check the console message from the development tool menu.
  componentDidMount() {
    console.log("componentDidMount called 2");
  }

  componentWillMount() {
    console.log("componentWillMount called here");
  }

  componentWillReceiveProps(newProps){
    console.log("componentWillReceiveProps called");
    }

  shouldComponentUpdate(newProps, nextState){
    console.log("shouldComponentUpdate called");
    return true;
    }

  componentWillUpdate(newProps, neexState){
    console.log("componentWillUpdate called");
  }

  componentDidUpdate(newProps, nextState){
    console.log("Called Component Did update");
  }

  componentWillUnmount(){
    console.log("Called componentWill un mount");
  }



  render(){
    return(
      <div>
      {this.props.myNumber}
      </div>
    );
  }
}

export default App;




````
