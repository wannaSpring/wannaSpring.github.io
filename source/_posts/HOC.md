---
title: HOC 
date: 2020-01-28 09:25:00
img: https://images.pexels.com/photos/355465/pexels-photo-355465.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2
top: true
hide: false
cover: true
coverImg: https://images.pexels.com/photos/355465/pexels-photo-355465.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2
toc: true
mathjax: false
summary: What's HOC and what it can do.
categories: Tech
reprintPolicy: cc_by
tags:
  - React
---
# HOC
## What's HOC
High of components is react component package with another react component. so that's just a wrapper around react component.
such as the function model , we also call Class Factory Methods, we can use haskell to describe that
```
HocFactory:: W: React.Compoent => E: React.Component
```
W(WrapperComponent) refer to component has been wrapped.
E(EnhancedComponent) refers to a new HOC that returns a type of React.

Parcel definection have two different meanings.
1. Props Proxy: HOC operates on props passed to WrapperComponent W.
2. Inheritance Inversion: HOC extends WrappeerCompoent W.


## HOC Factory implementation methods
In this section, we will describe the implementation for the HOC factory.
### Props Proxy
The simple implementation of Props Proxy
```
  function ppHOC(WrappedComponent) {  
    return class PP extends React.Component {    
      render() {      
        return <WrappedComponent {...this.props}/>    
      }  
    } 
  }
```
The main thing here is that the Hoc returns a React element of type WrappedComponent in the render method, and we also pass in the props  recieved by the HOC, which is where name <b>Props Proxy</b> comes from.
```
 <WrappedComponent {...this.props}/> 
 // equal 
 React.createElement(WrappedComponent, this.props, null)
```
Both create a React Element for rendering in a reconciliation process within React. If you want to learn more about React Elements vs Components, see this article by Dan Abramov, and for more information on the reconciliation process, see the documentation.

(Note: the reconciliation process can be understood as the process within React of synchronising the virtual DOM to the real DOM, including comparing the old and new virtual DOM and calculating the minimum DOM operation)

### The reconciliation process
reconciliation process can be understood that unifies behaviour, and the HOC is an implementation based on this idea.

> https://zhuanlan.zhihu.com/p/24776678


