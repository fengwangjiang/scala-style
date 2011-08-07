Symbolic methods
----------------

Methods with symbolic names should *always* be invoked using infix notation with
spaces separated the target, the symbolic method and the parameter::
    
    // right!
    "daniel" + " " + "Spiewak"
    
    // wrong!
    "daniel"+" "+"spiewak"
    
For the most part, this idiom follows Java and Haskell syntactic conventions.

Symbolic methods which take more than one parameter (they do exist!) should still be
invoked using infix notation, delimited by spaces::
    
    foo ** (bar, baz)
    
Such methods are fairly rare, however, and should be avoided during API design.

Finally, the use of the ``/:`` and ``:\`` should be avoided in preference to the more explicit
``foldLeft`` and ``foldRight`` method of ``Iterator``.  The right-associativity of the ``/:`` 
can lead to extremely confusing code, at the benefit of saving a few characters.
