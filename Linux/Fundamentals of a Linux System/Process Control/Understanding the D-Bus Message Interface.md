# Understanding the D-Bus Message Interface
D-Bus is a message bus that allows for processes to communicate through a message bus.

## Understanding D-Bus
D-Bus was developed for Linux desktops to make communications between applications more efficient.
The challenge in these environments is that many processes need to establish one-on-one relations and that is not very efficient.
D-Bus provides a software bus abstraction that creates one virtual channel that can be used for communications between a group of processes.
Using a D-Bus ensures that all processes can connect directly to one another
Typically, Linux implements multiple busses: a single system bus that is available to all users and processes and a session bus for each user login system
