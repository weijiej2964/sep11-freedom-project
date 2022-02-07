# Entry 3
##### 2/7/2022

##### Context

Since the last blog entry, I have made progress on firebase authentication. Mainly about the how to sign up, log in, and log out. I used the [Firebase Documentation](https://firebase.google.com/docs/auth) and [tutorial by Net Ninja](https://www.youtube.com/watch?v=9zdvmgGsww0&list=PL4cUxeGkcC9jERUGvbudErNCeSZHWUVlb). I found out that I needed to make a new import for firebase auth. Similarly to importing from firestore, importing from firebase auth follows the same step. Use the import{} with commands inside the brackets and the location after it. Then using a const Auth to help me go into the server's authenthecation backend. 

```js
import{
  getAuth,
  createUserWithEmailAndPassword,
  signOut, signInWithEmailAndPassword,
  onAuthStateChanged
}from 'firebase/auth'

const auth = getAuth()
```
After I imported the required tools for the tasks, I use a form with a submit button to input the username and the password for the account creation. Using the form, when taking in a vaild email and password, longer than a certain amount, the account will be created. The codes are as such:

```js
const signupForm = document.querySelector('.signup')
signupForm.addEventListener('submit', (e) => {
  e.preventDefault()
  
  const email = signupForm.email.value
  const password = signupForm.password.value
  
  createUserWithEmailAndPassword(auth,email,password)
    .then((cred) => {
      console.log("user created:",cred.user)
      signupForm.reset()
    })
  .catch((err) => {
    console.log(err.message)
  })
  
})
```
First, I use querySelector to select the informations on the sign up form. Then when the submit button was hit, It will run following commands. To make it simplier I put the email and password into a constant. Then using the tool "createUserWithEmailAndPassword" , I use auth to access the auth backend and then the email and password of the account that is going to be created. The last part is for errors.

Next I used another form for the log in.

```js
const loginForm = document.querySelector('.login')
loginForm.addEventListener('submit', (e) => {
  e.preventDefault()
  
  const email = loginForm.email.value
  const password = loginForm.password.value
  
  signInWithEmailAndPassword(auth,email,password)
    .then((cred) => {
      console.log('user logged in:', cred.user)
    })
    .catch((err) => {
      console.log(err.message)
    })
})
```
After the user pressed submit with the correct exsisting account, it will take the email and password then put it inside the tool, 'signInWithEmailAndPassword'. It will then go into the backend to see if the account was vaild. If the account was valid it will say that the `user logged in` in the console. Else it going to be an error. 

Next I wanted the user to be able to sign out. So I just used a button and a eventlistener. 
```js
const logoutButton = document.querySelector('.logout')
logoutButton.addEventListener('click',() => {
  signOut(auth)
    .then(() => {
      console.log('the user signed out')
    })
    .catch((err) => {
      console.log(err.message)
    })
})
```
I made a `querySelector` for the button and when the button was clicked, It will use the `signOut` with the auth to sign out the user. It will also post a message inside the console. 

##### EDP

I am currently on step 2 and 3 of the engineering design process experiement with firebase and brainstorm ways to use the concepts given. I learn the basics of the tools I needed and try to think of ways to make these tools into use. Looking forward, I want to be able to use firebase auth to switch pages whenever they log in or log out. 

##### Skills

The skills I have developed the most was consideration and how to learn when building with firebase auth I tried consider about each user having their unique database and information. Using firebase auth allows high security and protection of the user's privacy. When making auth I had to find a way to gather user input and cause a command to run when a event happens. I had to learn on my own about the tools needed for this idea to work. 


[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
