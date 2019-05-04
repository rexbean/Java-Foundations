# Array
- [Basic](#basic)
- [Implementation](#implementation)
- [Arrays](#arrays)

## <div id = "basic">Basic</div>
- Arrays are all objects. Its direct superclass of an array type is Object
- The class name of the array:
  - The number of `[` means the number of dimensions
  - The type of the array
    - I is integer
    - D is double
    - S is short
    - B is byte
    - Z is boolean
    - L is for the reference type
- Every array type implements interfaces **Cloneable** and **java.io.Serializable**
  - For one dimensional array, `array.clone()` will do the **deep clone** and return a new array.
  - For multiple dimensional array, `array.clone` will only copy the references to each dimension.
## <div id = "implementation">Implementation</div>
- Array includes two parts: **reference**, **values**
  - Reference will be saved in the jvm stack.
  - Values are saved in a continuous memory in the heap.
    - One dimensional array
      - For primitive type, values will be directly stored in the memory
      - For reference type, references to the objects will be stored in the memory and the objects will be stored in the other places in the heap
    - Multiple dimensional array
      - The memory will store the refrences to each dimensional.
## <div id = "arrays">Arrays</div>
- Arrays is a special utility class for manipulating array. It is located in `java.util.Arrays`.
### Copying Arrays
- **Copying one dimensional array** can use `Arrays.copyOf(<source>, <length>)`. This will return a new array with length. `System.arraycopy(<src>, <srcPos>, <dest>, <destPos>, <length>)`
- **Range copying one dimensional array** can use `Arrays.copyOfRange(<source>, <startIndex>, <endIndex(excluded)>)`
### Sorting Array
- Arrays.sort is using **Dual-pivot** quick sort algorithm with **nlog(n)** time complexity on many data sets that cause other quicksorts to degrade to quadratic performance, and is typically faster than traditional (one-pivot) Quicksort implementations.
- **Sorting array of primitive Type** can use `Arrays.sort(<source>)`
- **Sorting array of Object** can use `Arrays.sort(<source>, <Comparator>)`
### Filling Array
- **Filling array** can use `Arrays.fill(<source>, <value>)`
- **Filling range of an array** can use `Arrays.fill(<source>, <startIndex>, <endIndex>, <value>)`
### Searching Array
- **Searching array** can use `Arrays.binarySearch()`.
  - If it has only one -> return index
  - If it has multiple -> return random index
  - If is doesn't have -> -(must be index) - 1
### Equal
- **<array>.equals(<array>)** is used to judge whether they have same address
- **Equal judgment** can use `Arrays.equals()`, must has same value in same order
- **`Arrays.DeepEquals()`** is used to do the deep equal judgment
### Convert array to arrayList
```java
@SafeVarargs
public static <T> List<T> asList(T... a) {
    return new ArrayList<>(a);
}
```
- `asList()` will return an ArrayList with fixed length. It means it cannot do the `add()` or `remove()` operations. Eventually, the list will convert to an array
- Argument can be an one dimensional array and the formal argument will be a two dimensional array with one dimension
### To String
- **`toString()`** for one dimensional array, it will return the array, while for mulitple dimensional array, it will return addresses.
- **`DeepToString()`** can return the multiple dimensional array
