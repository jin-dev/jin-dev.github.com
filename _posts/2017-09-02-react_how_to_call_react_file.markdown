---
layout: post
title:  "[react] How to call react files"
date:   2017-09-02 20:45:30 +0530
categories: science
author: "Jin Woo Park"
---
In this post, I will describe how to get react(js)files from app.js

first create react project with "create-react-app"

1. first my react file(intro.js)

````javascript
import React, { Component } from 'react';


class Intro extends Component {
    render() {
      return(
        <div>

        <p className="App-intro">
          (Modified Version)To get started, edit <code>src/App.js</code> and save to reload.
        </p>

        </div>
      );
    }
    }

    export default Intro;

````

Here is my app.js 
````javascript
import React, { Component } from 'react';
import logo from './logo.svg';
import './App.css';
import Header from './Header';
import Intro from './Intro'; // get intro.js

class App extends Component {
  render() {
    return (
      <div className="App">


      <Intro /> //call method
      </div>
    );
  }
}

export default App;
````
