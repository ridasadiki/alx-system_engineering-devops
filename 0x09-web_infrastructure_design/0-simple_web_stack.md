Simple Web Stack

Description:
This web infrastructure is basic, hosting a website accessible through www.foobar.com. 
The server lacks firewalls and SSL certificates to safeguard its network. Resource sharing, including CPU,
RAM, and SSD, is implemented among the server's components, such as the database and application server.

Specifics Of Infrastructure:

- **Server Definition:**
  A server is a computing system, encompassing both hardware and software components,
  designed to provide services to other computers, commonly known as clients.

- **Domain Name Functionality:**
  The domain name serves as a human-friendly alias for an IP address. For instance,
  www.wikipedia.org offers a more recognizable and memorable alternative to the IP address 91.198.174.192.
  The mapping between IP addresses and domain name aliases is maintained in the Domain Name System (DNS).

- **DNS Record Type for www.foobar.com:**
  The DNS record type utilized by www.foobar.com is an A record. Verification can be done through the command
   "dig www.foobar.com." In this design, an Address Mapping record (A Record) is employed, storing a hostname
  and its corresponding IPv4 address.

- **Web Server's Role:**
  The web server, whether in the form of software or hardware, is responsible for handling requests via HTTP
  or secure HTTP (HTTPS) and responding with the content of the requested resource or an error message.

- **Application Server's Function:**
  The application server's primary role is to install, operate, and host applications and associated services
  for end-users, IT services, and organizations. It facilitates the hosting and delivery of sophisticated consumer
  or business applications.

- **Database Purpose:**
  The database functions to maintain a well-organized collection of information that can be easily accessed, managed,
  and updated. It serves as a repository for structured data.

- **Server-Client Communication:**
  Communication between the server and the client, representing the user's computer requesting the website, takes
  place over the internet network using the TCP/IP protocol suite.
