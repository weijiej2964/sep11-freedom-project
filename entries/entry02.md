# Entry 2
##### 12/13/2021

Since my last blog entry I had been tinkering with firebase commands. I found out that since the update of firebase 9, many of the tutorials have been outdated and the startup will not work. However after reading the documentation and updated firebase 9 tutorials, I found that commands needed to be individually imported. This new thing is called treeshaking. 

With the knowledge of treeshaking from the firebase [documentation](https://firebase.google.com/docs/web/setup?authuser=0), I imported initializeApp from firebase/app so I can initialize firebase in my files. After that, I was confused with setting up webpack until I follow a [webpack setup tutorial](https://www.youtube.com/watch?v=vK2NoOoqyRo) by NetNinja. I found that to setup Webpack you have to make a package.json and make a webpack.config.js file. The webpack.config file allowed me to take everything in my javascript file and put it all inside a file called bundle.js. Therefore in my html file, all I need to source is the bundle.js. Then I imported the commands that I would like to use:

```js 
import {
  getFirestore, collection, onSnapshot, 
  addDoc, deleteDoc, doc,
  query, where, 
  orderBy,serverTimestamp
} from 'firebase/firestore'
```
With the imported commands I can then change things in my firebase firestore. With addDoc I can add a document to my firestore collection.
With deleteDoc is the same but delete instead of add. 
With orderBy I can change the orientation of the documents and etc. 

I am currently in stage 2 and 3 of the EDP process where I research and brainstorm for possible solution. With the knowledge that I can bring many different commands using the import method, I can think of many solutions to make my project. 

For skills, I have practice ways to learn. Not only have I need to watch videos but also read documentations to understand firebase. Sometimes even ask peers for help whether in school or on slack. Choosing the best method to learn each piece of information have been a big improvement of mine. I can use video tutorials for complex setup such as webpack and use documentation for small chunks of information. 


[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
