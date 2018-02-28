---
layout: post
title:  "[react] Hello World with ES6 "
date:   2017-8-24 22:01:30 +0530
categories: science
author: "Jin Woo Park"
---
# This post is based on my personal experiences.

For main javascript file
````javascript
import React from 'react';

class App extends React.Component {
    render(){

        return (
                <h1>Hello React Skeleton</h1>
        );
    }
}

export default App
````
For main index javascript file
````javascript
import React from 'react';
import ReactDOM from 'react-dom';
import App from './components/App';

const rootElement = document.getElementById('root');
ReactDOM.render(<App />, rootElement)
````
