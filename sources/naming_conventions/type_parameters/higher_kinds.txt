Higher-Kinds and Parameterized Type parameters
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Higher-kinds are theoretically no different from regular type parameters
(except that their kind_ is at least ``*=>*`` rather than simply ``*``).
The naming conventions are generally similar, however it is
preferred to use a descriptive name rather than a single letter, for clarity::
    
    class HigherOrderMap[Key[_], Value[_]] { ... }
    
The single letter form is (sometimes) acceptble for fundamental
concepts used throughout a codebase, such as ``F[_]`` for Functor and ``M[_]`` for Monad. 
    
In such cases, the fundamental concept should be something well known and understood
to the team, or have tertiary evidence, such as the following::

    def doSomething[M[_]: Monad](m: M[Int]) = ...

Here, the type bound ``: Monad`` offers the necessary evidence to inform the reader that
``M[_]`` is the type of the Monad.

.. _kind: http://en.wikipedia.org/wiki/Kind_(type_theory)

