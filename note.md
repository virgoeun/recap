Accessing Element by Class Name (`.getElementsbyClassName`)


```ts
let elements = document.getElementsByClassName(names);
```
Returns an array of all child elements which have all of the given class names.

<b>HTML Collections :</b> <br>HTML Collections : Array-like of elements
The HTMLCollection is an array-like object but is not an array. So we can’t use the array methods such as 
`.forEach`, `.map()` `.push`, etc.

To iterate over an HTMLCollection, we should use a for loop or `spread operator[...]`

OR turning into an array with `Array.from()`
```ts
let elements = document.getElementsByClassName(names);
let arrayElements = Array.from(elements); 
// Convert to an actual array
```

```ts
// Now you can use array methods on arrayElements
arrayElements.forEach(element => {
  // Do something with each element
});
```
<br>
<b>querySelector</b>
<br>: it returns the first element within the document
```ts 
let theFirstFoundElem = document.querySelector(selectors);
(Selectors can be one or more selectors)
```
<br>
<b>querySelectorAll</b><br>
: The method .querySelectorAll() returns a list of the elements within the document that match the specified group of selectors.
<br>


```ts 
let elementList = document.querySelectorAll(selectors);
(Selectors can be one or more selectors)
```
```ts 
Example)

let allDivs = document.querySelectorAll('.mouse, #cat');
console.log(allDivs); 

[div#cat, div.mouse, div.mouse, div.mouse]
```


This example returns a list of all div elements within the document with either a mouse class or a cat id.

<b>.className</b><br> : Getting & Setting the Class Name
The className property of the element gets and sets the value of the class attribute of the specified element.

```ts 
  let cName = element.className;
```

<b>.id: <br>Getting and Setting the ID</b>

```ts
let idStr = element.id; // get the id of "element"
 ```

This is different from .getElementById/ClassName.
This sets & get to the ID (not the element)

```ts
Example)

let myElement = document.createElement("div");
myElement.id = "myId"; // Sets the id attribute of the element
let elementId = myElement.id; // Gets the id attribute value
console.log(elementId); // This will log "myId"
```

<b>Reference </b><br>
`.getAttribute()` Vs `.getAttributeNode()`<br><br>
In JavaScript and DOM manipulation, both element.getAttribute() and element.getAttributeNode() are used to retrieve information about attributes of a DOM element, but they have different purposes.

`element.getAttribute(attributeName)`<br>: This method is used to retrieve the value of the specified attribute on the element. You provide the name of the attribute as an argument, and the method returns the value of that attribute. If the attribute doesn't exist, it returns null.

`.getAttribute()`<br>
```ts 
let myElement = document.createElement("div");
myElement.setAttribute("data-value", "42");

let attributeValue = myElement.getAttribute("data-value"); // Retrieves the value of the "data-value" attribute
console.log(attributeValue); // This will log "42"
```

`.getAttributeNode()`
```ts 
let myElement = document.createElement("div");
myElement.setAttribute("data-value", "42");

let attributeNode = myElement.getAttributeNode("data-value"); // Retrieves the attribute node for the "data-value" attribute
console.log(attributeNode.name); // This will log "data-value"
console.log(attributeNode.value); // This will log "42"
```
<br>

In the context of `element.getAttributeNode()`, the "node" refers to the DOM node object representing the attribute itself. In the example, attributeNode is an object of type Attr that contains information about the "data-value" attribute of the myElement element.

In short, while `element.getAttribute()` is more commonly used to retrieve just the attribute value, `element.getAttributeNode()` is used when you need more detailed information about the attribute node, including both its name and value.
