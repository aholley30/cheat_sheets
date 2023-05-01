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
- Use ```continue``` to skip an iteration in a loop and ```break``` to exit a loop early.
- Ternary expressions:
  ~~~javascript
  condition ? doThisIfTrue : doThisIfFalse

  1 > 2 ? console.log(true) : console.log(false)
  // returns false

  //only if
  condition && doThing
  ~~~
- Exponentiation can be achieved with ```num ** exp``` or ```Math.pow(num, exp)```
- Try - Catch - Finally:
  ~~~javascript
  try {
    // try_statements
  } 
  catch(error) {
      console.error(error.message) // catch_statements  
  }
  finally() {
      // codes that gets executed anyway
  }
  ~~~
- ```of``` vs ```in``` while looping: In prints default values while of does not.
  ~~~javascript
  const car = {
    engine: true,
    steering: true,
    speed: 'slow'
  }
  const sportsCar = Object.create(car);
  sportsCar.speed = 'fast';

  for (prop in sportsCar) {
    console.log(prop) //speed engine steering
  }

  for (prop of Object.keys(sportsCar)) {
    console.log(prop) //speed
  }
  ~~~
### Variable declarations
- **var**
  - allows redefinition and updating
  - variables are hoisted to the top of their scope and initialized as undefined
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
- Add to an array with ```push()``` and ```unshift()``` - these are inplace
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
  array = JSON.parse(JSON.stringify(array))
  ~~~
- To concatenate 2 arrays use ```.concat()``` it returns a new array.
  - Format is ```arr1.concat(arr2)```
- Use ```.indexOf(element)``` to get the index of something in the array.
  - Returns -1 if element is not in array.
- Sort array using the ```.sort()``` method:
  ~~~javascript
  numArray.sort((a, b) => a - b); // For ascending sort
  numArray.sort((a, b) => b - a); // For descending sort
  arr.sort(function(a, b) {       // alphabetical order
    return a === b ? 0 : a < b ? -1 : 1;
  });
  ~~~
- For Each iterator:
  ~~~javascript
  const avengers = ['thor', 'captain america', 'hulk'];
  avengers.forEach((item, index)=>{
	  console.log(index, item)
  })
  ~~~
### Dictionary Objects
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
  - can also take regex delimeters. for example ```/\d/``` would split by digits.
- ```substr(start, length)```	returns a part of a string
- ```substring(start,end)```	returns a part of a string
- ```slice(start, end)```	returns a part of a string
- ```toLowerCase()```	returns the passed string in lower case
- ```toUpperCase()```	returns the passed string in upper case
- ```trim()```	removes starting and trailing whitespace from the strings
- ```includes()```	searches for a string and returns a boolean value
- ```search()```	searches for a string and returns a position of a match
- ```parseInt(str)``` to convert to integer
- ```parseFloat(str)``` to convert to float
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
### Javascript objects/structs
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
### Classes & OOP
Principles of OOP:
1. Encapsulation: wraps related data and code into a single entity
   - Can use functions without knowing how they work.
2. Abstraction: Only shows or allows access to essential items in an entity.
   - Achieved by using access modifiers
3. Polymorphism: Using a single function that behaves differently based on context.
   - Achieved by function overloading and overriding.
4. Inheritance
~~~javascript
class Car {
  constructor(color, speed) {
    this.color = color;
    this.speed = speed;
  }

  drive(direction) {
    console.log("we are driving " + direction )
  }
}

const car1 = new Car("red", 120);

class rollsroyce extends Car {
  constructor(color, speed, year=1977){
    super(color, speed);
    this.year = year;
  }

  drive(direction) {
    super.drive(direction);
    console.log(' in style')
  }
}

~~~
### Functional Programming
A style of programming where solutions are simple, isolated functions, without any side effects outside of the function scope.

- **Terminology**:
  - <u>*Pure functions*</u> always returns the same result if the same arguments are passed. It does not depend on any state or data change during a program's execution.
  - <u>*Callbacks*</u> are the functions that are slipped or passed into another function.
  - <u>*First class functions*</u> can be assigned to a variable, passed into another function, or returned from another function just like any other normal value.
  - <u>*Higher order functions*</u> take a function as an argument, or return a function as a return value.
  - <u>*Lambda functions*</u> are passed in to other functions as arguments or returned from other functions.
  - <u>*IIFE*</u> (Immediately invoked function expression) is a function that is executed right after being declared. 
    ~~~javascript
    (function () { console.log("Chirp, chirp!"); })();
    ~~~
    - Also called an anonymous function expression.
- **Principles**:
  1) Don't alter a variable or object - create new variables and objects and return them if need be from a function. 
      - Using something like ```const newArr = arrVar```, where ```arrVar``` is an array will simply create a reference to the existing variable and not a copy. So changing a value in ```newArr``` would change the value in ```arrVar```.
  2) Declare function parameters - any computation inside a function depends only on the arguments passed to the function, and not on any global object or variable.
- **Methods**:
   
   - ```Array.prototype.map()``` or more simply, ```map```, iterates over each item in an array and returns a new array containing the results of calling the callback function on each element.
      ~~~javascript
    
      const posts = [
        { id: 1, title: "Sample Title 1", description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit..." },
        { id: 2, title: "Sample Title 2", description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit..." },
        { id: 3, title: "Sample Title 3", description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit..." },
      ];
      // ES2016+
      // Create new array of post IDs. I.e. [1,2,3]
      const postIds = posts.map((post) => post.id);
      // Create new array of post objects. I.e. [{ id: 1, title: "Sample Title 1" }]
      const postSummaries = posts.map((post) => ({ id: post.id, title: post.title }));
      ~~~
    - ```Array.prototype.filter()``` or more simply, ```filter()``` calls a function on each element and returns a new array containing only the elements for which the function returns true.
      ~~~javascript
      const users = [
        { name: 'John', age: 34 },
        { name: 'Amy', age: 20 },
        { name: 'camperCat', age: 10 }
      ];

      const usersUnder30 = users.filter(user => user.age < 30);
      console.log(usersUnder30); 
      ~~~
      - Can accept 3 arguments: the current element being processed, the index of that element, the array. The example above only uses the first argument.
    - ```Array.prototype.reduce()``` or simply ```reduce()```, iterates over each item in an array and returns a single value using a callback function.
      - The callback func can take 4 args. 
          1) The first is the accumulator, which gets assigned the return value of the callback function from the previous iteration. 
          2) The second is the current element being processed. 
          3) The third is the index of that element. 
          4) The fourth is the array upon which reduce is called.
      - ```reduce``` has another param that can take an initial value for the accumulator. If the second parameter is not used, then the first iteration is skipped and the second iteration gets passed the first element of the array as the accumulator.
        ~~~javascript
        const users = [
          { name: 'John', age: 34 },
          { name: 'Amy', age: 20 },
          { name: 'camperCat', age: 10 }
        ];

        const sumOfAges = users.reduce((sum, user) => sum + user.age, 0);
        console.log(sumOfAges); //64

        const usersObj = users.reduce((obj, user) => {
          obj[user.name] = user.age;
          return obj;
        }, {});
        console.log(usersObj); //{ John: 34, Amy: 20, camperCat: 10 }
        ~~~
    - The ```every()``` method returns true if every element in an array meets a certain criteria.
      ~~~javascript
      const numbers = [1, 5, 8, 0, 10, 11];

      numbers.every(function(currentValue) {
        return currentValue < 10;
      }); //false
      ~~~
    - The ```some()``` method returns true if any element in an array meets a certain criteria.
      ~~~javascript
      const numbers = [1, 5, 8, 0, 10, 11];

      numbers.some(function(currentValue) {
        return currentValue < 10;
      }); //true
      ~~~
    - The <u>*arity*</u> of a function is the number of arguments it requires. <u>*Currying*</u> a function means to convert a function of N arity into N functions of arity 1.
      ~~~javascript
      function unCurried(x, y) {
        return x + y;
      }

      function curried(x) {
        return function(y) {
          return x + y;
        }
      }

      const curried = x => y => x + y

      curried(1)(2)
      ~~~
      - A <u>*partial application*</u> can be described as applying a few arguments to a function at a time and returning another function that is applied to more arguments. 
        ~~~javascript
        function impartial(x, y, z) {
          return x + y + z;
        }

        const partialFn = impartial.bind(this, 1, 2);
        partialFn(10); // 13
        ~~~

  

