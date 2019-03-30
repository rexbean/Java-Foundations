# synchronized
- Instance methods
- Static methods
- Code blocks inside instance methods
- code blocks inside static methods
## Instance methods
- A synchronized instance method in Java is synchronized on the instance (object) owning the method. Thus, each instance has its synchronized methods synchronized on a different object: the owning instance. Only one thread can execute inside a synchronized instance method. If more than one instance exist, then one thread at a time can execute inside a synchronized instance method per instance. One thread per instance.
