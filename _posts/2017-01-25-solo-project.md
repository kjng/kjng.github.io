---
id: 83
title: Solo Project
date: 2017-01-25T12:39:58.000Z
author: pianistkevinjang@gmail.com
layout: post
guid: 'http://blog.kevinjang.com/?p=83'
permalink: /2017/01/25/mvp-project/
categories:
  - General
  - Projects
published: true
---
Yesterday, I completed my first project at Hack Reactor Remote. The goal of the project was to create a &#8216;minimum viable product&#8217;, or a web app with a very limited scope. This was done over the course of two days!<!--more-->

### LOL Whiteboard

For my project, I decided I wanted to build something League of Legends (LOL) related. While brainstorming, I initially wanted to make a strategic whiteboard app that used the League of Legends map as a background:

<img src="https://i1.wp.com/ddragon.leagueoflegends.com/cdn/6.8.1/img/map/map11.png?resize=219%2C219" />

However, this was before I realized that the MVP project was only 2 days long. So I scoped down.

&nbsp;

### LOL Champion Viewer

My next idea was to make a League of Legends champion viewer displaying all the characters of the game. Users would be able to interact with images by clicking on them and the app would display info in a polished and pretty way. This idea though, didn&#8217;t align with my personal development goals.

&nbsp;

## My Goals

My goals for this MVP project was to develop a web app using the [MEAN](https://meanjs.org/) stack. The stack consists of using four primary technologies: MongoDB, Express, AngularJS (not Angular 2), and Node.js. Of the four pieces of tech, I was the most comfortable with the backend using Node and Express. Therefore, I wanted to focus on learning MongoDB and AngularJS.

With a League of Legends champion viewer, I estimated that I would barely be interacting with the backend and MongoDB. Essentially, I would just send a GET request for champion data, and boom, done. That would be one single HTTP request for the entire app. Although there would have been heavy work with Angular routing and views (more on this later), it would be a project primarily focused on Angular with little work elsewhere. I wanted an app that required a more even distribution of work throughout the tech stack.

&nbsp;

## lol-champions

So I landed on a League of Legends timeline-like app where users could add a champion to the board and add notes under each champion. This allowed me to explore a bit more with MongoDB, creating new Documents for each champion added with an array of notes.

On the first day, I quickly set up a Node server using express, that had a /champions API route. The /champions route responds to GET and POST requests. On a GET request, the server queries MongoDB for all the pre-existing champions on the board and returns all entries. On a POST, the user would send JSON consisting of a champion name, and short title/description. This would add a new document containing the name, title, and image for the champion (from the Riot static data server). By the end of the first day, I had something that looked like this:

![First day site]({{site.baseurl}}/images/Screen-Shot-2017-01-25-at-8.55.45-AM.png)

While this met what I perceived as the minimum requirements for the MVP project, I wanted to do more. I planned for a better UI, note functionality, and multiple Angular views.

&nbsp;

## Second Day

On the second day, I started out with implementing the notes feature. At the point where I left off the first day, each champion post document structure didn&#8217;t have a notes field. Therefore, I had to modify my existing database architecture to add the notes array.

After this was done, I created a simple note submission form under each champion.

&nbsp;

### One Rabbit Hole

After completing my note submission, I wanted to improve the UI. I stumbled upon [angular-deckgrid](https://github.com/akoenig/angular-deckgrid). This seemed like a nice display library for my champions but with one caveat &#8211; it hasn&#8217;t been updated since 2014! I disregarded this and tried using this library.

However, I quickly ran into the issue of my controller&#8217;s scope change not updating the deckgrid&#8217;s directive. 🙁

For the functionality I was desiring (adding a note via a submit button), I ran into the issue of the deckgrid directive not having access to my controller. While I could add my main controller to the directive, this was not an elegant solution because there were now two instances of my controller.

Therefore, I reverted back a bit and decided to code without random libraries so that I could understand exactly how my code interacted with itself without other people&#8217;s code disrupting mine.

&nbsp;

### Bootstrap &#8211; Angular &#8211; Bootstrap

In the next part of working on MVP, I think fatigue was setting in and my workflow was bouncing back and forth.

After removing deckgrid, I decided to learn and use [Bootstrap](http://getbootstrap.com/) to style my app. Once I added bootstrap to my project via css and angular-ui-bootstrap (didn&#8217;t get to use these directives, unfortunately), I turned back to Angular to add some new views (pages).

Previously, I wasn&#8217;t using ng-view, making my app a literal single page app (haha). Therefore, I injected ngRoute in order to use $routeProvider for rendering views while visiting links. As a proof of concept, I added a landing page for my app and contact page and the main portion of my app was moved to the &#8216;tracker&#8217; page. Then, I moved back to bootstrap.

After experimenting and perusing Bootstrap documentation, I styled my app a bit and I was done!

Final product image:

![Final site image]({{site.baseurl}}/images/Screen-Shot-2017-01-25-at-9.34.43-AM.png)

## Closing Thoughts

It was really fun to work solo and build my first &#8216;completely solo-developed no-template full-stack MEAN&#8217; web application. I wouldn&#8217;t have imagined building something like this just a few months/weeks ago.

You can check out my lol-champions site deployed on

Heroku: <https://guarded-shelf-26292.herokuapp.com/> and at

Github: <https://github.com/kjng/lol-champions>.
