---
published: true
---
## React Native and Firebase

### What is React Native?

React Native is a library built on top of React for building native mobile applications on iOS and Android. It uses the same general syntax of React (for building web apps) but with different components.

For example, when building a web app in React, you would use a div as a container but in React Native, 'View' is used. Even though learning all these new mobile built-in component names requires some time, React Native components quickly become associated to HTML elements in your head.

Here's a quick comparison between small code snippets of React and React Native (Bear in mind, React uses JSX for templating):

React:
```
render() {
	return (
    	<div>
        	<p>Welcome to React!</p>
        </div>
    );
}
```

React Native:
```
render() {
	return (
    	<View>
        	<Text>Welcome to React Native!</Text>
        </View>
    );
}
```

Notice the similarity? 'View' components replace 'div' tags and 'Text' components replace 'p' tags.

When building React Native applications, most of the work will be in building the front-end. It turns out, routing of different views isn't relatable as the JSX. Another hard thing is testing, but I'll save that for another blog post.

### Firebase

So what can make our lives easier developing React Native applications? Enter Firebase.

Acquired by Google in 2014, Firebase is essentially your entire app backend. Instead of writing a Node + Express server, developers can use Firebase services to handle tons of things including your database, authentication, analytics, and ad revenue services. Firebase can be rather easily integrated into iOS, Android, or web apps.

The coolest thing about the Firebase database if you choose to use it is that it is socket-based so that your app can listen for value changes at specific references and update the app as needed! No need for extra sockets or intervalic database checking, the Firebase node module abstracts and provides a great API.

### Setting up Firebase in React Native

[Firebase documentation](https://firebase.google.com/docs/)

To get started with Firebase and React Native, you'll be using the Firebase Web docs (JavaScript) rather than the iOS or Android. Although this seems strange, the iOS and Android docs are aimed at conventional mobile development in their respective programming languages (Objective-C, Swift, Java, etc.). Since React Native is JavaScript development, JS web development applies here.

The following will be a series of steps to get you up and running! This will require Node, npm, xcode, and react-native-cli to be installed previously.

**Note: This is for iOS specifically, aimed at XCode and its simulator.** 

#### Initialize React Native app

```
// Replace MyNewAwesomeFirebaseApp with a name of your choosing :)

react-native init MyNewAwesomeFirebaseApp
```

The React Native CLI sets up everything to get an app running in XCode. After this finishes, you should be able to cd into the newly made directory named after your app name and run the iOS version with:
```
react-native run-ios
```

The React Native CLI sets up everything to run the default app including installing the npm modules and the xCode build files. To run your application, simply type:

```
react-native run-ios
```

Depending on your computer processing power, this may take a while. While the default project builds, you'll see a terminal window pop up with a dependency package manager. This should stay open while developing and will rebuild your project everytime you reload your application in the simulator.

#### Initialize Firebase ####

After the default 'Welcome to React Native' application opens, now it's time to install Firebase. As I've mentioned above, you can't use the iOS version documentation and should reference the web app/JavaScript side. Things to note are that since there aren't any script tags in React Native, we'll need to use the npm package that Firebase offers.

To start, import Firebase from npm:
```
npm install --save firebase

// In your project:
import * as firebase from 'firebase';
var app = firebase.initializeApp({ /* Copy your config from the firebase console here */ });
```

After this, pick and choose what features from the large number that Firebase offers! Most of the services require you to make a their own specific connections to Firebase. For more details, visit the npm page [here](https://www.npmjs.com/package/firebase)

The ones I've used are Firebase Authentication and Database. Stay tuned for more detailed explanations/guides on those two!