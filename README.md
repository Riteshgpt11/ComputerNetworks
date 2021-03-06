# Secure Client Server Communication through SSL
High- level Approach:

This is a client-side program that makes a socket connection with the server,sends a HELLO message, solves the questions asked by the server and sends it back to the server.
The program uses split function to distinguish between the terms send by the server and perform the computations accordingly. 
The server after receiving the answers of all the questions sends a secret flag to the client written in ASCII code with a BYE message.
The program also implements SSL which make a secured connection with the server, follows the same steps but receives a different secret flag.

Code Implementation:
This program imports the following modules:
	socket: To build a socket connection with the server
	AF_INET: To build a tuple of Address Family used to assign Hostname and Port Number
	SOCK_STREAM: For using TCP Connection
	ssl: For secured connection with the server using SSL
	sys: For taking command-line arguments
	wrap_socket: For wrapping the socket to support SSL

Challenges Faced:
	Building up connection with the server.
	Implementing SSL

Testing:

Without SSL:
	./client cs5700sp17.ccs.neu.edu 001280361 - NO error, Flag received
	./client -p 27993 cs5700sp17.ccs.neu.edu 001280361 - NO error, Flag received
	./client -p 2793 cs5700sp17.ccs.neu.edu 001280361 - Error-Can't connect to this port
	./client -p 27993 cs5700sp17.ccs.neu.edu 00128036 - Incorrect NU ID
	./client -p 2799 cs5700sp17.ccs.neu.edu 00128036 - Error-Can't connect to this port
With SSL
	./client -s cs5700sp17.ccs.neu.edu 001280361 - NO error, Flag received
	./client -p 27994 -s cs5700sp17.ccs.neu.edu 001280361 - NO error, Flag received 
	./client -p 2799 -s cs5700sp17.ccs.neu.edu 001280361 - Error-Can't connect to this port
	./client -p 27994 -s cs5700sp17.ccs.neu.edu 00128036 - Incorrect NU ID
	./client -p 2799 -s cs5700sp17.ccs.neu.edu 00128036 - Error-Can't connect to this port
