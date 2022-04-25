# Entry 5
##### 07/26/2005

### Context

Since last time me and my partner have created our prototype with the functions (addDoc, deleteDoc, updateDoc) we have create a prototype with our core function of creating and editing individual cards. 

We created our add feature by using addDoc and taking the information in the text boxes. 

```js
const colRef = collection(db, 'cards')
addDoc(colRef, {
      name: addCardForm.name.value,
      shortdescription: addCardForm.shortdescription.value,
      notes: " ",
      imgurl: addCardForm.imgurl.value,
    })
    
```
When I initialize my code, I first set colRef to my database of 'cards' then when I use the addDoc function I can just put colRef to access my collection and the added doc will be inside the collection of 'cards'.

Next We created a

[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
