# AirBnB_clone

# AirBnB clone - The console

##Introduction

Project to build a clone of [AirBnB](https://www.airbnb.com/).

The console is a command interpreter to manage objects abstraction between objects and how they are stored.

To see the fundamental background of the project visit the [Wiki](https://github.com/ralexrivero/AirBnB_clone/wiki).

The console willl perform the following tasks:

* create a new object
* retrive an object from a file
* do operations on objects such as updating the content
* destroy an object(i.e delete)

### Storage

All the classes are handled by the `Storage` engine in the `FileStorage` Class.

## Environment

<!-- ubuntu -->
<a href="https://ubuntu.com/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Ubuntu&color=E95420&logo=Ubuntu&logoColor=E95420&labelColor=2F333A" alt="Suite CRM"></a> <!-- bash --> <a href="https://www.gnu.org/software/bash/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=GNU%20Bash&color=4EAA25&logo=GNU%20Bash&logoColor=4EAA25&labelColor=2F333A" alt="terminal"></a> <!-- python--> <a href="https://www.python.org" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Python&color=FFD43B&logo=python&logoColor=3776AB&labelColor=2F333A" alt="python"></a> </a> <!-- vim --> <a href="https://www.vim.org/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Vim&color=019733&logo=Vim&logoColor=019733&labelColor=2F333A" alt="Suite CRM"></a> <!-- vs code --> <a href="https://code.visualstudio.com/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Visual%20Studio%20Code&color=5C2D91&logo=Visual%20Studio%20Code&logoColor=5C2D91&labelColor=2F333A" alt="Suite CRM"></a> </a><!-- git --> <a href="https://git-scm.com/" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=Git&color=F05032&logo=Git&logoColor=F05032&labelColor=2F333A" alt="git distributed version control system"></a> <!-- github --> <a href="https://github.com" target="_blank"> <img height="" src="https://img.shields.io/static/v1?label=&message=GitHub&color=181717&logo=GitHub&logoColor=f2f2f2&labelColor=2F333A" alt="Github"></a>
 <!-- Style guidelines -->
* Style guidelines:
  * [pycodestyle (version 2.8.0)](https://pypi.org/project/pycodestyle/)
  * [PEP8](https://pep8.org/)

All the development and testing was runned over an operating system Ubuntu 20.04 LTS using programming language Python 3.8.3. The editors used were VIM 8.1.2269, VSCode 1.6.1 and Atom 1.58.0 . Control version using Git 2.25.1.

## Installation

```bash
git clone https://github.com/NicolasMabeleng/AirBnB_clone.git
```

change to the `AirBnb` directory and run the command:

```bash
 ./console.py
```

### Execution

In interactive mode

```bash
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb)
(hbnb)
(hbnb) quit
$
```

in Non-interactive mode

```bash
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
```

## Testing


All the test are defined in the `tests` folder.


### Documentation

* Modules:

```python
python3 -c 'print(__import__("my_module").__doc__)'
```

* Classes:

```python
python3 -c 'print(__import__("my_module").MyClass.__doc__)'
```

* Functions (inside and outside a class):

```python
python3 -c 'print(__import__("my_module").my_function.__doc__)'
```

and

```python
python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'
```

### Python Unit Tests

* unittest module
* File extension ``` .py ```
* Files and folders star with ```test_```
* Organization:for ```models/base.py```, unit tests in: ```tests/test_models/test_base.py```
* Execution command: ```python3 -m unittest discover tests```
* or: ```python3 -m unittest tests/test_models/test_base.py```

### run test in interactive mode

```bash
echo "python3 -m unittest discover tests" | bash
```

### run test in non-interactive mode

To run the tests in non-interactive mode, and discover all the test, you can use the command:

```bash
python3 -m unittest discover tests
```


## Usage

* Start the console in interactive mode:

```bash
$ ./console.py
(hbnb)
```

* Use help to see the available commands present in the console:

```bash
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  all  count  create  destroy  help  quit  show  update

(hbnb)
```

* Quit the console:

```bash
(hbnb) quit
$
```

### Commands

> The commands are displayed in the following format *Command / usage / example with output*

* Create

> *Creates a new instance of a given class. The class' ID is printed and the instance is saved to the file file.json.*

```bash
create <class>

```

```bash
(hbnb) create BaseModel
1f37ccf9-08e2-4aed-8e31-879a5a35ec1a
(hbnb)
```

* Show

```bash
show <class> <id>
```

```bash
(hbnb) show BaseModel 1f37ccf9-08e2-4aed-8e31-879a5a35ec1a
[BaseModel] (1f37ccf9-08e2-4aed-8e31-879a5a35ec1a) {'id': '1f37ccf9-08e2-4aed-8e31-879a5a35ec1a', 'created_at': datetime.datetime(2023, 10, 30, 0, 58, 35, 635286), 'updated_at': datetime.datetime(2023, 10, 30, 0, 58, 35, 635333)}
(hbnb)
```

* Destroy

> *Deletes an instance of a given class with a given ID.*
> *Update the file.json*

```bash
(hbnb) create User
1f26420f-3fbb-4a6a-a239-60f1c1ee8b08
(hbnb) destroy User 1f26420f-3fbb-4a6a-a239-60f1c1ee8b08
(hbnb) show User 1f26420f-3fbb-4a6a-a239-60f1c1ee8b08
** no instance found **
(hbnb)
```

* all

> *Prints all string representation of all instances of a given class.*
> *If no class is passed, all classes are printed.*

```bash
(hbnb) create BaseModel
3cda7c63-89f0-466a-b038-254e3b70b0df
(hbnb) all BaseModel
["[BaseModel] (1f37ccf9-08e2-4aed-8e31-879a5a35ec1a) {'id': '1f37ccf9-08e2-4aed-8e31-879a5a35ec1a', 'created_at': datetime.datetime(2023, 10, 30, 0, 58, 35, 635286), 'updated_at': datetime.datetime(2023, 10, 30, 0, 58, 35, 635333)}", "[BaseModel] (3cda7c63-89f0-466a-b038-254e3b70b0df) {'id': '3cda7c63-89f0-466a-b038-254e3b70b0df', 'created_at': datetime.datetime(2023, 10, 30, 1, 3, 50, 920788), 'updated_at': datetime.datetime(2023, 10, 30, 1, 3, 50, 920811)}"]
```

* count

> *Prints the number of instances of a given class.*

```bash
(hbnb) create City
81c08919-04f4-4a63-ae4b-eff3bc7f8be2
(hbnb) create City
cc9b90a7-bd56-4fa4-8873-c35c598e505e
(hbnb) create City
67db2b2b-b1d1-413a-8fc3-5e2c395a1a85
(hbnb) count City
3
(hbnb)
```

* update

> *Updates an instance based on the class name, id, and kwargs passed.*
> *Update the file.json*

```bash
(hbnb) create User
b95367e0-b526-4bf9-86cf-bb04236ab79d
(hbnb) update User
** instance id missing **
(hbnb) update User b95367e0-b526-4bf9-86cf-bb04236ab79d email "mabelengnicolas@outlook.com"
(hbnb) show User b95367e0-b526-4bf9-86cf-bb04236ab79d
[User] (b95367e0-b526-4bf9-86cf-bb04236ab79d) {'id': 'b95367e0-b526-4bf9-86cf-bb04236ab79d', 'created_at': datetime.datetime(2023, 10, 30, 1, 7, 49, 593521), 'updated_at': datetime.datetime(2023, 10, 30, 1, 8, 56, 794518), 'email': 'mabelengnicolas@outlook.com'}
(hbnb)

```
## Authors
<details>
    <summary>Nicolas Mabeleng</summary>
    <ul>
    <li><a href="https://www.github.com/NicolasMabeleng">Github</a></li>
    <li><a href="mailto:mabelengnicolas@outlook.com">e-mail</a></li>
    </ul>
</details>

