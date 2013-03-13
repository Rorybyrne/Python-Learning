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
