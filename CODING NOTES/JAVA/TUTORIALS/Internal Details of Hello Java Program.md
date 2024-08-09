
### ***What happens at compile time?*** ###

- At compile time, the Java file is `compiled by Java Compiler` (`It does not interact with OS`) and `converts the Java code into bytecode`.

![[../../IMAGES/Pasted image 20240809151728.png]]
### ***What happens at the Runtime*** ###

- At runtime, the following steps are performed:
![[../../IMAGES/Pasted image 20240809151837.png]]
>[!info]
>- ***Classloader*** - It is the` subsystem of JVM` that is `used to load class files`.
>- ***Bytecode Verifier*** -  Checks the `code fragments for illegal code` that can `violate access rights to objects`.
>- ***Interpreter*** - `Read bytecode stream` then `execute the instructions`.
