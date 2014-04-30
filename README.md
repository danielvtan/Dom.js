# Selector.js
an alternative element selector using id/class with element manipulation functionalities

### Features
* select an element by:
   * id
   * class name
   * tag
* select multiple element
* specified selection (child of an element)
* element manipulation
   * add a class
   * remove a class
   * set an attribute
   * set style
   * access of element attributes

### Element selector example
```javascript
Selector.el("testID")
Selector.el("#testID")
Selector.el(".test-class")
Selector.el("div")
Selector.el("#testID .test-class")
Selector.el(".test-class-parent .test-class") 
Selector.el(".test-class-parent .test-class div")
```
you can also use el as Shortcut for Selector.el
```javascript
el("testID")
```
these all returns the ff functions that can be used to manipulate the element
* `addClass("class-name")` - add a class name
* `removeClass("class-name")` - remove a class name
* `set("onclick", function(){})` - set an attribute on the element
* `css({ width:"800px", border:"1px solid #000"})` - apply css (apply using style attribute of the element)
* `_dom()` - returns the dom element/s selected (returns an array of elements if multiple element is selected)
* `animate()` - not yet properly implemented
* each function also returns the functions first returned which can be used in chain calling (except for `_dom()`)

```javascript
Selector.el("#testID")
        .addClass("test-class")
        .set("onmouseover", function(){})
        .css({ background: "#000"})
        .addClass("class-name");
```
## How to use the element selector
```javascript
// returns a normal dom element
// use as a normal element
Selector.el("testID") // by id

// returns an object with functions
// can be used to manipulate a single element
Selector.el("#testID") // by id

// returns an object with functions
// can be used to manipulate all element with the specified class
Selector.el(".test-class") // by class

// returns an object with functions
// can be used to manipulate all element with the specified class
Selector.el("div") // by tags


// use spaces if you need to specify targeted elements
// returns an object with functions
// can be used to manipulate all element with the specified class
Selector.el("#testID .test-class") // by tags

```