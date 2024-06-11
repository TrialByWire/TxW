Trial By Wire 
Author:  KH 


BHP Net Tool
This repository contains a Python implementation of a NetCat-like tool inspired by the "Black Hat Python" book. The tool can be used for command execution, file upload, and as a simple command shell.

Features
Execute commands on a remote system
Upload files to a remote system
Open a command shell on a remote system
Connect to a remote system and interact with it
Usage
To use this tool, you need to have Python installed on your system. You can run the script from the command line with various options as described below.

Command Line Arguments
-c, --command: Open a command shell
-e, --execute: Execute a specified command
-l, --listen: Listen for incoming connections
-p, --port: Specify the port to use (default: 5555)
-t, --target: Specify the target IP address (default: 192.168.1.203)
-u, --upload: Upload a file to the target system
Examples
Command Shell
Listen for incoming connections and open a command shell:


Copy command
python netcat.py -t 192.168.1.108 -p 5555 -l -c
File Upload
Listen for incoming connections and upload a file:

Copy command
python netcat.py -t 192.168.1.108 -p 5555 -l -u=mytest.txt
Execute Command
Listen for incoming connections and execute a command:

Copy command
python netcat.py -t 192.168.1.108 -p 5555 -l -e="cat /etc/passwd"
Send Data
Send text to a server:

Copy command
echo 'ABC' | python netcat.py -t 192.168.1.108 -p 135
Connect to Server
Connect to a server:

Copy command
python netcat.py -t 192.168.1.108 -p 5555
Implementation
The main functionality is implemented in the NetCat class, which supports both sending and receiving data, depending on the provided command line arguments. The execute function is used to run shell commands and return their output.

NetCat Class
__init__(self, args, buffer=None): Initializes the NetCat object with arguments and an optional buffer.
run(self): Runs the NetCat tool either in listen mode or send mode based on the provided arguments.
send(self): Connects to a target and sends data.
listen(self): Listens for incoming connections.
handle(self, client_socket): Handles client connections, supporting command execution, file upload, and command shell functionalities.
Dependencies
Python 3
argparse: For parsing command line arguments
socket: For network communication
shlex: For parsing shell commands
subprocess: For executing shell commands
sys: For interacting with the system
textwrap: For formatting text
threading: For handling multiple connections
License
This project is licensed under the MIT License. See the LICENSE file for details.

Author
This tool was implemented following the guidelines provided in the "Black Hat Python" book.

Feel free to fork this repository and modify the tool according to your needs. Contributions are welcome!
