# Modules 

### Importing/Loading a module

### *import*: underneath the hoods

An import is a runtime operation that performs the following steps when a program imports a file/module

* Checks to see if the module being imported is already loaded by looking for it in the **sys.modules** table

If the module is not already loaded i.e. if not found in the **sys.modules** table

* **Finds** the module's file
* **Compiles** it to byte code, if needed (by running the compiler)
* **Executes** the module's code and creates a module object
* **Stores** a reference to the module's instance in the **sys.modules** table

**Finding the module**

To import a module, Python tries to locate the requested module in a standard *module search path*.

**Compiling the module**

Once the source code corresponding to the requested module is found in the *module search path*, Python 

* **Compiles** the source code to generate its byte code (or)
* **Does not compile** the source code but just uses the byte code generated in the previous import operation.

**Executing the module**

The bytecode from the previous step is executed from top to bottom and a module object is created. The top-level code is executed and any assignments to names results in the attributes of the newly created module object.


### Re-importing/Reloading a module

Reloading a module is useful in cases where dynamic customizations are needed by the end-users. 

By default, an imported module is loaded ONLY once per process. Once a module is imported, any subsequent imports just refers to the module already loaded in memory. To force a re-import, use *imp.reload* method.
