---
published: true
---
## Ember.js

Ember is a really interesting front-end JavaScript framework. It's different than the main ones (AngularJS, React, Backbone) in that it's **opinionated**. While developing applications in the Ember ecosystem, developers make use of the ember-cli which generates boilerplate code (including tests!) which sets you up for success. However, it's generally known that the learning curve of Ember is steep.

### What's cool

What initially turned me towards Ember was that Twitch.tv uses it for their frontend. I thought, "Hey, Twitch is using Ember and they're a modern leader of the live video streaming industry, Ember must be really cool to work with." In addition, LinkedIn recently redesigned their frontend with Ember.

I think coding-wise, Ember is great in how it allows developers to collaborate on code. Once you know it, reading another Ember.js codebase is pretty simple because of the opinionated nature and conventions of the framework. One of the taglines of Ember is "convention over configuration".

### What's not

Now, the few things I don't like about Ember. Since it never was and isn't the "hot new thing" when it comes to JavaScript frameworks, it can be hard to find resources when starting out. Although the short release cycles of Ember (6 weeks) is great for bug fixes and updates for the community, a lot of things become out-of-date quickly. One of the biggest changes I experienced was how Ember switched from RESTAdapter to JSONAPIAdapter for handling Ajax requests. Many great published books, although written very comprehensively and easy to digest are outdated usually because of the ajax Ember adapter.

### Why I don't recommend it

Going along the lines of Ember ajax requests, I don't particularly love the constraints on JSON data when using JSONAPIAdapter and this is the one thing I like to configure. When building a RESTful API with Node hooked up to a database, I like structuring my returned data as I see fit. Although I can see the benefits of convention in that you know which properties to access with the [JSON API standard](http://jsonapi.org/format/#document-top-level), the Ember adapters don't let you break this mold.

### Not hard and fast

I still appreciate Ember for its unique features and design and will definitely revisit it again, but for now, I think I'll buy into the Kool Aid and stick with React ;). 
