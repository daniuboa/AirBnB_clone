# AirBnB_clone - The console

## Contributors

- [Daniel Uboa](https://github.com/daniuboa)

- [Leila Yesufu](https://github.com/leilayesufu)

## Description
This project is a complete web application, intergrating database storage, a backend API, and front-end interfacing in a clone of AirBnB.

This project currently only implements the backend console.

## Classes
The project utilizes the following classes:

|     | BaseModel | FileStorage | User | State | City | Amenity | Place | Review |
| --- | --------- | ----------- | -----| ----- | -----| ------- | ----- | ------ |
| **PUBLIC INSTANCE ATTRIBUTES** | `id`<br>`created_at`<br>`updated_at` | | Inherits from `BaseModel` | Inherits from `BaseModel` | Inherits from `BaseModel` | Inherits from `BaseModel` | Inherits from `BaseModel` | Inherits from `BaseModel` |
| **PUBLIC INSTANCE METHODS** | `save`<br>`to_dict` | `all`<br>`new`<br>`save`<br>`reload` | "" | "" | "" | "" | "" | "" |
| **PUBLIC CLASS ATTRIBUTES** | | | `email`<br>`password`<br>`first_name`<br>`last_name`| `name` | `state_id`<br>`name` | `name` | `city_id`<br>`user_id`<br>`name`<br>`description`<br>`number_rooms`<br>`number_bathrooms`<br>`max_guest`<br>`price_by_night`<br>`latitude`<br>`longitude`<br>`amenity_ids` | `place_id`<br>`user_id`<br>`text` | 
| **PRIVATE CLASS ATTRIBUTES** | | `file_path`<br>`objects` | | | | | | |

### Storage

All the classes are handled by the `Storage` engine in the [`FileStorage`](./models/engine/file_storage.py) Class.

## Technologies Used

- `Ubuntu`
- `Bash`
- `Python`
- `Vim`

#### Styles guideline

- [pycodestyle (version 2.7.\*)](https://pypi.org/project/pycodestyle/)
- [PEP8](https://pep8.org/)

All the development and testing was runned over an operating system Ubuntu 20.04 LTS using Python 3.8.3 programming language. The editors used were VIM and VSCode. Control version using Git.

### Execution
The console can be run both interactively and no-interactively.

In interactive mode, run the file `console.py` by itself:

```bash
$ ./console.py
(hbnb) help

Document commands (typehelp <topic></topic>):
=============================================
EOF help guit

(hbnb)
(hbnb)
(hbnb) quit
$
```

To quit the console, enter the command `quit`, or input an EOF signal
(`control+D`).

In non-interactive mode, pipe any command(s) into an execution of file `console.py` at the command line.

```bash
$ echo "help" | ./console.py
(hbnb)

Document commands (types help <topic></topic>):
===============================================
EOF help quit
(hbnb)
$
$ cat test_help | ./console.py
(hbnb)
$
```

## Testing

All the tests are defined in the `tests` folder.

### Documentation

- Modules:

```python
python3 -c 'print(__import__("my_module").__doc__)'
```

- Classes:

```python
python3 -c 'print(__import__("my_module").MyClass.__doc__)'
```

- Functions (inside and outside a class):

```python
python3 -c 'print(__import__("my_module").my_function.__doc__)'
```

and

```python
python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'
```

### Python Unit Tests

- unittest module
- File extinsion `.py`
- Files and folders start with `test_`
  *Organization:for `models/base.py`, unit tests in:
  `tests/test_models/test_base.py`
  *Execution command: `python3 -m unittest discocer tests`
- or: `python3 -m unittest tests/test_models/test_base.py`

### run test in interactive mode

```bash
echo "python3 -m unittest discover tests" |bash
```

### run test in non-interactive mode

To run the tests in non-interactive mode, and discover all the test, you can use the command:

```bash
python3 -m unittest discover tests
```

## Usage

- Start the console in interactive mode:

```bash
$ ./console.py
(hbnb)
```

- Use help to see the available commands:

```bash
(hbnb) help

Documented commands (type help <topic></topic>):
================================================
EOF all count create destroy help quit show update

(hbnb)
```

- Quit the console:

```bash
(hbnb) quit
$
```

###Console Commands

> The commands are displayed in the following format

- Command / usage / example with output\*

> _Create a new instance of a given class. The class' ID is printed and the instance is saved to the file file.json._

```bash
create <class>

```

```bash
(hbnb) create BaseModel
6cfb47c4-a434-4da7-ac03-2122624c3762
(hbnb)
```

- Show

```bash
show <class> <id>
```

```bash
(hbnb) show BaseModel 6cfb47c4-a434-4da7-ac03-2122624c3762
[BaseModel] (a) [BaseModel]
(6cfb47c4-a434-4da7-ac03-2122624c3762) {'id': '6cfb47c4-a434-4da7-ac03-2122624c3762', 'created_at': datetime.datetime(2022, 8, 29, 3, 28, 45, 571360), 'updated_at': datetime.dayetime(2022, 8, 28, 45, 571360)}
(hbnb)
```

- Destroy

> - Delets an instance of a given class with a given ID.\* > _Update the file.json_

```bash
(hbnb) create User
0c98d2b8-7ffa-42b7-8009-d9d54b69a472
(hbnb) destroy User 0c98d2b8-7ffa-42b7-8009-d9d54b69a472
(hbnb) show User 0c98d2b8-7ffa-42b7-8009-d9d54b69a472
** no instance found **
(hbnb)
```

- all

> _Prints all string representation of all instances of a given class._ > _If no class is passed, all classes are printed._

```bash
(hbnb) create BaseModel
e45ddda9-eb80-4858-99a9-226d4f08a629
(hbnb) all BaseModel
["[BaseModel] (4c8f7ebc-257f-4ed1-b26b-e7aace459897) [BaseModel] (4c8f7ebc-257f-4ed1-b26b-e7aace459897) {'id': '4c8f7ebc-257f-4ed1-b26b-e7aace459897', 'created_at': datetime.datetime(2021, 11, 13, 22, 19, 19, 447155), 'updated_at': datetime.datetime(2021, 11, 13, 22, 19, 19, 447257), 'name': 'My First Model', 'my_number': 89}"]
["[BaseMode
```

- count

> _Prints the number of instances of a given class._

```bash
(hbnb) create City
4e01c33e-2564-42c2-b61c-17e512898bad
(hbnb) create City
e952b772-80a5-41e9-b728-6bc4dc5c21b4
(hbnb) count City
2
(hbnb)
```

- update

> _Updates an instance based on the class name, id, and kwargs passed._ > _Update the file.json_

```bash
(hbnb) create User
1afa163d-486e-467a-8d38-3040afeaa1a1
(hbnb) update User 1afa163d-486e-467a-8d38-3040afeaa1a1 email "uboadaniel@gmail.com"
(hbnb) show User 1afa163d-486e-467a-8d38-3040afeaa1a1
[User] (s) [User] (1afa163d-486e-467a-8d38-3040afeaa1a1) {'id': '1afa163d-486e-467a-8d38-3040afeaa1a1', 'created_at': datetime.datetime(2021, 11, 14, 23, 42, 10, 502157), 'updated_at': datetime.datetime(2021, 11, 14, 23, 42, 10, 502186), 'email': 'uboadaniel@gmail.com'}
(hbnb)

```
