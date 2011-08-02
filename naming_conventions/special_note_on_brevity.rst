Special Note on Brevity
-----------------------

Because of Scala's roots in the functional languages, it is quite normal for
local field names to be extremely brief::
    
    def add(a: Int, b: Int) = a + b
    
While this would be bad practice in languages like Java, it is *good* practice
in Scala.  This convention works because properly-written Scala methods are
quite short, only spanning a single expression and rarely going beyond a few
lines.  Very few local fields are ever used (including parameters), and so there
is no need to contrive long, descriptive names.  This convention substantially
improves the brevity of most Scala sources.  This in turn improves readability,
as most expressions fit in one line and the arguments to methods have descriptive
type names.

This convention only applies to parameters of very simple methods (and local fields for 
very simply classes); everything in the public interface should be descriptive.  Also note
that the names of arguments are now part of the public API of a class, since users can
use named parameters in method calls.
