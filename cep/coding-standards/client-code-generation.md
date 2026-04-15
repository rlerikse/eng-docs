# Client Code Generation

Client including models can efficiently and reliably be generated from existing `openapi-spec.yml` files. This changes the SSoT from the `models/` folder to the OpenAPI spec, providing absolute and continual congruity between actual code and published documentation. Additionally, the generated clients can be distributed, with complete and generated models, thus reducing client implementation time and providing support in any language if the OpenAPI spec is distributed as well.

## Requirements

- A standards-compliant OpenAPI spec document (`openapi-spec.yml`).
- A multi-project Gradle build (Gradle 6.0 min required).

## Rationale

An approach summary can be found here: Comparing Client Generation To OpenApi Generation

## Multi-Project Gradle Build

You will want to have a multi-project build. To accomplish this, place any existing code in sub-modules (directories) within the main Gradle project. Then, in your `settings.gradle` file, include the sub-modules by directory name.

```gradle
rootProject.name = '<root project name>'

include '<main module directory>', 'client'
```

You will have moved your build.gradle file to your main module directory, so you will have to create a new one at the top of the multi-project build. A minimal build.gradle is all that is required, as your dependencies are specified in the actual module.

```gradle
plugins {
    id "idea"
    id "java"
    id "jacoco"
}
```

## Setting Up Your Client Module

In a directory called client/ from the root of your repo, you will create a new build.gradle and init the wrapper with gradle wrapper for your ./gradlew script. Be sure to adjust the values below to the appropriate directories / versions for your build.

```gradle
buildscript {
    ext {
        findBugsVersion = "3.0.2"
        jacksonVersion = "2.12.2"
        openApiGeneratorVersion = "4.3.1"
        // ... other versions
    }
    // ... repositories and dependencies
}

plugins {
    id "idea"
    id "java"
    id "maven-publish"
}

// ... additional configuration

task sourceJar(type: Jar) {
    classifier "sources"
}

jar {
    from sourceSets.main.allSource
}

// ... publishing configuration

openApiGenerate {
    generatorName = "java"
    // ... other configuration
}

sourceSets.main.java.srcDirs += "build/generated/sources"
tasks.compileJava.dependsOn tasks.openApiGenerate

```

Notice the last line of the above file connect the openApiGenerate task to the compileJava task, so the generate should be run every time as part of an assemble or a build from Gradle.

Also, you should add a file called .openapi-generator-ignore to prevent the generator from doing too much:

```ignore title=".openapi-generator-ignore"
gradlew
gradlew.bat
gradlew
gradlew.bat
gradle/wrapper/gradle-wrapper.jar
gradle/wrapper/gradle-wrapper.properties
docs/*
VERSION
.openapi-generator/*
.openapi-generator/VERSION
.gitignore
.travis.yml
build.sbt
git_push.sh
gradle.properties
pom.xml
settings.gradle
README.md
src/main/AndroidManifest.xml
src/main/*
src/main/
src/main
src/
```

Once you do this, you should be able to run the following command from the top level of your repo, which should generate the client and models to the build folder of the client:

```bash
./gradlew clean openApiGenerate
```

## Publishing

Be sure that you correctly modified the apiPackage and modelPackage values in the above build.gradle file. Additionally, be sure to set the artifactId and group for publishing to Maven.

```bash
./gradlew clean publish
```

## Using the generated models in the code

Assuming you have a working client that is capable of compilation, you are ready to use the generated models in your deployment code.

```gradle
implementation project(":client")
```

This will add a reference to the generated client for the generated models.

## Recommendations and General Usage

### Automated Converter

As with any imported library model, duplicate objects can and will crop up with importing multiple related clients which operate on the same object domain.

```java
public static String writeToString(Object object) {
  if (object == null) return null;
  String value = null;
  try {
    value = OBJECT_MAPPER.writeValueAsString(object);
  } catch (Exception e) {
    String msg = String.format(ErrorMessages.ERROR_CONVERTING_OBJECT_TO_STRING, e.getMessage(), object);
    throw new ObjectToStringException(msg, e);
  }
  return value;
  }

public static <T> T readFromString(String input, Class<T> c, String failureMessage) {
  T result = null;
  try {
      result = OBJECT_MAPPER.readValue(input, c);
  } catch (Exception ex) {
      if (ex.getLocalizedMessage() != null)
          failureMessage = failureMessage.replace("$$", ex.getLocalizedMessage());
      if (!failureMessage.equals("")) throw new StringToObjectException(failureMessage, ex);
  }
  return result;
}

public static <T> T mapObjectType(Object o, Class<T> dest) {
  return readFromString(writeToString(o), dest);
}
```

The following can then be used via:

```java
WrongPointType wrongPointType = new WrongPointType().latitude(42.0).longitude(-82.0);
RightPointType rightPointType = mapObjectType(wrongPointType, RightPointType.class);
```

Thus, converting between congruent object model types can be carried out efficiently and consistently throughout a codebase without the need for complex transform classes.