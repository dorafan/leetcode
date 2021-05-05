#### **Question: What are the features of Java?**

**Answer**: Following are the various features of the Java programming language:

- High Performance– Using a JIT (Just-In-Time) compiler allows high performance in Java. The JIT compiler converts the Java bytecode into machine language code, which then gets executed by the JVM.
- Multi-threading– A thread is a flow of execution. The JVM creates a thread which is called the main thread. Java allows the creation of several threads using either extending the thread class or implementing the Runnable interface.
- OOPS Concepts– Java follows [various OOPS concepts](https://hackr.io/blog/object-oriented-programming-oops-concepts-in-java-with-examples), namely abstraction, encapsulation, inheritance, object-oriented, and polymorphism
- Platform Independency– Java makes use of the Java Virtual Machine or JVM, which allows a single Java program to operate on multiple platforms without any modifications.

You may want to check out Java features in detail [here](https://hackr.io/blog/features-of-java). 

#### **Question: How does Java enable high performance?**

**Answer:** In the Just-in-Time compilation, the required code is executed at run time. Typically, it involves translating bytecode into machine code and then executing it directly. For enabling high performance, Java can make use of the Just-In-Time compilation. The JIT compiler is enabled by default in Java and gets activated as soon as a method is called. It then compiles the bytecode of the Java method into native machine code. After that, the JVM calls the compiled code directly instead of interpreting it. This grants a performance boost.

#### **Question: Differentiate between JVM, JRE, and JDK**

**Answer:** 

| **Parameters**     | **JVM**                                                     | **JRE**                                                      | **JDK**                                                      |
| ------------------ | ----------------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **Full-Form**      | Java Virtual Machine                                        | Java Runtime Environment                                     | Java Development Kit                                         |
| **Purpose**        | It provides a runtime environment to execute Java bytecode. | It is a set of software tools used for developing Java applications. | It is a software development environment used to develop Java applications. |
| **Existence**      | It is a runtime instance created when we run a Java class.  | It exists physically.                                        | It exists physically.                                        |
| **Implementation** | Its implementation is known as JRE                          | It is the implementation of JVM                              | It is an implementation of any one of the below given Java Platforms released by Oracle Corporation:Standard Edition Java PlatformEnterprise Edition Java PlatformMicro Edition Java Platform |

#### **Question: What is the JIT compiler?**

**Answer:** JIT compiler runs after the program is executed and compiles the code into a faster form, hosting CPU's native instructing set. JIT can access dynamic runtime information, whereas a standard compiler doesn't and can make better optimizations like inlining functions that are used frequently. 

#### **Question: Which Java IDE to use, and why?**

#### **Answer**: A Java IDE is a software that allows Java developers to easily write as well as debug Java programs. It is basically a collection of various programming tools, accessible via a single interface, and several helpful features, such as code completion and syntax highlighting. Codenvy, Eclipse, and NetBeans are some of the[ most popular Java IDEs](https://hackr.io/blog/best-java-ides).