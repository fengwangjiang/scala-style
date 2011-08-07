Operators
~~~~~~~~~

Avoid!  Despite the degree to which Scala facilitates this area of API design,
operator definition should not be undertaken lightly, particularly when the
operator itself is non-standard (for example, ``>>#>>``).  As a general rule,
operators have two valid use-cases:

* Domain-specific languages (e.g. ``actor1 ! Msg``)
* Logically mathematical operations (e.g. ``a + b`` or ``c :: d``)

In the former case, operators may be used with impunity so long as the syntax is
actually beneficial.  However, in the course of standard API design, operators
should be strictly reserved for purely-functional operations.  Thus, it is
acceptable to define a ``>>=`` operator for joining two monads, but it is not
acceptable to define a ``<<`` operator for writing to an output stream.  The
former is mathematically well-defined and side-effect free, while the latter is
neither of these.

As a general rule, operators should be well-understood and self documenting in
nature.  The rule of thumb is as follows: if you need to explain what the operator
does, then it should be a method with a real, descriptive name rather than a
symbolic operator.  There are some *very* rare cases where it is acceptable to
invent new operators.  Odds are, your API is not one of those cases!

Operator definition should be considered an advanced feature in Scala, to be used
only by those most well-versed in its pitfalls.  Without care, excessive operator
overloading can easily transform even the simplest code into symbolic soup.

