# Entry 4
##### 3/15/2022

### Context

Since my last blog, I have made a general idea of what the foundation of firebase is.
Following the learning, me and my partner created a plan for our freedom project, breaking down each part by components and deadline. 
The base code have taken inspirations from the [firebase documentation](https://firebase.google.com/docs) and [NetNinja's Firebase 9 Series](https://www.youtube.com/watch?v=9zdvmgGsww0&list=PL4cUxeGkcC9jERUGvbudErNCeSZHWUVlb). 

First I initialized the firebase and this time also the firestore. 
I took many different functions such as `collection` and `getDocs` to help me create my project
```js
import{
  getFirestore, collection, getDocs,
  addDoc, deleteDoc, getDoc, doc,
  onSnapshot
} from 'firebase/firestore'

//init firestore
const db = getFirestore()

//collection ref
const colRef = collection(db, 'cards')
```
This code above gave me the ability to access and manipulate my firebase database. 


Next I created a set of codes that will reference my collection in firebase.
This code creates array of all my documents in a specific named collection, In this case, its 'cards'

```js
let cards = []
getDocs(colRef)
  .then(function(snapshot){
    // let cards = []
    snapshot.docs.forEach(function(doc){
      cards.push({ ...doc.data(), id:doc.id })
    })
```
This set of codes uses the `getDocs` function on the collection reference to 'cards' and then it will snapshot each document and put it in the array. 

Next I would reference this array of documents and for each one, I created a `card` that will contain the overview info. 

```js
      //create card structure
      var place = document.createElement('div')
      var card = document.createElement('div')
      var picture = document.createElement('img')
      var bod = document.createElement('div')
      var names = document.createElement('h4')
      var description = document.createElement('p')
      var docId = document.createElement('p')
      //add class
      
      place.classList.add('col-sm-10', 'col-md-5', 'col-lg-4', 'col-xl-3', event.id)
      card.classList.add('card')
      picture.classList.add('card-img-top', 'col-xl-3')
      bod.classList.add('card-body')
      names.classList.add('card-title')
      description.classList.add('card-text')
      docId.style.display = 'none'

      //insert info
      picture.src = event.imgurl
      names.innerHTML = event.name
      description.innerHTML = event.shortdescription
      docId.innerHTML = event.id
      //construct card
```

With each element in place, you will be able to click on the card and it will let a box, that was invisible and covers the whole page, appear.  
It will then take the id from `docId` above and use it to reference the database again.

```js 
let currentDoc = thing.target.nextElementSibling.children[2].innerHTML
let docRef = doc(db, 'cards', currentDoc)
```

By using the reference, I made the box with elements change on behalf of the doc with the id referenced.

```js
onSnapshot(docRef, (doc) => {
  cardImg.src = doc.data().imgurl
  cardName.innerHTML = doc.data().name
  cardDesc.innerHTML = doc.data().shortdescription
  cardNote.innerHTML = doc.data().notes
  cardid.innerHTML =  currentDoc
})
```
After, We worked together and created the delete and add function that is done through all the functions imported from firestore. 
After knowing just how each function works, the rest is very customizable
The delete function uses the deleteDoc(doc('db',collectionName, idOfDoc)
The add would be the same but intake inputs
```js
    addDoc(colRef, {
      name: addCardForm.name.value,
      shortdescription: addCardForm.shortdescription.value,
      notes: " ",
      imgurl: addCardForm.imgurl.value,
    })
```
The different subjects like name, shortdes, notes are the different variables you create. 

### EDP
I am currently in the 3rd and 4th step of the engineering design process. Me and my partner had started to plan and create our minimum viable products. Currently creating the functionality of our products. Looking forward, we are going to continue building on our product's functionality and adding authentication and style to our product as well. 

### Skills 
The skills that I have grown the most in were collaboration. Collaboration is important and complex when working with coding. Me and my partner used our plan to separate when we will be working so we will not create conflict in our codes. More importantly, in large scale projects, being collaborative is extremely important and when working on this project I feel like I have grown a lot in my ability to work collaboratively. 




[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)

