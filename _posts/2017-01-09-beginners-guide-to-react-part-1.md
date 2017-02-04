---
id: 65
title: 'Beginner's Guide to React: Part 1'
date: 2017-01-09T00:24:06+00:00
author: pianistkevinjang@gmail.com
layout: post
guid: http://blog.kevinjang.com/?p=65
permalink: /2017/01/09/beginners-guide-to-react-part-1/
categories:
  - Tutorials
tags:
  - facebook
  - react
  - tutorial
---
After a week-long break from Hack Reactor Remote, the course started up again focusing on MVC frameworks. Among the two we looked at this week, one was React. This blog post will be a journal of my understanding in the form of a beginner&#8217;s tutorial.

#### !!! **Information on this page may be inaccurate or opinionated** due to my inexperience and lack of knowledge with React. **!!!**

<!--more-->

#### MVC (Model-View-Controller)

Before diving into React, one has to understand the concept of MVC development. MVC is a design pattern for website development that separates website components into Models, Views, and Controllers. Models are containers for storage of data. Views take the data stored in models and render them on the webpage for the user. Controllers are the ways in which user interaction changes the state of models.

To form a working example in your head, here are some examples of each:

  * Model examples: Keeps track of a store inventory, state of webpage elements (text is bold, data has been rendered to the page). Usually the data stored here is dynamic, altered at some point in the instance of the webpage
  * View examples: Take the store inventory and display items and prices in an HTML table, render data as text, images, or videos in the DOM
  * Controller examples: Listens for clicks on items or DOM elements and lets the model know it should update the data. For the store inventory, clicks on items should perhaps increase a view count.

#### Is React an MVC?

React definitely has elements of the Model, View, Controller pattern. Looking at other frameworks, however, it may not be full-fledged to handle the model or controller portion of your application. The reasons for my saying this will become more apparent when working with a framework such as Backbone. Therefore, React is most commonly described as the &#8220;view&#8221; portion of an app even though it can technically be used for all three parts of the MVC pattern. This tutorial, in regards to simplicity, will provide examples and instruction for solely using React to handle the 3 parts of MVC.

#### ES6, and JSX

While writing code with React, it&#8217;s usually best practice to use ES6 language. The reason for this are the improvements in readability, ease of use, and functionality of JavaScript. React can be written using ES5, but will require using React methods (React.createClass) and less readable syntax to achieve the same functionality of an ES6 implementation. In addition, writing views with JSX is recommended for readability for yourself and individuals reading your code. The alternative is using React methods again (React.createElement, etc.) to mirror the JSX method.

TLDR: Using ES6 + JSX provides a better experience coding with React.

#### ReactDOM.render() pattern

The entry point of displaying React components is using ReactDOM&#8217;s &#8216;.render&#8217; method. This allows you to specify a React component and choose a DOM element to append to. The usage is as follows:

<pre>ReactDOM.render(&lt;ShoppingList /&gt;, document.getElementById('app'));</pre>

This code takes the &#8216;ShoppingList&#8217; and renders it in the first &#8216;app&#8217; element on the DOM.

#### Functional components

Now, we&#8217;re getting to the good stuff. In React, this is what a simple component can look like:

<pre>let ShoppingList = () =&gt; (
  &lt;div&gt;
    &lt;p&gt;Some text here!&lt;/p&gt;
  &lt;/div&gt;
);</pre>

A point to note here is that this snippet doesn&#8217;t reference React. All it does it return JSX. However, in tandem with ReactDOM.render, React takes the returned JSX and appends HTML.

This is an example of a React functional component, one that is a function (as opposed to a class). Functional components are used when you want to render static HTML that doesn&#8217;t contain the ability the store information or change the stored information. However, functional components can be dynamically rendered based on some passed-in data. That&#8217;s where &#8216;props&#8217; come in.

#### Props/Dynamic rendering

With the previous example of the functional ShoppingList component, &#8216;Some text here&#8217; is hard-coded. Now, how could I pass in an item of my shopping list and return HTML based on that item?

Accepting an argument is the way to go. With React, the convention is to name your component&#8217;s argument &#8216;props&#8217; meaning &#8216;properties&#8217;. An JavaScript object is passed in to the function and accessed using the key.

<pre>let ShoppingList = (props) =&gt; (
  &lt;div&gt;
    // Reference an 'item' property on the props object
    &lt;p&gt;I need to buy {props.item}&lt;/p&gt;
  &lt;/div&gt;
);

// Example usage:
ReactDOM.render(&lt;ShoppingList item="Bananas" /&gt;, document.getElementById('app'));</pre>

In this example, React takes the &#8216;item=&#8221;Bananas&#8221;&#8216; and passes in a props object { item: &#8216;Bananas&#8217; } to ShoppingList which returns the message, &#8216;I need to buy Bananas&#8217;.

The moustaches/curly brackets around &#8216;props.item&#8217; is the way to differentiate JavaScript code from JSX. When you want to comment code in a JSX block within a JS file, you have to use the curly braces and multi-line JavaScript comments.

<pre>&lt;p&gt;
  Some JSX here.
  {/* Ooh, a comment! This won't be converted to HTML */}
&lt;/p&gt;</pre>

* * *

Those were some of the basics of React and there&#8217;s quite a bit more. Unfortunately, because of the intensiveness of Hack Reactor and my need to sleep, I have to bring this blog post to a close. If I write another post to continue this beginner&#8217;s tutorial, it will include &#8216;classical components&#8217;, &#8216;states&#8217;, and &#8216;event handling&#8217;.