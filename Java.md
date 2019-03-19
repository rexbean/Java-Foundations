# Foundations
## Java
- [Primitive types](#primitiveTypes)
  - definition
  - conversion
  - Exceptions
- keywords
  - [abstract](#abstract)
  - [assert](#assert)
  - [break](#break)
  - [class](#class)
  - [continue](#continue)
  - [default](#default)
  - [enum](#enum)
  - [extends](#extends)
  - [**final**](#final)
  - [implements](#implements)
  - [import](#import)
  - [instanceOf](#instanceOf)
  - [interface](#interface)
  - [native](#native)
  - [new](#new)
  - [package](#package)
  - [return](#return)
  - [**static**](#static)
  - [strictfp](#strictfp)
  - [super](#super)
  - [synchronized](#synchronized)
  - [this](#this)
  - [**throw**](#throw)
  - [**throws**](#throws)
  - [translent](#translent)
  - [volatile](#volatile)
- Classes
  - Enum
  - Integer
  - Double
  - Charactor
  - String
  - Arrays
  - Collections
  - JNI
### <div id = "primitievTypes">primitive types</div>
#### Definition
| Types   | Size(bits) | Range                          | Default Value |
| ------- | ---------- | ------------------------------ | ------------- |
| byte    | 8          | -128~127                       | 0             |
| short   | 16         | -2^15 ~ 2^15-1                 | 0             |
| int     | 32         | -2^31 ~ 2^31-1                 | 0             |
| long    | 64         | -2^63~ 2^63 -1                 | 0             |
| float   | 32         | 2^-149 ~ (2 - 2^(-23))*2^127   | 0             |
| double  | 64         | 2^-1074 ~ (2 - 2^(-52)*2^1023) | 0             |
| boolean |            |                                | false         |
| void    |            |                                |               |
#### conversion
- From low to equal or high, it isn't necessary to use type casting.
- From high to low it should use type casting.
- Boolean cannot do type casting to any type else.
#### Exceptions
- **ArithmeticException: / by zero**
  - this is only for Integer
  - Floating-point / 0 = Infinity
  - Floating-point / Infinity = 0
### keywords
#### <div id = "abstract">abstract</div>
- Abstraction in Java is implemented by using **Abstract Class** and **Interface**
- Abstract means imcompleted. It can be **abstract class** and **abstract method**.
- Abstract class **may or may not** have abstract methods.
- **ANY** abstract class **cannot be instantiated**, it can only **be inherited**.
- **Concrete object can be auto-upcasted to Abstract Class**
- Abstract class can be a combination of concrete and abstract methos.
- Abstract method **may or may not** be implemented in the sub-class. If not all abstract methods are implemented, the sub-class should still be **abstract**.
- Abstract method **cannot be private**.
- Abstract method **cannot be static**
- Abstract method **cannot be final**
- Fields and contstructor **cannot be abstract**
- Example
  ``` java
  abstract class AbstractClass{
     AbstractClass(){
         // first constructor
     }
     AbstractClass(int i){
         // second constructor
     }

     abstract void abstractMethod();

     void concreteMethod(){
        // concrete method
     }
  }

  public class ConcreteClass extends AbstractClass{
      void abstractMethod(){
         // implemented abstract method
      }
  }

  public class Main{
     public static void main(String[] args){
        ConcreteClass c = new ConcreteClass();

        AbstractClass a = c; // auto-upcasted
     }
  }
  ```
#### <div id = "assert">assert<div>
- `assert` is used in the **Assert statement**.
- ***Assert Statement*** is used to **detect and correct** the programming errors.
- ***Assert statement*** takes **boolean expression** as input and assume it will return true. If it return false, it will **throw AssertionError**
- Example
  ``` java
    Scanner sc = new Scanner(System.in);
    int temp = sc.nextInt();
    assert temp > 35 : "FAIL"
  ```
#### <div id = "break">break</div>
- `break` is used to stop the execution of a statement(for, while, switch-case) according to some condition
#### <div id = "continue">continue</div>
- `continue` is used to stop current iteration and start the next iteration in loop.
#### <div id = "class">class</div>
- `class` is used to define a class in Java
#### <div id = "default">default</div>
- From **Java 8**, `default` is used to define the default methods in an interface
- `default` is also used in switch-case statement.
#### <div id = "enum">enum</div>
- `enum` is used to define a Enum types
#### <div id = "extends"> extends</div>
- `extends` is used in inheritance.
#### <div id = "final">final</div>
`final` keywords restrict the furthre modification. When a final keyword is used, it means that entity is complete and can not be modified further.
- **`final` for class**  This class cannot be inherited, fields are not necessary to be final, but **methods are default final**.
- **`final` for method** This method cannot be overridden, but can be overloaded.
- **`final` for parameter** The primitive types's value cannot be changed in the method, but reference's field can be changed.
- **`final` for field**
  Final fields won't get default value, it must get the value at the time of object creation.
  - **For primitive type variable** The field's value can only be initialized once.
  - **For array** The array cannot be re-assgined, but the elements can
  - **For reference variable** The variable can be re-assgined a new object. But it's state can be changed.
- `final` and `static`

#### <div id = "implements">implements</div>
- `implements` is used while implements an interface.
#### <div id = "import">import</div>
- **Normal import** If a class in another packages is wanted, an **import statement** can help, like `import pack1.*`;
- **Static import** If a variable or method is **static**, then it can be imported by **static import** and used directly.
  ```java
  package pack1;
  class A {
      public static int i;
      public static int methodOne(){
          return i;
      }
  }

  package pack2;
  import static pack1.A.*;
  class B{
      System.out.println(methodOne());
  }
  ```
#### <div id="instanceOf">instanceOf</div>
- `instanceOf` is used to check whther an object is an instance of a Class
#### <div id = "interface">interface</div>
- `interface` is uesd to define the interfaces in java
#### <div id = "native">native</div>
- `native` is used with a method to indicate that a particular method is implemented in native code using Java Native Interface(JNI)
#### <div id = "new">new</div>
- `new` is used to instantiate a new object
#### <div id = "package">package</div>
- `package` is used to specify the package which the current file belongs to.
#### <div id = "return">return</div>
- `return` is used to  return the control back to the caller with the result.
#### <div id = "static">static</div>
-


#### <div id = "strictfp">strictfp</div>
#### <div id = "super">super</div>
- `super` is used to access super class members inside a sub class
#### <div id = "synchronized">synchronized</div>
- `synchronized` is
#### <div id = "this">this</div>
- `this` is used to access other members in the same class
#### <div id ="throw">throw</div>
#### <div id ="throws">throws</div>
#### <div id = "translent">translent</div>
- `translent` is used in serialization. A variable which is declared as `translent` will not be eligible for serialization.
#### <div id = "volatile">volatile</div>
- When `volatile` is used, the variable will be read and write from the **main memroy**
### 可见域
### Sets
### Storage and Initialize
### Multithreading
### JVM
### Garbage collection
