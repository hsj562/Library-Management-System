## Library Management System
#### Description
- **Normal Users**: Users should log in to the system and enter a book code to search for a book. If the book is available, the quantity will be reduced by one on the backend server. The user will then be notified that the book is available.
- **Admin Users**: Users should log in to the system and enter a book code. The remaining quantity of the book will then be displayed to the user.

#### Illustration of the System
<img width="834" alt="Screenshot 2024-05-27 at 10 49 58 PM" src="https://github.com/hsj562/Library-Management-System/assets/48441567/6b28c606-0e6b-4ead-b03b-dbc1cfda1b6c">
(reference: project specification)

#### Explanation of Codes
* **serverM.cpp**: <br/> Server M communicates with both the client and backend servers. It first authenticates the client, then receives book queries from the client, and forwards them to a specific backend server. Finally, Server M receives the book status from the backend server and relays this information to the client.
  
* **serverS.cpp**: <br/> Server S communicates with Server M to handle queries for science books. Upon receiving a query, it determines the book's status (available/not available) and reports this, along with the remaining quantity for admin users, back to Server M.

* **serverL.cpp**: <br/> Server L functions similarly to Server S but is dedicated to queries for literature-related books.
  
* **serverH.cpp**: <br/> Server H, like Server S, specializes in handling queries, but focuses on history-related books.

* **client.cpp**: <br/> Client provides an interface for users to enter their username and password to access the service. After authentication, users can submit book codes for querying. These requests are sent to Server M, which then returns the book status to the user.

#### References
- [Beej's Guide to Network Programming Using Internet Sockets](https://www.beej.us/guide/bgnet/)
- StackOverflow
