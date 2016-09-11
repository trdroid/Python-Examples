# Modules 


### *import*: underneath the hoods

An import is a runtime operation that performs the following steps when a program imports a file/module

* Checks to see if the module being imported is already loaded by looking for it in the **sys.modules** table

If not found in the **sys.modules** table i.e. it the module is not already loaded 

* **Finds** the module's file
* **Compiles** it to byte code, if needed
* **Constructs** a module object by running the module's code
* **Stores** the module's instance in the table **sys.modules** table
