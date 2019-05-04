# Foundations
## Java
- [Primitive types](#primitiveTypes)
  - definition
  - conversion
  - Exceptions
- keywords
  - [assert](#assert)
  - [break](#break)
  - [continue](#continue)
  - [default](#default)
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
- [Enumeration](#enumeration)(#Outer link)
- [Arrays](#arrays)(outer link)
- [String](#String)
- [Access Modifier](#accessModifier)
- [Class](#class)
  - [Abstract class](#abstractClass)
  - [Nested Class](#nestedClass)
    - [static nested class](#staticNC)
    - [non-static nestd class](#nonStaticNC)
    - [local Class](#localClass)
    - [Anonymous class](#AnonymousClass)
- [Abstraction](#abstraction)
  - [Abstract class](#abstractClass)
  - [Interface](#interface)
- [Varargs](#varargs)
- Classes
  - Enum
  - Integer
  - Double
  - Charactor
  - String
  - Arrays
  - Collections
  - JNI
- Exceptions
- [Collections](#collections)
### <div id = "primitiveTypes">primitive types</div>
#### Definition
| Types   | Size(bits) | Range                          | Default Value |
| ------- | ---------- | ------------------------------ | ------------- |
| byte    | 8          | -128~127                       | 0             |
| char    | 8          |                                |               |
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

#### <div id = "finalize">finalize</div>
- `finalize()` method will be called by **garbage collector** to do the **clean-up activity** which means closing the resources associated with the object. In other word, it will be called when the object is going to be deleted/destroyed
- `finalize()` method is in the **Object** class, so every object can override this method
- If the object of the class which has overriden the `finalize()` method has no reference(which can be done by assigning it to `null`), then `finalize()` method will be called by the **garbage collector**.
- `finalize()` can be invoked as a normal method of the object, but it won't ignore the **unchecked exception**, which means abnormal exit.
- When `finalize()` called by the `System.gc()` (but it is up-to the garbage collector), it will igonre the **unchecked exception**. If it has corresponding catch, the exception won't be ignored.

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
- `static` can be used with block, class, method and field.
- **These members belong to the class** instead of any instance. So they are **shared between all instances(objects)**.
- These members are stored inside the **Class Memory(Heap)**. Memory allocation only happens once when the class is loaded.
- To access these, object creation isn't needed. They can be accessed by the class name.
##### static members
- static method
- static class


#### <div id = "strictfp">strictfp</div>
#### <div id = "super">super</div>
- `super` is used to access super class members inside a sub class
#### <div id = "synchronized">synchronized</div>
- `synchronized` is
#### <div id = "this">this</div>
- `this` is used to access other members in the same class
#### <div id ="throw">throw</div>
- `throw` is used to throw the exceptions manually
#### <div id ="throws">throws</div>
- `throws` is used to specify the exceptions which the current method may throw
#### <div id = "translent">translent</div>
- `translent` is used in serialization. A variable which is declared as `translent` will not be eligible for serialization.
#### <div id = "volatile">volatile</div>
- When `volatile` is used, the variable will be read and write from the **main memroy**


### <div id ="accessModifier">Acess Modifiers</div>
- Class can only use public and default
- Class access modifier is has high prority than other access modifier
- Interface access modifier is all default to be public
- SubClass's fields and methods must have equal or high priority than the superclass

| Keyword   | Class | Package | SubClass | External Package |
| --------- | ----- | ------- | -------- | ---------------- |
| public    | can   | can     | can      | can              |
| protected | can   | can     | can      | cannot           |
| default   | can   | can     | cannot   | cannot           |
| private   | can   | cannot  | cannot   | cannot           |
### Class
#### <div id = "initializerBlock">initializer block</div>
- There are two kinds of initializer blocks, one is **static** the other is **normal**
- **Static initializer block** will only be called once when the class is being loaded by the JVM.
- **Normal initializer block** will be called whenever the class is being instantiated. They will be called in order after the static initializer block and before the constructor.
#### <div id = "inheritance">Inheritance</div>
- A class can inherit another class, the first class is the subclass, the second one is superclass
- **Casting** reference a object of class as a different type than the class itself is called type casting
  - **Upcasting** Cast an object of a subclass to one of its superclass.
    ```java
    Car car = new Car();
    Vehicle vehicle = car;
    ```
  - **Downcasting** Cast an object of a superclass to a subclass type.
    ``` java
    Car car = new Car();
    Vehicle vehicle = car;
    Car c = (Car)vehicle;
    ```


#### <div id = "abstractClass">Abstract Class</div>
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
#### <div id ="nestedClass">Nested Class</div>
##### <div id = "staticNC">Static Nested Class</div>
- Static nested class can only use the static variable of the outclass
- **ONLY** static nested class can have static/non-static field, static/non-static method, static/non-static nested class
- Example
  ``` java
  public class OuterClass{
     public static class InnerClass{
        // some statements
     }
  }

  public static void main(String[] args){
    OuterClass.InnerClass innerClass = new OuterClass.InnerClass();
  }
  ```
##### <div id = "nonStaticNC">Non-static Nested Class(Inner class)</div>
- Non-static nested class is the normal inner class
- InnerClass can assess the outerclass's fields, even it is has **private** access modifier.
- **Inner Class Shadowing** If inner class have a field which has the same name as the outer one. They will refer to their own field. If the Inner class wants to access the outer's using the `outer.this.<fieldName>`
- Example
  ```java
  public class OuterClass{
      String text = "I'm in outer";
      public class InnerClass{
          String text = "I'm in inner";
          System.out.println(text); // this will be I'm in inner;
          System.out.println(OuterClass.this.text); // this will be I'm in outer;
      }
  }

  public static void main(String[] args){
      OuterClass outer = new OuterClass();
      OuterClass.InnerClass inner = outer.new InnerClass();
  }
  ```
##### <div id = "localClass">Local classes</div>
- Local class is same as inner class, but it is defined in the method or the block.
- Local class can **only** be accessed from inside the method or block
- Local class can access members of its outer class
- Local class can access the local variables inside the same method or block with `final`
- Example
```java
public void Method(){
   int a = 3;
   class Local{
      public c(){
        a = 4; // compile error, a is final here
        System.out.println(a);
      }
   }

   Local l = new Local();
}
```
##### Anonymous classes
- Anonymous class are nested class without a name. They are typically declared as either subclasses of an existing class or implementations of interface
- An anonymous class can access member of the outerclass with `final`
- In anonymous class **cannot** declare a constructor, but can have a instace initializer instead to initialize.
- Example
```java
public class SuperClass{
  public void doIt(){
     System.out.println("This is super");
  }
}

public interface MyInterface(){
  public void doIt();
}

public static void main(String[] args){
  private String text = "outer field";
  // define a subclass
  SuperClass s = new SuperClass(){
    {
      this.text = text;
    }
    public void doIt(){
       System.out.println("This is sub " + text);
    }
  }
  s.doIt();

  // implements a inteface
  MyInterface i = new MyInterface(){
    @Override
    public void doIt(){
      System.out.println("this is implementation of the interface");
    }
  }
}

```
### <div id = "abstraction">Abstraction</div>
- Abstraction is a process to show only "relevant" data and "hide" unnecessary details.
- Abstraction in Java is implemented by using **Abstract Class** and **Interface**
#### <div id = "abstractClass">abstract class</div>
[Abstract Class](#abstractClass)
#### <div id = "interface">interface</div>
- Interface is just like the class, it can have variables and methods. But the variables are **public, static & final** by default. The methods are **public and abstract** by default.
- The variable must be initialized at the time of declaration.
- Interface cannot be declared as private, protected or translent.
- **All methods** in interfaces must be implemented in the class implements it or the class must be an **abstract class**.
- A class can **inherited only one class** but can **implements more than one interfaces**.
- Class can both extends another class and implements interfaces. But interface can **only extends** interfaces.
- If a class implements an interface which extends another interface, the class must implements **all methods** in both interfaces or be an **abstract class**.
- If a class implements two interface both of which has a method with same name, the class can only implement one.
- The implemented methods must be **public**
- Default method can be a default implementation of a method. User's implementation can override it.
- Interface can have a **static method** and call it as the static method in a class.

### <div id = "varargs">varargs:Variable Arguments</div>
- **Varargs** is used to simplifie the creation of the method which need to take variable number of arguments
- **Varargs** is specified by ...
- **Varargs** can receive 0 or more arguments and then will be stored in the one dimension array.
- A method can only have one **Varargs** with the same type and **varargs** must be the last arguments of the method
- The method with fixed arguments will have high priority to be invoked

### <div id = "collections">Collections</div>

### Storage and Initialize
### Multithreading
### JVM
### Garbage collection
