# java6-functional-immutable

Simple immutable classes to support functional programming in Java 6.

## Why?

I wanted a simple lib containing lists with `.map` and `.filter` methods. While there are
already many around, I had some specific requirements: 

- The names of the classes should be different from the `java.util` ones to better enable simultaneous usage.
    - E.g., here I use `IList` as class name to differentiate from `java.util.List` and hint that the list is immutable.
    - This is to cause less confusion for inexperienced developers in old codebases.
- Since it is a different lib, it should be easier to add to a legacy project where the classpath is already filled
  with many libs (e.g. guava) which, if you updated, there could be conflicts between your dependencies's dependencies.
  For instance, you may not be able to update Guava version if one dependency you already have depends on a very specific
  Guava version.
- Inclusion of more general classes such as `IPair`, `ITriple` and `IOption`.
    - Also other more particular to the functional style, such as `IEither` and the `IFunction` interface.
- Addition of interfaces, classes and methods as needed.
- Anonymous classes [_can_ get verbose and that is a drawback][guava-functional]. Still, it is possible to
 profit from the functional style once it is enough a common way of reasoning in your team. In this case, the benefits
 may be higher than the cons. Filtering `for`s, as an example, can get much in the way
of the intent of the code. Nevertheless, Imperative foreach loops are still available (e.g. `IList` implements `Iterable`), so
you always have the choice of falling back when the functional approach is unsuitable.

Lastly, it seemed like a good exercise anyway.

LICENSE: MIT

[guava-functional]: https://github.com/google/guava/wiki/FunctionalExplained#Caveats