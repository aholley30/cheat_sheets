# <p align="center">Javascript Cheat Sheet</p>

### General
- To print with variables: 
  ~~~javascript
  console.log(`printin with a ${var}`);
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
- Mutable
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
  const numbers = [10, 11, 12, 12, 15];
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
- ```trim()```	removes whitespace from the strings
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


