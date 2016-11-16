# IndexOf

### Immutable Docs:
Returns the first index at which a given value can be found in the Iterable, or -1 if it is not present.
```typescript
  indexOf(searchValue: T): number
```

### Human Docs

The method `indexOf` it's similar a the native `Array.indexOf`, in immutable we use single reference for each object created, this give us the power to compare objects like `Map == AnotherMap`, so you can pass an object into indexOf and they will locate the index for you :)

```javascript
  // Method Signature
  // @param (value) : (Object) - Anything that you want locate in list
  const index = list.indexOf(value)
  
  //Return
  if (index > -1) return "Are In list"
  else return "Aren't In List"
```

**TIP** In many cases you won't have the object, so you can use [findIndex](https://github.com/guidiego/immutable-for-humans/blob/master/List/findIndex.md) to findIndex using functions  
**HOT TIP** Records working like Native JS objects, think in replace your objects for Records   
**MOST HOT TIP** A Record Instance can be `extended` and you can implement methods on that    

```javascript
import { List, Record } from 'immutable'

// Create a Record
const ExampleRecords = new Record({ name: '', age: 0 })

// Create 3 Mocks
const mock1 = ExampleRecords({name : 'Guilherme', age: 22})
const mock2 = ExampleRecords({name : 'Charles', age: 28})
const mock3 = ExampleRecords({name : 'Ana', age: 29})

// Create a List with 2 first mocks
const listExample = new List([mock1, mock2])

// See the outputs
console.log(listExample.indexOf(mock1)) // 0
console.log(listExample.indexOf(mock2)) // 1
console.log(listExample.indexOf(mock3)) // -1

```
