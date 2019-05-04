# String
[Basic](#basic)
[Implementation](#Implementation)
[methods](#methods)
[String vs StringBuilder vs StringBuffer](#Comparasion)
## Basic
- String is an immutable object which means it can not be changed once it has been created.
- Creation: **literal** and **new keyword**
  - **Using literal**
    ```java
    String str1 = "this is a string";
    ```
  - **Using new keyword**
    ```java
    String str2 = new String("this is a string");
    ```
  - Difference ***(Here should have knowledge about string pool in JVM)*** :
    - When string is created by **literal**, then the string will be created into the string pool directly.
    - When string is created by **new keyword**, then the string will be created into the heap.
    - Before Java 7, the

## <div id = "comparasion">String vs StringBuilder vs StringBuffer</div>
- https://www.journaldev.com/538/string-vs-stringbuffer-vs-stringbuilder
