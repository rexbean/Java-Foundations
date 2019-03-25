# Array
- [Basic](#basic)
- [Implementation](#implementation)
- [Arrays](#arrays)

## <div id = "basic">Basic</div>
## <div id = "implementation">Implementation</div>
- Arrays are all objects. Its direct superclass of an array type is Object
- Array in java is dynamically allocated.
- Array includes two parts
  - reference
  - values
- Reference will be saved in the jvm stack.
- Values are saved in a continuous memory in the heap.
  - Primitive type value will store in the memory
  - Multiple dimensional array will store the refrence to the other one demensional array in memory.
  - Reference type will store in the other place in heap)
- For one demensional array, it will deep clone a new array. But for multiple demensional array, it will only copy the references.
## <div id = "arrays">Arrays</div>
- Arrays is a special utility class for manipulating array. It is located in `java.util.Arrays`.
#### Copying Arrays
- **Copying one demensional array** can use `Arrays.copyOf(<source>, <length>)`. This will return a new array with length. `System.arraycopy(<src>, <srcPos>, <dest>, <destPos>, <length>)`
- **Range copying one demensional array** can use `Arrays.copyOfRange(<source>, <startIndex>, <endIndex(excluded)>)`
#### Sorting Array
- Arrays.sort is using quick sort algorithm with nlog(n) time complexity
- **Sorting array of primitive Type** can use `Arrays.sort(<source>)`
- **Sorting array of Object** can use `Arrays.sort(<source>, <Comparator>)`
#### Filling Array
- **Filling array** can use `Arrays.fill(<source>, <value>)`
- **Filling range of an array** can use `Arrays.fill(<source>, <startIndex>, <endIndex>, <value>)`
#### Searching Array
- **Searching array** can use `Arrays.binarySearch()`.
  - If it has only one -> return index
  - If it has multiple -> return random index
  - If is doesn't have -> -(must be index) - 1
#### Equal
- **Equal judgment** can use `Arrays.equals()`, must has same value in same order
