Objects
-------

Objects follow the class naming convention (camelCase with a capital first letter)
except when attempting to mimic a package or a function.  These situations don't happen often, but
can be expected in general development.::
    
    object ast {
      sealed trait Expr
      
      case class Plus(e1: Expr, e2: Expr) extends Expr
      ...
    }

    object inc {
      def apply(x: Int) : Int = x + 1
    }

In *all* other cases, objects should be named according to the class naming
convention.

