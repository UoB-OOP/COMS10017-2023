# Week 16

The most important tasks to attempt this week are:
1. The non-daggered questions on Generics in worksheet 3 
2. [Task 2 on the visitor pattern](#task-2-visiting-houses)

## Task 1: Worksheet

For this week, please
download [Worksheet 3](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS10017_2022_TB-2/content/oo/pdfs/sheet3_problems.pdf)

These worksheets are not credit bearing. You are encouraged to work in your with your partner. We find that students who complete these worksheets typically get higher marks in the summative coursework at the end.

Solutions will be released "later". 

## Task 2: Visiting Houses

Past students often found the visitor pattern to be the trickiest thing to understand and use in their summative coursework, so this is an opportunity to get it all figured out in advance. It can be confusing, because it introduces two levels of indirection with double dynamic dispatch, so it is well worth using Intellij's debugger to step through the code and make sure you understand what's happening.

### Understanding the visitor pattern

Though not its only application, we will primarily use the visitor pattern to look past the *declared* type we have for an object and determine its *concrete* type. To use `House unknownHouse = new BrickHouse();` as an example, `House` is the declared type, ie. the type of the `unknownHouse` reference, and `BrickHouse` is the concrete type of the actual object `unknownHouse` refers to.

To introduce the different components of the visitor pattern by way of analogy: Imagine you're looking for a house to rent and you see a listing for "a `House`", with few specific details except an address. How can you find out what kind of `House` it is if the website doesn't tell you? One way is to `visit` the `House` yourself. You call to ask the `House` if you can go as a `Visitor` and they `accept`. Once `accept`ed as a `Visitor`, you `visit` the `House`. Now you can see exactly what kind of `House` it is (be it a `StrawHouse`, a `StickHouse`, or a `BrickHouse`) and you can `return` from your `visit` with different information depending on which particular type of `House` it is.

For example, let's say you want to rate the sturdiness of the `House` out of 10, based on what particular kind of `House` it is. Here's how you could represent yourself as a `Visitor` in code:

```java
public class StudentVisitor implements House.VisitorInt {
  public Integer visit(StrawHouse house) { return 1; }
  public Integer visit(StickHouse house) { return 5; }
  public Integer visit(BrickHouse house) { return 10; }
}
```

And here's how you could visit the house:

```java
House unknownHouse = new BrickHouse();
StudentVisitor rian = new StudentVisitor();
Integer sturdinessRating = unknownHouse.accept(rian);
System.out.println(sturdinessRating); // Prints 10
```


### Tasks

**Download the skeleton code** [here](https://www.ole.bris.ac.uk/bbcswebdav/courses/COMS10017_2022_TB-2/content/oo/pdfs/house-visitor-skeleton_no_idea.zip)

1. Complete the `ChartedSurveyor` class which implements `House.VisitorInt`. It should return an integer representing the estimated rent per calendar month for a house. Which specific values should be returned is not important, but the `BrickHouse` should cost more than the `StickHouse`, which should in turn cost more than the `StrawHouse`. Use this `ChartedSurveyor` visitor to implement `public static Integer estimateRentPCM(House house)` in the `OnceUponATime` class

2. Implement `public static Integer estimateHeatingBillPCM(House house)`, which instead estimates the heating bill (you're free to make your own estimations). You should do this by using the visitor pattern with a class that implements the more generic `House.Visitor<T>` instead of `House.VisitorInt`. Implement the class in the following ways and reflect on the advantages/disadvantages of each:
   1. Define the class in its own separate file
   2. Define the class within the `OnceUponATime` class, ie. define it as a named *inner class*
   3. Implement the visitor as an *anonymous inner class*

3. Implement `public static String letMeComeIn(House house)`, which returns a string telling the story of what happens when the Big Bad Wolf visits the house. The exact string text is left up to your own imagination, but your implementation must:
   - Include the name of the `LittlePig` occupying the house in the returned string
   - Include whether the Big Bad Wolf manages to blow the house down 
   - For the brick house, the story should be different depending on whether the pot is boiling or not
   - If the Big Bad Wolf can get to the `LittlePig`, he should eat them (setting their `hp` to 0)
