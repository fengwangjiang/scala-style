Symbolic Method Names
~~~~~~~~~~~~~~~~~~~~~

Avoid!  Despite the degree to which Scala facilitates this area of API design,
the definition of methods with symbolic names should not be undertaken lightly, 
particularly when the symbols itself are non-standard (for example, ``>>#>>``).  
As a general rule, symbolic method names have two valid use-cases:

* Domain-specific languages (e.g. ``actor1 ! Msg``)
* Logically mathematical operations (e.g. ``a + b`` or ``c :: d``)

In the former case, symbolic method names may be used with impunity so long as the syntax is
actually beneficial.  However, in the course of standard API design, symbolic method names
should be strictly reserved for purely-functional operations.  Thus, it is
acceptable to define a ``>>=`` method for joining two monads, but it is not
acceptable to define a ``<<`` method for writing to an output stream.  The
former is mathematically well-defined and side-effect free, while the latter is
neither of these.

As a general rule, symbolic method names should be well-understood and self documenting in
nature.  The rule of thumb is as follows: if you need to explain what the method
does, then it should have a real, descriptive name rather than a symbols.
There are some *very* rare cases where it is acceptable to
invent new symbolic method names.  Odds are, your API is not one of those cases!

The definition of methods with symbolic names should be considered an advanced 
feature in Scala, to be used only by those most well-versed in its pitfalls. 
Without care, excessive use of symbolic method names can easily transform even 
the simplest code into symbolic soup.

