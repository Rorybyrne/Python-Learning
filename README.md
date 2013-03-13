#Python Learning (2.7)

## General
* **White space matters!**
* 4 spaces per tab.
* Avoid global variables.
* "If your classes Table and Chair in furn.py need to import Carpenter from workers.py to answer a question such as table.isdoneby(), and if conversely the class Carpenter needs to import Table and Chair, to answer the question carpenter.whatdo(), then you have a circular dependency"
* **Everything is an object**

##Modules
* **Good**
<pre><code>import math
[...]
x = math.sqrt(9)</code></pre>
* **Bad**
<pre><code>from math import sqrt
[...]
x = sqrt(9)</pre></code>
* **Very bad**
* <pre><code>from math import *
[...]
x = sqrt(9)

##Packages
* If the directory has a `__init__.py` file, it's considered a Python package
* Modules in a package are imported similarly to normal modules, but the `__init__.py` file is used to manage all package-wide definitions.
* To import the module `modu` from the directory `pack/`, use the statement `import pack.modu`.
* The statemtnt first executes all top-level statements in `__init__.py`, then all top-level statements in `pack/modu.py.` Then every variable, function, and class is available in the `pack.modu` namespace.

# Mutable and Immutable objects
* Mutable types allow modification of the content. Immutable types do not.
* Common mutable objects are lists and dictionaries (`append()`, `pop()`, etc.)
* Tuples, strings, and integers are immutable.
* If `x = 5`, and you want to add 1 to x, you must create a new object with `x = x + 5`.
* **Mutable objects cannot be used as dictionary keys.**
* **This**
* <pre><code>print "".join([str(n) for n in range(20)])</pre></code>
* **Is better than**
* <pre><code>numbers = []
for n in range(20):
        numbers.append(str(n))
print "".join(numbers)</pre></code>
* **Is better than**
* <pre><code>numbers = ""
for n in range(20):
        numbers += str(n)
print numbers</pre></code>
* This is because `numbers += str(n)` creates a new object every time the loop runs, making it slow and inefficient.
* Using a list means that I can modify the variable `numbers` without creating a new object, and then I can use `.join` to concatenate.

