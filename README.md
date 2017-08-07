# IntelliJ, Gradle & Annotation Processors

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
- Tick only "Auto Import"
- Use "Gradle wrapper task configuration"
- File | Settings | Build, Execution, Deployment | Compiler | Annotation Processors
  - Tick "Enable annotation processing"
  - Choose "Module content root"
  - Production sources directory: "src/main/generated"
  - Production sources directory: "src/main/generated"
 - Rebuild Project
 
