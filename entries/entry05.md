# Entry 5
##### 04/25/2022

### Context

Since last time me and my partner have created our prototype with the functions (addDoc, deleteDoc, updateDoc) we have created a prototype with our core function of creating and editing individual cards. 


We created the editing function by using updateDoc. updateDoc requires a reference to a specific doc through their id. When creating the cards I put the Id as one of the elements that can be shown so I can easily get the current document I have open. 
When I click on the save button I will take the Id of the current opened document and then put it inside the updateDoc function which just by doing
`field = change` which can be easily done. 


```js
document.querySelector('#save').addEventListener('click', function(){
  console.log(document.querySelector('#shortdescription').innerHTML)
  const docId = document.querySelector('#gone')
  const docRef = doc(db, 'cards', docId.innerHTML)
  updateDoc(docRef, {
    name: document.querySelector('#title').innerHTML
  })
  updateDoc(docRef, {
    notes: document.querySelector('#notes').innerHTML
  })
    updateDoc(docRef, {
    shortdescription: document.querySelector('#shortdescription').innerHTML
  })
  document.querySelector('.box').style.display = 'none'
})
```

However this feature needs the user to be able to change the input of the card first. I have paragraph elements setup with contenteditable as true so the user can edit with a click. 

```html
<h1 id=title contenteditable="true" >placeholder</h1>
```

Last is to add the feature of deleting which can be done by using deleteDoc and the document's id.

```js
document.querySelector('#delete').addEventListener('click', function(event){
    deleteDoc(doc(db,'cards', document.querySelector('#gone').innerHTML))
    .then(() => {
      document.querySelector('.box').style.display ='none'
      document.querySelector('.'+document.querySelector('#gone').innerHTML).remove()
    })
  })
```
I take the deleteDoc function and input db which is database and the collection and the id to choose the specific document then the document will be deleted however to make the card disappear as well I select the document and then use the .remove() function.

### EDP

I am currently on the 5th and 6th step of my engineering design process. I have created my minimum viable product prototype and tested it for error. The product's core system is working however it could be improved by making a better design as well as refactoring existing code. My next step is to refactor the code and try to add Auth so that instead of an anonymous product we have a username. 

### Skills

Throughout this process I have improved my debugging skills because creating a prototype comes with many errors such as elements sometimes get all deleted at once and sometimes adding new code will invalidate the other codes. Therefore I have adapted a habit of looking in the console for errors and then finding out the reason behind each error. 

I also developed my skill in research as many bugs are common and websites such as stack overflow is a great community for asking questions and reaching for help. Another way is through researching documentations and tutorials to help figure certain bugs out. 

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)

