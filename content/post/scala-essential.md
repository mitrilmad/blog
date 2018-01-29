---
title: "scala essential"
date: 2017-03-31T12:49:35+09:00
draft: true
---

* Algebraic data types
  * Model data with logical ors and logical ands.
  * A website visitor is :
      1. logged in; or
      2. anonymous

  * A logged in user has:
  * an ID; and
  * an email address

  * Structure of the code follows the structure of the data.

  * Two patterns:
      1. product types (and)
      2. sum types (or)

  * Product type:
         A has a B and C

```
  final case class A(b: B, c: C)
    A has a B and C

```

  * Sum type:
        A is a B or C

```
  sealed trait A
  final case class B() extends A
  final case class C() extends A
    A is a B or C
```

  * Sum and product together makse algebraic data types.
   A logged in user has:
   * an ID; and
   * an email address
   An anonymous has:
   * an ID

```
  sealed trait Visitor {
    id: Id
  }
  final case class Anonymous(id: Id) extends visitor
  final case class User(id: Id, email: Email) extends Visitor
```

  * A calculation is a success or failure.

```
  sealed trait Calculation
  final case class Success() extends Calculation
  final case class Failure() extends Calculation
```

  * A success has an value. A failure has an error message.

```
  sealed trait Calculation
  final case class Success(value: Int) extends Calculation
  final case class Failure(msg: String) extends Calculation
```

  * Structure data with logical ands and ors. These are called    algebraic data types. Code follows immediately from structure of the data.

* Structural Recursion

* Functional Loops

* Lexical Scopes

'''
BLOCKS AND VISIBILITY

The definitions inside a block are only visible from within the block.
The definitions inside a block shadow definitions of the same names outside the block.
'''

* Semicolons and infix operators

```
someLongExpression
+someOtherExpression

```

would be interpreted as two expressions:
```
someLongExpression;
+someOtherExpression
```

two solution

```
(someLongExpression
+someOtherExpression)
```

or

```
someLongExpression +
someOtherExpression
```
