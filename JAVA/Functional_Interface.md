# Functional Interfaces in Java

A functional interface is an **interface that only has one method**. \
The class is annotated by @functionalInterface.

```java
@FunctionalInterface
public interface Supplier<T> {
    T get();
}
```

## Principal functional interfaces

| Functional interface  | Method  | Param | Return  |
|:----------------------|:--------|:------|:--------|
| `Function<T, R>`      | apply   | T     | R       |
| `BiFunction<T, U, R>` | apply   | T, U  | R       |
| `Consumer<T>`         | accept  | T     | void    |
| `BiConsumer<T, U>`    | accept  | T, U  | void    |
| `Supplier<T>`         | get     |       | T       |
| `Predicate<T>`        | test    | T     | boolean |
| `BiPredicate<T, U>`   | test    | T, U  | boolean |
| `UnaryOperator<T>`    | apply   | T     | T       |
| `BinaryOperator<T>`   | apply   | T, T  | T       |
| `Runnable`            | run     |       | void    |
| `Callable<V>`         | call    |       | V       |
| `Comparator<T>`       | compare | T, T  | int     |