Type Parameters (generics)
--------------------------

For simple type parameters, a single upper-case letter (from the English
alphabet) should be used, starting with ``A`` (this is different
than the Java convention of starting with ``T``).  For example::

    class List[A] {
      def map[B](f: A => B): List[B] = ...
    }

If the type parameter has a more specific meaning, a descriptive name
should be used, following the class naming conventions (as opposed
to an all-uppercase style)::

    // Right
    class Map[Key,Value] {
      def get(key:Key):Value
      def put(key:Key,value:Value):Unit
    }

    // Wrong; don't use all-caps
    class Map[KEY,VALUE] {
      def get(key:KEY):VALUE
      def put(key:KEY,value:VALUE):Unit
    }


If the scope of the type parameter is small enough, a mnemonic can
be used in place of a longer, descriptive name::

    class Map[K,V] {
      def get(key:K):V
      def put(key:K,value:V):Unit
    }

.. toctree::

   higher_kinds
