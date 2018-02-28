---
layout: post
title:  "[React] Onclick function"
date:   2017-09-06 01:10:30 +0530
categories: science
author: "Jin Woo Park"
---


onClick function is useful(personally) and common method. it executes some event
when mouse button is clicked. To do that, There are 3 steps

1. declare onClick e.g <h2 onClick={this.handleClick}>Just some info</h2>
2. create event function.
handleClick() {
this.setState({cars: this.state.cars.reverse()});
}
3. bind it e.g this.handleClick = this.handleClick.bind(this);
