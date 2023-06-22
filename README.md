
# Java-9-features

https://www.youtube.com/watch?v=NJY-D9JLLdQ

https://www.pluralsight.com/blog/software-development/java-9-new-features

## 1. REPL JShell
REPL = Read Eval Print Loop
<li> It helps you write simple code and test it in the cmd.
<li> open cmd.
<li> run jshell  command to enter the shell.

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/e2e74b1e-1ea7-47ee-9388-a99c170a3e6a)
<li> run /help command to see  all the commands you can run in j shell.

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/728bf176-aee2-4961-b3a3-e179f3f44987)
<li> You can directly print something from the cmd, declare and initialize variables or operations.</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/55fb74eb-2d00-4a7b-975e-047b68e904b0)
<li> Run/list command to see all the commands you already executed.</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/ad6a22b4-6c4a-4c3d-b49c-4c93b99d6094)
<li> You can also create methods and call them.</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/821776dd-b75b-4316-bdcf-125598266bf3)
<li> If we run again the /list command we will see that the entire function that we defined is being referred to by a single line identifier: </li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/53329362-c106-49e8-9e8f-dc86b5872ac4)
<li>J shell is not meant to create projects. The main intent is to get a prompt response when you want to check if the logic of the code or the output is correct or not.</li>
<li> We can edit the code that we have already executed with /edit command followed by the identifier of the line and an edit pad is opened</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/e7ab8bc4-0fe1-430d-8c4b-b7034e408a36)
<li>after you edit what you need, Accept->Exit and call the method again </li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/9ac82a41-1432-44cd-96df-94da014dd4f5)
![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/87443d2f-cdb9-4afb-ad40-dc8137f2d4bf)
<li>use /exit command to exit from J shell </li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/6e5347d7-6f27-4682-9f11-6b404cf765fd)
<li> You’re always in a complete loop: you first take an input and read it then you evaluate to see if it is correct, you print it and the loop keeps running around.</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/99b2751e-21e0-405b-ad47-2e2e3ff20b7b)

## 2. Collection Factory Methods

<li>Java 9 has added new static factory methods on list, set, and map interfaces.</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/39fb66e3-90a3-4c2d-adf4-e7fad71974ba)

<li> **Set** is an interface that extends the collection class and is an unordered collection of objects in which duplicate values cannot be stored.</li>
<li> Create a set before and after Java 9: </li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/f1282dac-8cbc-4ccd-836f-a76be08a62ac)

<li>List is a sub-interface of the collection class and it contains methods to insert or delete elements on an index basis.</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/d2b86996-de8c-4004-abcd-ee221615fe49)

<li>Maps are key-value pairs. Each key-value pair is known as an Entity. Contains only unique pairs of keys, which is helpful when updating, searching, or deleting based on the key.</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/e8f6d521-9cdd-4ce2-a0dc-2a8ad39820f8)

###### Benefits:
<li>Shorter and easier to read.</li>
<li>You don't have to pick a specific collection implementation when you create them anymore.</li>
<li>The collection implementations returned from the factory methods are highly optimized for the number of elements you put in.</li>
<li>This is because they're immutable: adding items to these collections after creation results in an 'UnsupportedOperationException'.</li>

## 3. HTTP/2 Client

<li>This feature is expected to change or be removed in the following releases.</li>
<li>Earlier developers often used third-party libraries like Apache HTTP.</li>
<li>Java's HTTP API is HTTP 1.1 and this was hard to maintain.</li>
<li>This is a replacement for the old 'HttpURLConnection' and also supports WebSockets and HTTP/2</li>

```
HttpClient client = HttpClient.newHttpClient();

HttpRequest req =
   HttpRequest.newBuilder(URI.create("http://www.google.com"))
              .header("User-Agent","Java")
              .GET()
              .build();


HttpResponse<String> resp = client.send(req, HttpResponse.BodyHandler.asString());
```

###### Benefits of the new HTTP client API:
<li>A simple and concise API to deal with most HTTP requests.</li>
<li>Support for HTTP/2 specification.</li>
<li>Better performance.</li>
<li>Better security.</li>
<li>Other enhancements.</li>

## 4. Project Jigsaw - Modularity

<li>It is trying to help to achieve the concept of modularity.</li>
<li>It adds support for the creation of modules in Java.</li>
<li>The modularization of the Java JDK. By encapsulation JDK internal classes, the platform is more secure, and evolving it becomes much easier.</li>

###### The need: 
When the codebase grows larger and the "Spaghetti code" increase exponentially, it is hard to truly encapsulate code, and there is no notion of explicit dependencies between different parts (JAR files) of a system.
Every public class can be accessed by any other public class on the classpath, leading to inadvertent usage of classes that weren't meant to be public API. The classpath itself is problematic. How do you know whether all the required JARs are there, or if there are duplicate entries? The module system addresses these issues. 

```
module blog {
  exports com.pluralsight.blog;

  requires cms;
}
```
![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/9b47c5a7-63ee-41b1-b8cb-299fb1925366)

<li>Both modules contain packages that are encapsulated because they're not exported.</li>
<li>Nobody can accidentally use classes from those packages.</li>
<li>When starting a modular application, the JVM verifies whether all modules can be resolved based on the *requires* statements.</li>
<li>Modules allow you to better structure your application with strong enforcement of encapsulation and explicit dependencies. </li>

###### Key features:
<li> **Strong encapsulation**: the modules can access only those parts of the module that have been made available for use. TODO: add example</li>
<li> **Clear dependencies**: provides the basis for a reliable configuration of modules. </li>
<li> **Reliable**: applications are more reliable by eliminating run-time errors. </li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/2df40240-f563-4862-b3eb-a1f0cab79627)

## 5. Improved Javadoc
<li>Javadoc now includes search right in the API documentation itself.</li>
<li>The Javadoc output is now HTML5 compliant.</li>
<li>Every Javadoc page includes information on which JDK module the class or interface comes from.</li>

![image](https://github.com/CosminaIacob/Java-9-features/assets/18678681/a7301bbd-3e0c-4933-a909-29fe6d055549)

## 6. Stream API improvements

<li>Stream API allows you to create declarative pipelines of transformations on collections.</li>
<li>In Java 9 were added four new methods: </li>

```
dropWhile()
takeWhile()
ofNullable()
```
<li>The iterate method allows you to provide a Predicate on when to stop iterating:</li>

```
IntStream.iterate(1, i -> i < 100, i -> i + 1).forEach(System.out::println);
```

<li>The integration between Optional and Stream has been improved. It is now possible to turn an Optional object into a Stream with the new stream() method on Optional:</li>

```
Stream<Integer> s = Optional.of(1).stream();
```

<li>Turning an Optional into a Stream is especially useful when composing complex Stream pipelines.</li>

## 7. Private interface methods

If you have several default methods on an interface with code that does almost the same thing, normally you'd refactor those methods to call a private method containing the shared functionality. But default methods can't be private. Creating another default method with shared code is not a solution, because this helper method becomes part of the public API. With Java 9, you can add private helper methods to interfaces to solve this problem. 
```
public interface MyInterface {

    void normalInterfaceMethod();

    default void interfaceMethodWithDefault() {  init(); }

    default void anotherDefaultMethod() { init(); }

    // This method is not part of the public API exposed by MyInterface
    private void init() { System.out.println("Initializing"); }
}
```

## 8. Multi-release JARs
<li>This feature allows you to create alternate versions of classes that are only used when running the library on a specific Java version: </li>

```
multirelease.jar
├── META-INF
│   └── versions
│       └── 9
│           └── multirelease
│               └── Helper.class
├── multirelease
    ├── Helper.class
    └── Main.class
```
<li>In this case, multirelease.jar can be used on Java 9, where instead of the top-level 'multirelease.Helper' class, the one under `META-INF/versions/9` is used.</li>
<li>This Java 9-specific version of the class can use Java 9 features and libraries. At the same time, using this JAR on earlier Java versions still works, since the older Java versions only see the top-level Helper class.</li>



















