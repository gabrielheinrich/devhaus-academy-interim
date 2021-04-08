# JS DOM API

Javascript **Document Object** Model Application Programming Interface

## Resources

[Official Explanation](https://developer.mozilla.org/en-US/docs/Glossary/DOM)

The DOM (Document Object Model) is an API that represents and interacts with any
HTML or XML document. The DOM is a document model loaded in the browser and
representing the document as a node tree, where each node represents part of the
document (e.g. an element, text string, or comment).

## `document`: Entry Point into the DOM

The binding `document` gives you access to the loaded document. It represents
the root node of the html tree.

## Getting access to nodes

```js
document;
// The whole document

document.body;
// The <body> element

document.getElementById("login-button");
// Search for element with given id e.g. <button id="login-button">

document.querySelector(".card p");
// Search using a CSS Selector. Will return first selected element only

document.querySelectorAll(".card p");
// Return all elements matching querySelector as a NodeList
```

## Manipulation Nodes

HTML

```html
<div id="app"></div>
```

Javascript
