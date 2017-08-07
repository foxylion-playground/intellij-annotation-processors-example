# intellij-annotation-processors-problem

## Build with gradew

```
➜  intellij-problem git:(master) ./gradlew build
:compileJava
:processResources NO-SOURCE
:classes
:jar
:assemble
:compileTestJava NO-SOURCE
:processTestResources NO-SOURCE
:testClasses UP-TO-DATE
:test NO-SOURCE
:check UP-TO-DATE
:build

BUILD SUCCESSFUL
```

Everything works as expected.

## Build with IntelliJ

Ensure you try this by checking out a new repository.

- Import new project from exising source
- Select git root
- Choose external model "Gradle"
- Tick "Auto Import" and "Create separate module..."
- Use "Gradle wrapper task configuration"
- File | Settings | Build, Execution, Deployment | Compiler | Annotation Processors
  - Tick "Enable annotation processing"
  - Choose "Module content root"
  - Production sources directory: "build/generated/sources/apt/main"
  - Production sources directory: "build/generated/sources/apt/test"
 - Rebuild Project
 
 Windows 10 : This works as expected
 ### Results for Ubuntu 17.04
 ```
 IntelliJ IDEA 2017.2.1
Build #IU-172.3544.35, built on July 31, 2017
Licensed to itdesign GmbH / Jakob Jarosch
Subscription is active until April 28, 2018
JRE: 1.8.0_152-release-915-b6 amd64
JVM: OpenJDK 64-Bit Server VM by JetBrains s.r.o
Linux 4.10.0-28-generic
```
The build is now failing due to a unresolved dependency class "ImmutableMyImmutable".

```
Information:java: Errors occurred while compiling module 'intellij-problem_main'
Information:javac 1.8.0_131 was used to compile java sources
Information:07.08.17 16:45 - Compilation completed with 1 error and 4 warnings in 1s 410ms
Warning:Output path /home/.../intellij-problem/build/generated/source/apt/test/build/generated/sources/apt/main intersects with a source root. Only files that were created by build will be cleaned.
Warning:Output path /home/.../intellij-problem/build/generated/source/apt/test/build/generated/sources/apt/test intersects with a source root. Only files that were created by build will be cleaned.
Warning:Output path /home/.../intellij-problem/build/generated/source/apt/main/build/generated/sources/apt/main intersects with a source root. Only files that were created by build will be cleaned.
Warning:Output path /home/.../intellij-problem/build/generated/source/apt/main/build/generated/sources/apt/test intersects with a source root. Only files that were created by build will be cleaned.
/home/.../intellij-problem/src/main/java/Test.java
Error:(4, 28) java: cannot find symbol
  symbol:   variable ImmutableMyImmutable
  location: class Test
```
