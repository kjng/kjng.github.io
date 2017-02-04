---
id: 78
title: Creating a Server with Node.js
date: 2017-01-18T02:04:18+00:00
author: pianistkevinjang@gmail.com
layout: post
guid: http://blog.kevinjang.com/?p=78
permalink: /2017/01/18/creating-a-server-with-node-js/
categories:
  - Tutorials
tags:
  - express
  - http
  - module
  - node
  - nodejs
  - servers
---
Here are two examples of creating Node.js servers with 5 (or 6) lines of code. There is no routing being done (GET, POST, etc.) and all our server does is return &#8216;Hello World!&#8217; in the HTTP response body.<!--more-->

<pre>var http = require('http');
var server = http.createServer(function(req, res) {
 res.end('Hello World!');
});
server.listen(8080, '127.0.0.1');

// Require Node's http module
// Creates the server with a req/res handler
// Writes 'Hello World' to the response body and sends the response
// Our server will be listening to requests made to localhost on port 8080
</pre>

In this first example, we are using Node&#8217;s built-in &#8216;HTTP&#8217; module. We create the server instance with the method, &#8216;createServer&#8217;, which takes a callback function invoked with request and response objects. To actually have the server listening to requests, we use the method &#8216;listen&#8217; with our specified port and IP address.

* * *

<pre>var express = require('express');
var app = express();
app.use(function(request, response) {
 res.end('Hello World!');
});
app.listen(8080);</pre>

In this second example, we are using the &#8216;express&#8217; module which is a wrapper around the HTTP module used above. Express abstracts some of the boilerplate code and provides a more accessible interface with your Node server. Here, we use 6 lines instead of 5 :(.

Comparing both examples, the code here looks almost the same as the previous which makes it hard to see the apparent benefits of using express vs. http (bare node). Some express methods such as &#8216;.get&#8217; and &#8216;.post&#8217; make it easy to handle the respective HTTP request methods and middleware allows for easier parsing, authentication, and session handling, to name a few pros.

#### References

<https://nodejs.org/api/http.html>

<http://expressjs.com/en/starter/hello-world.html>