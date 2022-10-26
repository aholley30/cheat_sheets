# <p align="center">Javascript Cheat Sheet</p>

### General
- To print with variables: 
  ~~~javascript
  console.log(`printin with a ${var}`);
  ~~~
- Using ```typeof variable``` will return a string of the type.
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
### Key-Value Objects
