## List

### Immutable Docs
Lists are ordered indexed dense collections, much like a JavaScript Array.
class List<T> extends Collection.Indexed<T>

####DISCUSSION

Lists are immutable and fully persistent with `O(log32 N)` gets and sets, and O(1) push and pop.

Lists implement Deque, with efficient addition and removal from both the end (`push`, `pop`) and beginning (`unshift`, `shift`).

Unlike a JavaScript Array, there is no distinction between an "unset" index and an index set to undefined. List#forEach visits all indices from 0 to size, regardless of whether they were explicitly defined.

####Construction

**List()**  
Create a new immutable List containing the values of the provided iterable-like.  

```typescript
List<T>(): List<T>
List<T>(iter: Iterable.Indexed<T>): List<T>
List<T>(iter: Iterable.Set<T>): List<T>
List<K, V>(iter: Iterable.Keyed<K, V>): List<any>
List<T>(array: Array<T>): List<T>
List<T>(iterator: Iterator<T>): List<T>
List<T>(iterable: Object): List<T>
```

### Human Docs

An Immutable list it's something like a Array `[]`, if you use `.toJS()` at the end of a `List` instance they will return a native Javascript Array. 

Lists are more efficiente because they work with another data sctructure that permit find things and insert another faster than traditional JS array

####Construction
You can called with a simple `new List()` and pass: An another `List Instance`, any `Immutable Interator`, or a native javascript Array

```javascript
import { List, Interable } from 'immutable'

const listFromArraY = List([1,2])

console.log(listFromArraY.toJS()) // [1,2]

const listFromList = List(listFromArraY)

console.log(listFromList.toJS()) // [1,2]

```
