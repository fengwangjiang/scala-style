Higher-Kinds and Parameterized Type parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

While higher-kinds are theoretically no different from regular type parameters
(except that their kind_ is at least ``*=>*`` rather than simply ``*``), their
naming conventions do differ somewhat.  Generally, 
parameterized type parameters should have descriptive names and follow the same
convention used for naming traits, classes and objects.  For example::
    
    class HigherOrderMap[Key[_], Value[_]] { ... }
    
It is also (sometimes) acceptable to use a terse (one letter) name for fundamental
concepts used throughout a codebase, such as F[_] for Functor and M[_] for Monad. 
    
In such cases, the fundamental concept should be something well known and understood
to the team, or have tertiary evidence, such as the following::

    def doSomething[M[_]: Monad](m: M[Int]) = ...

Here, the type bound : Monad offers the necessary evidence to inform the reader that
M[_] is the type of the Monad.

.. _kind: http://en.wikipedia.org/wiki/Kind_(type_theory)

