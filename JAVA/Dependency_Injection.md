# Dependency Injection in Java

In Java, one of the biggest concept is "simple responsibility" of classes.
Each element has only small responsibilities, to not make it too hard.

But, if a class depends on another, it makes a Tight coupling (un couplage fort quoi). For example : 

```java
public Circle(String name){
    this.name = name;
    this.point = new Point(0, 0);
    super();
}
```
Here, Circle depends on a Point and creates-it on his own.

A better solution is to inject a dependency between Circle and point (Low coupling). It's called **manual injection**.

```java
public Circle(String name, Point p){
    this.name = name;
    this.point = p;
    super();
}

var center = new Point(0, 0);
var circle = new Circle(center);
```
In this case, if we modify constructors of Point, it will be good :)

But, in some big codes, manual injection is too long, it's better to make **automatic injection**.

```java
var registry = new InjectorRegistry();
registry.registerProvider(Point.class, new Point(0, 0));
registry.registerProvider(String.class, () -> "hello");
registry.registerProviderClass(Circle.class, Circle.class);

var circle = registry.lookupInstance(Circle.class);
IO.println(circle.center);  // Point(0, 0)
IO.println(circle.name);  // hello 
```

With this solution, we have a registry that, for each class (Circle, String), associate a way to build it.
Here, we create a circle that is already composed of elements, without make high coupling.