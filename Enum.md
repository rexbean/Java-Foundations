# Enum
- A special java type used to define collections of constants. It can contains constants, fields, methods.
```java
// a basic enum with only constants
public enum Level{
  // Constans
  HIGH,
  MEDIUM,
  LOW
}
```
## Iteration
```java
public static void main(String[]){
  for(Level l: Level.values()){
     System.out.println(l.getCode());
  }
}
```
## Field
- Enum can be added field to each constants, but it should add a contructor. The field and cosntructor should be private.
``` java
// a Enum with Fields
public enum Level{
   //Constants with fields
   HIGH(3),
   MEIDUM(2),
   LOW(1)
   ;

   private final int code;
   private Level(int code){
     this.code = code;
   }
}
```
## Method
- Methods can also be added. The method can used to return the fields or even do some calculation on it.
- **Abstract methods** can also be added, but each instance should have a implementation.
``` java
public enum Level{
    HIGH(3),
    MEDIUM(2),
    LOW(1)
    ;

    private final int code;
    privat Level(int code){
       this.code = code;
    }
}
// abstract method
public enum Level{
  HIGH(3){
    @Override
    public String toString(){
        return "high";
    }
  },
  MEDIUM(2){
    @Override
    public String toString(){
        return "medium";
    }
  },
  LOW(1){
    @Override
    public String toString(){
        return "low";
    }
  };

  private final int code;
  private Level(int code){
    this.code = code;
  }

  public int getCode(){
    return this.code;
  }
  public abstract String toString();
}
```
## Enum Set
- `EnumSet` is a specail set which can hold Enum.
```java
EnumSet<Level> enumSet = new EnumSet.of(Level.HIGH, Level.LOW);
```

## Enum Map
- `EnumMap` is a map which can let Enum be a key.
```java
EnumMap<Level, String> enumMap = new EnumMap<>(Level.class);
enumMap.put(Enum.HIGH, "hihg");

String level = enumMap.get(Enum.HIGH);
```
