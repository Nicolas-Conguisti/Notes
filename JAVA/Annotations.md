# Java Annotations

In Java, we declare annotations with **@interface**.

Annotations are used in top of class and methods declarations. \
It's used to give meta information on the **declarative part** of the language : method / class / parameter / attribute.

Annotations can be a part of :
- The language itself (Java native)
- A framework (Quarkus, Spring)
- We can create OWN

## Declaration of an annotation

```java
@Retention(RUNTIME)
@Target({METHOD, CONSTRUCTOR})
public @interface Inject { }
```
An annotation can be described by other annotations (meta-annotations), even recursively !
She can also have parameters


Parameters of annotations are registered is their "value" attribute. We can give a type to it.
Value attribute can also be a table.

```java
@Documented
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.ANNOTATION_TYPE)
public @interface Retention {
    RetentionPolicy value();
}
```

## Principal annotations

### @Retention
Define the range of the annotation :

| Retention                 | Description                                                                                |
|:--------------------------|:-------------------------------------------------------------------------------------------|
| `RetentionPolicy.RUNTIME` | The annotation is still visible at the execution.                                          |
| `RetentionPolicy.CLASS`   | The annotation is visible in the .class file but ignored at execution.                     |
| `RetentionPolicy.SOURCE`  | The annotation is ignored by the compiler. Only useful for the developer (like @Override). |

### @Target
Define where the annotation has the right to be placed :
- ElementType.METHOD
- ElementType.CONSTRUCTOR
- ElementType.FIELD
- ElementType. ....

## Others annotations
- @Override
- @FunctionalInterface
- @Deprecated
- @JSONProperty
- ...