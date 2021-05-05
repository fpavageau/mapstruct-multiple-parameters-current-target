# Reproducer for a MapStruct bug with 1.4.2.Final

## Prerequisites

- JDK 8

## Build

    ./gradlew build
    
The build should fail with

    > Task :compileJava FAILED
    /some/path/mapstruct-multiple-parameters-current-target/src/main/java/com/ekino/mapstruct/MyMapper.java:24: error: Method has no source parameter named "child". Method source parameters are: "parent, other".
    Flattened flatten(Parent parent, Other other);
    ^
    /some/path/mapstruct-multiple-parameters-current-target/src/main/java/com/ekino/mapstruct/MyMapper.java:24: warning: Unmapped target property: "name".
    Flattened flatten(Parent parent, Other other);
    ^
    1 error
    1 warning

## Issue

https://github.com/mapstruct/mapstruct/issues/2431
    
----

Licensed under the Apache License, Version 2.0
