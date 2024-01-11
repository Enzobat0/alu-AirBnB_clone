AirBnB clone - The console

The AirBnB Clone Project

https://camo.githubusercontent.com/f471b8e4f529b2586e8ff5597df432ff096a8f4b62f831d8dc7c25f39363dbee/68747470733a2f2f7777772e706e676974656d2e636f6d2f70696d67732f6d2f3133322d313332323132355f7472616e73706172656e742d6261636b67726f756e642d616972626e622d6c6f676f2d68642d706e672d646f776e6c6f61642e706e67

Project Description

This project is a clone of the Airbnb website. The purpose of it is to get hands-on experience by building the first full web application. We'll start by creating the console first.
Data (python objects) generated are stored in a JSON file and can be accessed with the help of the JSON module in python
Description of the command interpreter:
The interface of the application is just like the Bash shell except that this has a limited number of accepted commands that were solely defined for the usage of the AirBnB website.
This command line interpreter serves as the frontend of the web application where users can interact with the backend which was developed with Python OOP programming.
Some of the commands available are:
-use
-show
-create
-update
-destroy
-count
As part of the implementation of the command line interpreter coupled with the backend and file storage system, the following actions can be performed:
Creating new objects (ex: a new User or a New Place)
Retrieving an object from a file, a database, etc…
Doing operations on objects (count, compute stats, etc…)
Updating attributes of an object
Destroying an object

How to start it:
These instructions will get you a copy of the project up and running on your local machine (Linux distro) for development and testing purposes.

Installing:
You will need to clone the repository of the project from Github. This will contain the simple shell program and all of its dependencies.
git clone git@github.com:Enzobat0/alu-AirBnB_clone.git
After cloning the repository you will have a folder called AirBnB_clone. In here there will be several files that allow the program to work.

/console.py: The main executable of the project, is the command interpreter.
models/engine/file_storage.py: Class that serializes instances to a JSON file and deserializes JSON file to instances
models/__ init __.py: A unique FileStorage instance for the application
models/base_model.py: Class that defines all common attributes/methods for other classes.
models/user.py: User class that inherits from BaseModel
models/state.py: State class that inherits from BaseModel
models/city.py: City class that inherits from BaseModel
models/amenity.py: Amenity class that inherits from BaseModel
models/place.py: Place class that inherits from BaseModel
models/review.py: Review class that inherits from BaseModel

How to use it:
It can work in two different modes:
Interactive and Non-interactive.
In Interactive mode, the console will display a prompt (hbnb) indicating that the user can write and execute a command. After the command is run, the prompt will appear again a wait for a new command. This can go indefinitely as long as the user does not exit the program.
$ ./console.py
(hbnb) help
Documented commands (type help <topic>):
========================================
EOF help quit
(hbnb) 
(hbnb) 
(hbnb) quit
$
In Non-interactive mode, the shell will need to be run with a command input piped into its execution so that the command is run as soon as the Shell starts. In this mode, no prompt will appear, and no further input will be expected from the user.
$ echo "help" | ./console.py
(hbnb)
Documented commands (type help <topic>):
========================================
EOF help quit
(hbnb) 
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)
Documented commands (type help <topic>):
========================================
EOF help quit
(hbnb) 
$
Format of Command Input
To give commands to the console, these will need to be piped through an echo in case of Non-interactive mode.
In Interactive Mode, the commands will need to be written with a keyboard when the prompt appears and will be recognized when an enter key is pressed (new line). As soon as this happens, the console will attempt to execute the command through several means or will show an error message if the command doesn't run successfully. In this mode, the console can be exited using the CTRL + D combination, CTRL + C, or the command quit or EOF.
Arguments
Most commands have several options or arguments that can be used when executing the program. For the Shell to recognize those parameters, the user must separate everything with spaces.
Example:
user@ubuntu:~/AirBnB$ ./console.py
(hbnb) create BaseModel
8faafa-89012-7851f-87b6-910505c559af
user@ubuntu:~/AirBnB$ ./console.py
or
user@ubuntu:~/AirBnB$ ./console.py $ echo "create BaseModel" | ./console.py
(hbnb)
8faafa-89012-7851f-87b6-910505c559af
(hbnb)
user@ubuntu:~/AirBnB$ ./console.py
Available commands and what they do
The recognizable commands by the interpreter are the following:
CommandDescription
quit or EOF	Exits the program
Usage	By itself
-----	-----
help	Provide a text describing how to use a command.
Usage	By itself --or-- help <command>
-----	-----
create	Creates a new instance of a valid Class, saves it (to the JSON file), and prints the id. Valid classes are BaseModel, User, State, City, Amenity, Place, and Review.
Usage	create <class name>
-----	-----
show	Prints the string representation of an instance based on the class name and id
Usage	show <class name> <id> --or-- <class name>.show(<id>)
-----	-----
destroy	Deletes an instance based on the class name and id (saves the change into a JSON file).
Usage	destroy <class name> <id> --or-- .destroy()
-----	-----
all	Prints all string representation of all instances based or not on the class name.
Usage	By itself or all <class name> --or-- <class name>.all()
-----	-----
Update updates an instance based on the class name and ID by adding or updating an attribute (saves the changes into a JSON file).
----- -----
Usage	update <class name> <id> <attribute name> "<attribute value>" ---or--- <class name>.update(<id>, <attribute name>, <attribute value>) --or-- <class name>.update(<id>, <dictionary representation>)
-----	-----
count	Retrieve the number of instances of a class.
Usage	<class name>.count()
