### UNDERSTANDING CLIET SERVER ARCHITECTURE

## Understanding Client Server Architecture with MySQL

This is an architecture where two or more computers are connected togther over a network to send and receive requests between one another. Each machine has it's own role in the network; **Client** is the machine that sends requests while **Server** is the maching responding (serving) to the requests.

see the diagram below demonstarting this architecture. A client machine is trying to access a website using a web browser or 'curl' command. It sends the HTTP request to a Web Server (Apache, Nginx, IIS or any other) over the internet.

![alt text](<Images/client server architecture.png>)

Adding a Database Server to our architecture will give us another picture like this below:

![alt text](<Images/client server archi with DB.png>)

In this case, the Web Server has a role of a Client that connects to a Database Server to read from/write to it. Databases like MySQL, MongoDB, Oracle, SQL Server etc. The communication between them happens over a local network and can also be via internet but it is common practice to have the DB Server and Web Server close to each other within the same local network.

The diagram above is also a typical We Stack Architecture which we have seen and implemented before (LAMP, LEMP, MEAN, MERN).