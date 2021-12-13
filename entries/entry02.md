# Entry 2
##### 12/13/2021

Since my last blog entry I had been tinkering with firebase commands. I found out that since the update of firebase 9, many of the tutorials have been outdated and the startup will not work. However after reading the documentation and updated firebase 9 tutorials, I found that commands needed to be individually imported. This new thing is called treeshaking. 

With the knowledge of treeshaking, I imported initializeApp from firebase/app so I can initialize firebase in my files. After that, I was confused with setting up webpack until I follow a [webpack setup tutorial](https://www.youtube.com/watch?v=vK2NoOoqyRo) by NetNinja. I found that to setup Webpack you have to make a package.json and make a webpack.config.js file. The webpack.config file allowed me to take everything in my javascript file and put it all inside a file called bundle.js. Therefore in my html file, all I need to source is the bundle.js.  



[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
