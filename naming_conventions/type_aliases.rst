Type Aliases
------------

Type aliases follow the same naming conventions as classes.  For example::
    
    type StringList = List[String]

The exception to this rule are for 'type lambdas'.  This is when a type constructor needs to be adapted to have different type parameters.  In this instance it is acceptible to use a single letter to represent the lambda type alias.  For example, the type alias X is acceptible in the following use case::

    def foo[Container[_]](x : Container[String]) = ...
    foo[({ type X[Y] = Tuple2[Int,X] })#X](Tuple2(5,"Hi"))
