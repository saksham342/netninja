# netninja
This script, netninja.py, is a versatile network tool that allows for file uploads, command execution, and interactive command shells over a network connection.

This script, named `netninja.py`, is a versatile network tool that can be used for a variety of purposes such as uploading files, executing commands, and establishing an interactive command shell over a network connection. The script begins by importing necessary modules, including `sys`, `socket`, `getopt`, `threading`, and `subprocess`. Several global variables are defined to control the script's behavior, such as whether to listen for incoming connections, execute a command, upload a file, or initialize a command shell. The `usage` function provides detailed instructions and examples on how to use the script, including command-line options for specifying the target host, port, and various operational modes.

The `main` function parses command-line arguments to set the appropriate global variables and determine the script's behavior. If the script is set to send data from standard input, it calls the `client_sender` function to handle the client-side operations. If the script is set to listen for incoming connections, it starts the `server_loop` function to handle server-side operations.

The `client_sender` function establishes a connection to the target host and port, sends any initial data, and then enters a loop to send and receive data to and from the server, handling exceptions as they occur.

The `server_loop` function sets up a server socket to listen on the specified target and port. When a client connects, it spawns a new thread to handle the client's requests using the `client_handler` function.

The `run_command` function executes a given shell command and returns its output, handling any errors that occur during execution.

The `client_handler` function processes the client's requests based on the global variables. If an upload is requested, it reads the incoming file data and saves it to the specified destination, sending a success or failure message back to the client. If a command execution is requested, it runs the command and sends the output back to the client. If an interactive command shell is requested, it enters a loop to receive and execute commands from the client, sending the results back each time.

Overall, this script provides a flexible framework for remote file uploads, command execution, and interactive shells, making it a powerful tool for network administrators and penetration testers. However, due to the security implications, it should be used with caution and only in authorized and controlled environments.
