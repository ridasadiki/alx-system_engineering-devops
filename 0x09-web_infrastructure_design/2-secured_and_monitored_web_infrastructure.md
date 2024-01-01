Secured and Monitored Web Infrastructure

Description:

This is a 3-server web infrastructure that is secured, monitored, and serves encrypted traffic.

Specifics Of Infrastructure:

- **Purpose of Firewalls:
  Firewalls serve the crucial purpose of safeguarding the network, particularly the web servers, against unwanted and
  unauthorized access. They act as intermediaries between the internal and external networks, blocking incoming traffic
  that matches predefined criteria. By establishing a barrier, firewalls prevent malicious users from infiltrating the network,
   enhancing overall security.

- **Purpose of SSL Certificates:**
  SSL certificates play a vital role in securing the traffic between web servers and the external network.
  They encrypt data to prevent unauthorized access by potential threats, such as man-in-the-middle attacks (MITM) and
  network sniffers attempting to intercept sensitive information. SSL certificates ensure privacy, integrity, and
  identification, making data transmission more secure and protecting valuable information from potential breaches.

- **Purpose of Monitoring Clients:**
  Monitoring clients are instrumental in overseeing the servers and the external network. They analyze server performance
  and operations, measuring overall health and promptly alerting administrators to deviations from expected performance.
  Monitoring tools observe servers, providing key metrics that offer insights into operations. These tools automatically
  test server accessibility, measure response times, and issue alerts for various issues, including corrupt or missing files,
  security vulnerabilities or violations, and other potential problems. Monitoring clients enable administrators to proactively
   manage and maintain the infrastructure's health and reliability.
Issues:
- **SSL Termination at Load Balancer:
-   While terminating SSL at the load balancer provides encryption up to that point, it leaves the traffic between the load
-   balancer and the web servers unencrypted. To ensure end-to-end encryption, SSL termination should be extended to the web
-    servers, enhancing the overall security of data transmission.

- **Single MySQL Server Issue:
  Relying on a single MySQL server poses scalability challenges and introduces a potential single point of failure for the web
   infrastructure. A more robust solution involves implementing a MySQL cluster or replication setup, distributing the load and
  providing redundancy to enhance scalability and fault tolerance.

- **Uniform Server Components Challenge:
  Using servers with identical components may lead to resource contention, as these components (CPU, Memory, I/O) compete
  for resources on the server. This contention can result in poor performance and difficulties in pinpointing the source of
  issues. Adopting a diverse server setup or implementing load balancing at the component level can help address resource
  contention and enhance scalability.

- **Difficulty in Scalability:**
  A homogeneous server setup, where all servers have the same components, can impede scalability. Scaling becomes challenging
  due to resource constraints and limitations. A more scalable approach involves deploying a heterogeneous infrastructure,
  utilizing specialized servers for specific tasks, and implementing scalable architectures, such as microservices, to meet
  growing demands.
