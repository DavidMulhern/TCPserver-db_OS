# David Mulhern 
# December 2021, Final Project
# Student ID: G00268549
# Module: Operating Systems
# Lecturer: Mr. Martin Hynes

# Project Type 
Mutli-Threaded TCP server. Demonstrating server/client communication and database maintenance.



# Classes included: 
1.	Client – connection to server, communicate with server
2.	Server – creates a server with a connection port, maintains the live connection in a loop  •	ServerThread – A sequence of communication with the client. Handles requests which it retrieves from SharedMembers class and SharedObject class
3.	SharedMembers – Functionality and maintenance of the members linked list and database (memberinfo.txt)
4.	SharedObject - Functionality and maintenance of the clubentries linked list and database (clubs.txt)
5.	ClubInfo – Constructor of type ClubInfo, with getters
6.	Member - Constructor of type Member, with getters and setters



# Other files (AKA, databases):
1.	Clubs.txt – maintains records of all added clubs, loads all entries on compile time
2.	memberInfo.txt – maintains records of all added members, loads all entries on compile time





# Functionality:
User prompted by a login screen:
	Create a new club login – save to DB
	Login with an existing club details – Protected, must match existing name & id
A menu is displayed to the user
1.	Add a member – Adds member to DB
2.	Update member type/fee – allows update of these details, changes will reflect on linked list and .txt DB
3.	Update member payment status – Allows update of the payment statues, changes will reflect on linked list and .txt DB
4.	Show members who visited in last 14 days – This uses real time. It will make the check from the current date and use two formatters to calculate the difference and return a list that displays to the user.
5.	Show all members who have paid – This will iterate through the linked list and display to the user only members who have “paid”
6.	Remove a member – Allows the user to remove a member via selecting their user id, changes will reflect on linked list and .txt DB
7.	View all registered clubs – This will retrieve all clubs that have been registered from the clubEntries linkedlist and display them to the user
8.	Update a players club info – This must pass two conditions, 1. The member has “paid” and 2. The user has selected a valid ID. Only then will it allow the change of club information, changes will reflect on linked list and .txt DB

	
	

# Points of interest:
1.	The Linked lists and text files are always in sync, if any create, updates or deletes occur, the text file gets wiped ( nukeFile() ) and reconstructed. Linklist also gets updated accordingly.
2.	As mentioned before, the program uses real time solutions, checking the last 14 days can be used at any time and reflect accurately using the current date of program execution.
3.	Upon closing the application ( pressing 9 in menu ), the finally block gets hit. This should demonstrate a correct “logging out” of the program, closing sockets and streams before exiting.
4.	Any functionality that creates, deletes or updates information sits within synchronized blocks, ensuring a thread safe environment, should multiple users be accessing the server at a given time.

