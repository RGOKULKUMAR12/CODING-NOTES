- To create a simple Java program, you need to `create a class that contains the main method`.

### ***Compilation Flow:*** ###

- When we compile Java program using `javac tool`, the Java compiler `converts the source code into byte code`.

![[../../IMAGES/Pasted image 20240809144826.png]]
### ***First Java Program:*** ###

```java
class Simple{
	public static void main(String[] args){//method signature
		System.out.println("Hello World");
	}
}
```

***Parameters used in the above code***

|           **PARAMETERS**           |                                                                                                                                    **MEANING**                                                                                                                                     |
| :--------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|              `class`               |                                                                                                                 It is a keyword is used to declare a class in Java                                                                                                                 |
|              `public`              |                                                                               1. This keyword is an `access modifier`<br>2. It represent `visibility` to others<br>3. `Public` means visible to all                                                                                |
|              `static`              | 1. It is a `keyword`<br>2.The core advantage of the static method is that there is no `need to create an object to invoke the static method`. The main() method is executed by the JVM, so it doesn't require creating an object to invoke the main() method. So, it saves memory. |
|               `void`               |                                                                                                                             return type of the method                                                                                                                              |
|               `main`               |                                                                                                                           starting point of the program                                                                                                                            |
| `String[] args` or `String args[]` |                                                                                                                               Command Line Argument                                                                                                                                |
### ***Different ways to write method signature*** ###

```java
	public static void main(String[] args)  
	public static void main(String []args)  
	public static void main(String args[])  
	public static void main(String... args)  
	static public void main(String[] args)  
	public static final void main(String[] args)  
	final public static void main(String[] args)  
	final strictfp public static void main(String[] args)
```

### ***How does a .java file compile/run*** ###

1. At   