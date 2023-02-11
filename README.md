# AirBnB clone - The console

## Description

this AirBnB clone project is the first step towards building a first full web application.
This first step consists of a custom command-line interface for data management, and the base classes for the storage of this data.
create a new object (ex: a new User or new Place)
retrieve an object from a file, a database, etc..
update attributes of an object
do operations on objects (count, compute stats, etc..)
destroy an object

## Execution

the console works both in interactive mode and non-interactive mode
 shell works like this in interactive mode:

$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb) 
(hbnb) 
(hbnb) quit
$
shell works like this in non-interactive mode:

$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$

# Requirements

## Python Scripts
all files will be interpreted/compiled on Ubuntu 14.04 LTS using python3 (version 3.4.3)
code will use PEP 8 style (version 1.7 or higher)
all modules will have documentation (python3 -c 'print(__import__("my_module").__doc__)')
all classes will have documentation (python3 -c 'print(__import__("my_module").MyClass.__doc__)')
all functions will have documentation (python3 -c 'print(__import__("my_module").my_function.__doc__)' and python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)')
## Python Unit Tests

all test files are inside a folder tests
all test files and folders start by test_
file organization in the tests folder is same as project (for models/base_model.py unit tests must be in tests/test_models/test_base_model.py)
all tests will be executed by this command: python3 -m unittest discover tests
all modules will have documentation
all classes will have documentation
all functions will have documentation

## How To Use

Command | Example
--------|-------
Run the console | ```./console.py```
Quit the console | ```(hbnb) quit```
Display the help for a command | ```(hbnb) help <command>```
Destroy an object | ```(hbnb) destroy <class> <id>```
Create an object (prints its id)| ```(hbnb) create <class>```

## File storage

The folder engine manages the serialization and deserialization of all the data, following a JSON format.

A FileStorage class is defined in file_storage.py with methods to follow this flow: <object> -> to_dict() -> <dictionary> -> JSON dump -> <json string> -> FILE -> <json string> -> JSON load -> <dictionary> -> <object>

The init.py file contains the instantiation of the FileStorage class called storage, followed by a call to the method reload() on that instance. This allows the storage to be reloaded automatically at initialization, which recovers the serialized data.
## Tests
All the code is tested with the unittest module. The test for the classes are in the test_models folder.


