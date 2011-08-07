Method Invocation
=================

Generally speaking, method invocation in Scala follows Java conventions.  In
other words, there should not be a space between the invocation target and the
dot (``.``), nor a space between the dot and the method name, nor should there
be any space between the method name and the argument-delimiters (parentheses).
Each argument should be separated by a single space *following* the comma (``,``)::
    
    foo(42, bar)
    target.foo(42, bar)
    target.foo()
    
As of version 2.8, Scala now has support for named parameters.  Named parameters
in a method invocation should be treated as regular parameters (spaced accordingly
following the comma) with a space on either side of the equals sign::
    
    foo(x = 6, y = 7)
    
While this style does create visual ambiguity with named parameters and variable
assignment, the alternative (no spacing around the equals sign) results in code
which can be very difficult to read, particularly for non-trivial expressions for
the actuals.

.. toctree::

   arity0/index
   arity1/index
   symbolic_methods
