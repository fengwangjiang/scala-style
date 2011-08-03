Annotations
-----------

Annotations, such as ``@volatile`` should be in camel-case, with the first letter
being lower case::
    
    class cloneable extends StaticAnnotation

This convention is used throughout the Scala library, even though
it is not consistent with Java annotations.

Note: This convention applied even when using type aliases on annotations.  For
example, when using JDBC::

    type id = javax.persistence.Id @annotation.target.field
    @id
    var id: Int = 0

