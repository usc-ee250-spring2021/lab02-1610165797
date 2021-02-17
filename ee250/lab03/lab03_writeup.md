Question 1: How did the reliability of UDP change when you added 50% loss to your local environment? Why did this occur?

There's about 50% chances that the message won't show up on the server. This is because UDP protocol doesn't care if the message has been succssfully received.

Question 2: How did the reliability of TCP change? Why did this occur?

All of the messages are finally sent regardless of the loss percentage. This occurs because TCP will ensure that all messages are sent; if not, the server will keep sending the message until it's succssfully received.

Question 3: How did the speed of the TCP response change? Why might this happen?

The speed is decreased when the loss is added. This happens because the client resends the message until the server receives it. Therefore, it might take longer for the server to succssfully receive a message.


1.
argc is the count of I/O variables
argv is the list of input files for this program

2.
In Unix,  FD is is an indicator used to access a file or other I/O recourses, including network socket.
FD index into a per-process file descriptor table maintained by the kernel, that indexes into a system-wide table of files opened by all processes, called the file table.
This table stores information about the mode with which the file is opened, liking reading, writing...

3.
a struct is a data structure in C++, kind of like class but not exactly the same(more public to users).
The following is the definition of sockaddr_in
     struct sockaddr_in {
#if ...
  short          sin_family;
#else
  ADDRESS_FAMILY sin_family;
#endif
  USHORT         sin_port;
  IN_ADDR        sin_addr;
  CHAR           sin_zero[8];
} SOCKADDR_IN, *PSOCKADDR_IN;

4.
domain: an integere describing the communication domain AF_INET is IPv4 Protocol
Type: communnication type, SOCK_STREAM is TCP
protocol: Protocol values for IP, which is 0
When created succssfully, socket returns a non-negative value; when unsuccessful, it returns -1

5.
The input parameters for bind() is the socket, the address, and its size
The input for listen() is the socket and the backlog argument

6.
We use while(1) to constantly search and receive messages
If there are multiple connections to handle, the code might not function properly since there's only one socket created for connection

7.
The fork() function creates a child socket for listening every time a socket a connected to a client; therefore, it always has at least one spare socket 
Fork can be used to creat a new socket each time a connection is made so that the while(1) loop can handle multiple connections

8.
A system call is a code that interacts with the kernel to request a service from it
In the case of bind(), it is calling to associate a socket with a known address
In the case of listen(), it is setting the serever in the listen mode, which is the mode before establishing final connection

Link to Demo Video:
https://drive.google.com/file/d/1QkVPfaSAbgLYJEg4WrtMAdu7Gad0omXA/view?usp=sharing

