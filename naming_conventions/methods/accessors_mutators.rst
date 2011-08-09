Accessors/Mutators
~~~~~~~~~~~~~~~~~~

Scala does *not* follow the Java convention of prepending ``set``/``get`` to
mutator and accessor methods (respectively).  Instead, the following conventions
are used:

* For accessors of properties, the name of the
  method should be the name of the property
* In some instances, it is acceptable to prepend "`is`" on a boolean accessor
  (e.g. ``isEmpty``). This should only be the case when no corresponding 
  mutator is provided.  Please note that the Lift_ convention of appending 
  "``_?``" to boolean accessors is non-standard and not used outside of the 
  Lift framework.
* For mutators, the name of the method should be the name of the property with
  "``_=``" appended.  As long as a corresponding accessor with that particular
  property name is defined on the enclosing type, this convention will enable
  a call-site mutation syntax which mirrors assignment.  Note that this is not
  just a convention but a requirement of the language.

::
    
    class Foo {
    
      def bar = ...
      
      def bar_=(bar: Bar) {
        ...
      }
      
      def isBaz = ...
    }
    
    val foo = new Foo
    foo.bar             // accessor
    foo.bar = bar2      // mutator
    foo.isBaz           // boolean property

Quite unfortunately, these conventions fall afoul of the Java convention to name
the private fields encapsulated by accessors and mutators according to the
property they represent.  For example::
    
    public class Company {
        private String name;
        
        public String getName() {
            return name;
        }
        
        public void setName(String name) {
            this.name = name;
        }
    }

In Scala, there is no distinction between fields and methods.  In fact, fields are
completely named and controlled by the compiler.  If we wanted to adopt the Java
convention of bean getters/setters in Scala, this is a rather simple encoding::
    
    class Company {
      private var _name: String = _
      
      def name = _name
      
      def name_=(name: String) {
        _name = name
      }
    }
    
While Hungarian notation is terribly ugly, it does have the advantage of
disambiguating the ``_name`` variable without cluttering the identifier.  The
underscore is in the prefix position rather than the suffix to avoid any danger
of mistakenly typing ``name _`` instead of ``name_``.  With heavy use of Scala's
type inference, such a mistake could potentially lead to a very confusing error.

Note that the Java getter/setter paradigm was often used to work aroun a lack
of first class support for Properties and bindings.   In Scala, there are
libraries that support properties and bindings.  The convention is to
use an immutable refrence to a property class that contains its own getter and
setter.  For example::

  class Company {
    val string : Property[String] = 
      Property("Initial Value")

.. _Lift: http://liftweb.com

