---
id: 58
title: Working with D3
date: {}
author: pianistkevinjang@gmail.com
layout: post
guid: 'http://blog.kevinjang.com/?p=58'
permalink: /2017/01/02/working-with-d3/
categories:
  - General
  - Projects
published: true
---
Over Hack Reactor break, I had time to learn the basics of D3, a JavaScript library for building data visualizations. At first, it took a while to understand the concepts of the library because of sparse documentation with many missing holes. However, after a bit, I was able to Google around and find what I needed to learn enough to build a simple game.<!--more-->

The game in question was an asteroids clone. To simplify the game, though, I left out the ability to shoot and destroy asteroids so the game was more of an &#8220;asteroid avoid&#8221; game. Now, games aren&#8217;t the traditional implementation of the D3 library but the simplified task made the use of D3 easier for a newbie. Through making the game, I learned to use D3 selections (e.g. select, selectAll, and enter) and some of the data binding and updating methods (data, enter). Although I didn&#8217;t use the _exit_ selection in my game, I learned that it&#8217;s an important part in a visualization to remove elements from the DOM (e.g. filtering out elements in a graph). Here&#8217;s a snapshot of my game:

![asteroidavoid.png]({{site.baseurl}}/images/asteroidavoid.png)

The game is made up of 4 main parts: the HTML, CSS, JavaScript, and D3 library file (of course). The HTML provides a skeleton of divs for the game area and scoreboard, the CSS handles simple styling of the gameboard and scoreboard (font families, background colors), and the JS handles the rest. Working with D3 to make my game made me realize the similarity in using CSS selectors like in JavaScript. In my .js using D3, I was able to create DOM nodes for the player (red circle) and enemies (green circles) while also updating the scoreboard and a collision checking function. The game can be easily tweaked in difficulty by modifying a gameOptions global variables containing keys for number of enemies as well as the rate in which the enemies move across the screen.

If I have more time/interest in improving my game, I have a short list for myself sorted roughly by priority:

  1. Restrict my player to the game area (Right now, the game allows the user to drag the player &#8220;off board&#8221;, avoiding all enemies)
  2. Use D3 tweening functions to control the enemy movement
  3. Refactor uses of setInterval (currently used to loop enemy movements infinitely and detect collisions) to use D3 timer
  4. Style the game better

All in all, I enjoyed learning D3 and hope to work with it again to in more of a traditional application, for example with a line/bar graph. Some resources I used for D3 were dashingd3js (_really good_, need to go through all of the tutorials), d3Garden, and some chapters of Scott Murray&#8217;s D3 tutorials.

In regards to D3 though, I have to put it on the back-burner because HRR starts back up again tomorrow. I&#8217;m excited to learn more libraries and frameworks of the web!
