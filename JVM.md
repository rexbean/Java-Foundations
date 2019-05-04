# JVM
- Execution engine
  - Interpreter vs JIT compiler
    - First thing first:
With JVM, both interpreter and compiler (the JVM compiler and not the source-code compiler like javac) produce native code (aka Machine language code for the underlying physical CPU like x86) from byte code.

What's the difference then:
The difference is in how they generate the native code, how optimized it is as well how costly the optimization is. Informally, an interpreter pretty much converts each byte-code instruction to corresponding native instruction by looking up a predefined JVM-instruction to machine instruction mapping (see below pic). Interestingly, a further speedup in execution can be achieved, if we take a section of byte-code and convert it into machine code - because considering a whole logical section often provides rooms for optimization as opposed to converting (interpreting) each line in isolation (to machine instruction). This very act of converting a section of byte-code into (presumably optimized) machine instruction is called compiling (in the current context). When the compilation is done at run-time, the compiler is called JIT compiler.

enter image description here

The co-relation and co-ordination:
Since Java designer went for (hardware & OS) portability, they had chosen interpreter architecture (as opposed to c style compiling, assembling, and linking). However, in order to achieve more speed up, a compiler is also optionally added to a JVM. Nonetheless, as a program goes on being interpreted (and executed in physical CPU) "hotspot"s are detected by JVM and statistics are generated. Consequently, using statistics from interpreter, those sections become candidate for compilation (optimized native code). It is in fact done on-the-fly (thus JIT compiler) and the compiled machine instructions are used subsequently (rather than being interpreted). In a natural way, JVM also caches such compiled pieces of code.

Words of caution:
These are pretty much the fundamental concepts. If an actual implementer of JVM, does it a bit different way, don't get surprised. So could be the case for VM's in other languages.

Words of caution:
Statements like "interpreter executes byte code in virtual processor", "interpreter executes byte code directly", etc. are all correct as long as you understand that in the end there is a set of machine instructions that have to run in a physical hardware.

Some Good References: [I've not done extensive search though]

[paper] Instruction Folding in a Hardware-Translation Based Java Virtual Machine by Hitoshi Oi
[book] Computer organization and design, 4th ed, D. A. Patterson. (see Fig 2.23)
[web-article] JVM performance optimization, Part 2: Compilers, by Eva Andreasson (JavaWorld)
PS: I've used following terms interchangebly - 'native code', 'machine language code', 'machine instructions', etc.
  - https://www.geeksforgeeks.org/jvm-works-jvm-architecture/
  - https://www.cnblogs.com/insistence/p/5901457.html
  - https://www.cubrid.org/blog/understanding-jvm-internals
