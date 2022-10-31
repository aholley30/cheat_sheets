# <p align="center">Javascript Cheat Sheet</p>

### General
- To print with variables: 
  ~~~javascript
  console.log(`printin with a ${var}.`);
  console.log('printin with a ' + var + '.');
  ~~~
- Using ```typeof variable``` will return a string of the type.
- Iterate through all keys in an object with a for each loop
  ~~~javascript
  for (let user in users) {
    console.log(user);
  }
  ~~~
### Variable declarations
- **var**
  - allows redefinition and updating
  - variables are hoisted to the top of their schope and initialized as undefined
  - scope is global when declared outside of a function and it's function wide when declared inside a function
- **let**: <em>preferred</em>
  - does not allow redefinition but does allow updating
  - variables are hoisted to the top but are not initialized
  - block scoped
- **const**
  - does not allow redefinition or updating, but the properties of the object can be updated
  - variables are hoisted to the top, but not initialized
  - block scoped
  
### Arrays
- To reverse: ```arr.reverse```
- Convert to string w/o commas: ```arr.join('')```
- Convert to string w/ commas: ```arr.toString()```
- Add to an array with ```push()``` and ```unshift()```
  - unshift adds to the beginning
  - push adds to the end
- Remove items from an array with ```pop()``` and ```shift()```
  - pop removes from the end
  - shift removes from the front
  - both return removed value
- To remove more than one item at once, use ```splice()```
  - First param is the index to start removing items
  - Second param is the number of items to remove
  ~~~javascript
  let array = ['today', 'was', 'not', 'so', 'great'];
  array.splice(2, 2); 
  //array = ['today', 'was', 'great']
  ~~~
- To remove and replace an item with one or more items, also use ```splice()```
  - The first two params are the same as the one above
  - The other params are the items to replace the removed item
  ~~~javascript
  let numbers = [10, 11, 12, 12, 15];
  const startIndex = 3;
  const amountToDelete = 1;

  numbers.splice(startIndex, amountToDelete, 13, 14);
  //numbers = [ 10, 11, 12, 13, 14, 15 ]
  ~~~
- To add one or more items at a specific index, also use ```splice()```
  ~~~javascript
  arr.splice(index, 0, item);
  //explanation:
  inserts "item" at the specified "index",
  deleting 0 other items before it
  ~~~
- To copy part of an array, use ```.slice(ind1, ind2)```
  - Ind1 is the starting index
  - Ind2 is the exclusive ending index
- To copy a full array, use the spread operator ```...```
  - You can also combine arrays using it
  ~~~javascript
  let thisArray = ['sage', 'rosemary'];

  let thatArray = ['cilantro', ...thisArray, 'coriander'];
  ~~~
- The spread operator does a deep copy when the array is 1D. For multidimensional arrays use this:
  ~~~javascript
  JSON.parse(JSON.stringify(array))
  ~~~
- Use ```.indexOf(element)``` to get the index of something in the array.
  - Returns -1 if element is not in array.
- Sort array using the ```.sort()``` method:
  ~~~javascript
  numArray.sort((a, b) => a - b); // For ascending sort
  numArray.sort((a, b) => b - a); // For descending sort
  ~~~
### Key-Value Objects
~~~javascript
let foods = {
  apples: 25,
  oranges: 32,
  plums: 28
  data: {
    popularity: 15
    total: 25
  }
};
~~~
- Adding new elements:
  ~~~javascript
  foods.origin = 'Dirt';
  foods['origin'] = 'Dirt';
  ~~~
- Nested elements: ```foods.data.popularity = 1```
- To remove elements, use delete: ```delete foods.data```
- To check if an object has a certain property
  ~~~javascript
  foods.hasOwnProperty('plums');
  'plums' in foods;
  ~~~
- Retrieving elements in for...in loop:
  ~~~javascript
  for (let user in users) {
    if (users[user]['online']) {
      count += 1;
    }
  }
  ~~~
- Get list of keys: ```Object.keys(obj)```
- Turning it into a list:
  ~~~javascript
  var dict = {
    "key1" : 100,
    "key2" : 200,
    "key3" : 300
  }

  var data = Object.entries(dict).map(([key, value]) => ([key, value]))
  ~~~
- These types of objects can contain functions:
  ~~~javascript
  let duck = {
    name: "Aflac",
    numLegs: 2,
    sayName: function() {return "The name of this duck is " + this.name + ".";}
  };
  duck.sayName();
  ~~~
### Strings
- ```charAt(index)```	returns the character at the specified index
- ```concat()```	joins two or more strings
- ```replace()```	replaces a string with another string
- ```split('')```	converts the string to an array of strings
- ```substr(start, length)```	returns a part of a string
- ```substring(start,end)```	returns a part of a string
- ```slice(start, end)```	returns a part of a string
- ```toLowerCase()```	returns the passed string in lower case
- ```toUpperCase()```	returns the passed string in upper case
- ```trim()```	removes starting and trailing whitespace from the strings
- ```includes()```	searches for a string and returns a boolean value
- ```search()```	searches for a string and returns a position of a match
### Sets
- Contain no duplicate values.
- Make a new set from list with ```new Set(list)```
- Use ```.add(val)``` to add a new value.
- Use ```.has(val)``` to check if val is in the set.
- Remove everything from the set with ```.clear()```
- Remove an element with ```.delete(el)```
- Use ```.size``` to check out how big the set is.
- Convert to an array with ```Array.from(myset)```
- Iterating through it:
  ~~~javascript
  // iterate over items in set
  // all log the elements in insertion order
  for (const item of mySet1) {
    console.log(item);
  }

  for (const item of mySet1.keys()) {
    console.log(item);
  }

  for (const item of mySet1.values()) {
    console.log(item);
  }

  for (const [key, value] of mySet1.entries()) {
    console.log(key);
  }
  ~~~
### OOP
- Constructors create new objects
  ~~~javascript
  function Dog() {
    this.name = "Albert";
    this.color = "blue";
    this.numLegs = 2;
  }
  let newDog = new Dog();
  newDog.name = "Pince" //not a typo
  ~~~
  - They are defined with a capitalized name and use the <strong>this</strong> keyword.
  - They define properties and behaviors instead of returning a value
  - Can add arguments
- To see if an object is an instance of a constructor, use this format: ```obj instanceof Dog```
  - Can also use ```===``` like this: ``` beagle.constructor === Dog ```
    - The constructor property can be overwritten so it's generally better to use instanceof.
- Add all properties of an object to an array:
  ~~~javascript
  let canary = new Bird("Tweety");
  let ownProps = [];

  for (let prop in canary) {
    if (canary.hasOwnProperty(prop)) {
      ownProps.push(prop)
    }
  }
  ~~~
- Make a prototype of an object to reduce duplicate variables. Creates a shared variable among all instances.
  - All instances automatically have the properties of the prototype
  ~~~javascript
  function Dog(name) {
    this.name = name;
  }
  Dog.prototype.numLegs = 2;
  ~~~
- Own properties vs Prototype properties:
  - Own properties are instance dependent
    - Defined directly on the object instance
  - Prototype properties are not instance dependent
    - Defined on the object prototype
- To add protype properties and own properties to their own arrays:
  ~~~javascript
  let ownProps = [];
  let prototypeProps = [];

  for (let property in duck) {
    if(duck.hasOwnProperty(property)) {
      ownProps.push(property);
    } else {
      prototypeProps.push(property);
    }
  }
  ~~~
- You can set a prototype to have multiple properties at a time
  ~~~javascript
  function Bird(name) {
    this.name = name;
  }

  Bird.prototype = {
    numLegs: 2, 
    constructor: Bird, //IMPORTANT
    eat: function() {
      console.log("nom nom nom");
    },
    describe: function() {
      console.log("My name is " + this.name);
    }
  };
  let duck = new Bird("Canary")
  ~~~
- An object inherits its prototype directly from the constructor function that created it. 
  - In the code above, duck inherits its prototype from the bird constructor. This relationship can be shown with:
    ~~~javascript
    Bird.prototype.isPrototypeOf(duck);
    ~~~
- A prototype can have a prototype. The prototype of ```Bird.prototype``` is ```Object.prototype```. It inherits functions like ```.hasOwnProperty``` and whatever from ```Object.prototype```.
  - Object is a supertype for all objects. 'Bird' would be a subtype of object, but a supertype of 'duck'.
##### <em>Inheritance </em>
- To make an inheritance relation, use Object.create(something.prototype)
  ~~~javascript
  let animal = Object.create(Animal.prototype);
  animal instanceof Animal; //true
  ~~~
  - Creates a new object and sets obj as the new objects prototype.
- To make a prototype inherit from another prototype:
  ~~~javascript
  let Bird.prototype = Object.create(Animal.prototype);
  ~~~
- The above example would also change the Bird's constructor to Animal.
  - To change it back: 
  ~~~javascript
  Bird.prototype.constructor = Bird;
  ~~~
- Add new methods after inheritance the normal way:
  ~~~javascript
  Bird.prototype.fly = function() {
    console.log("I'm flying!");
  };
  ~~~
- You can override an inherited function by defining it again as if you were adding a new method like above.
- To add a common behavior between unrelated objects, use a **mixin**.
  ~~~javascript
  //Take any object and give it a fly method
  let flyMixin = function(obj) {
    obj.fly = function() {
      console.log("Flying, wooosh!");
    }
  };
  flyMixin(air_plane);
  ~~~
- An **IIFE** (Immediately invoked function expression) is a function that is executed right after being declared. 
  ~~~javascript
  (function () { console.log("Chirp, chirp!"); })();
  ~~~
  - Also called an anonymous function expression.
- An IIFE is often used to group related functionality into a single object. We can group multiple mixins together to form one object
  ~~~javascript
  function glideMixin(obj) {
    obj.glide = function() {
      console.log("Gliding on the water");
    };
  }
  function flyMixin(obj) {
    obj.fly = function() {
      console.log("Flying, wooosh!");
    };
  }
  
  //group them together
  let motionModule = (function () {
    return {
      glideMixin: function(obj) {
        obj.glide = function() {
          console.log("Gliding on the water");
        };
      },
      flyMixin: function(obj) {
        obj.fly = function() {
          console.log("Flying, wooosh!");
        };
      }
    }
  })();

  motionModule.glideMixin(duck);
  duck.glide();
  ~~~
##### <em>Encapsulation</em>
- Make a variable private by creating avariable within the constructor function.
  ~~~javascript
  function Bird() {
    let hatchedEgg = 10; //private
    this.name = "Blue Jay"; //public

    this.getHatchedEggCount = function() { 
      return hatchedEgg;
    };
  }
  ~~~
  - The ```getHatchedEggCount``` method is called a **priviledged** method since it has access to a private variable.
    - In JavaScript, a function always has access to the context in which it was created. This is called **closure**.

### Functional Programming

- An **IIFE** (Immediately invoked function expression) is a function that is executed right after being declared. 
  ~~~javascript
  (function () { console.log("Chirp, chirp!"); })();
  ~~~
  - Also called an anonymous function expression.

