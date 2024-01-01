Distributed Web Infrastructure

Description:
This is a distributed web infrastructure designed to alleviate traffic on the primary server by distributing a portion of the load 
to a replica server. The system employs a load balancer, responsible for evenly distributing the workload between the 
primary and replica servers.

Specifics Of Infrastructure:
- **Load Balancer Distribution Algorithm:
  The HAProxy load balancer is configured with the Round Robin distribution algorithm.
  This algorithm operates by cycling through each server behind the load balancer in turns,
  based on their assigned weights. Round Robin is recognized for its fairness, as it evenly
  distributes the processing time among servers. It is a dynamic algorithm, allowing real-time
  adjustments to server weights.

- **Load-Balancer Setup:
  The HAProxy load balancer establishes an Active-Passive setup instead of an Active-Active setup. In an Active-Active configuration, workloads are distributed across all nodes to prevent overloading any single node. This improves throughput and response times due to multiple active nodes. In contrast, an Active-Passive setup designates only one node as active, capable of receiving workloads at a given time. The next node remains passive or on standby, transitioning to an active state if the preceding node becomes inactive.

- **Database Primary-Replica (Master-Slave) Cluster:
  In a Primary-Replica setup, one server acts as the Primary server,
  handling both read and write requests. The Replica server, on the other hand,
   is limited to processing read requests. Data synchronization occurs when the Primary
  server executes a write operation, ensuring consistency between the two servers.

- **Difference Between Primary and Replica Nodes in Application:
  The Primary node manages all write operations required by the site,
  serving as the central hub for data modifications. In contrast, the Replica node is dedicated to
  processing read operations, effectively reducing read traffic directed to the Primary node. This segregation
  of responsibilities enhances the overall efficiency and performance of the application.


  Issues:

  - **Single Points of Failure (SPOFs):
  There are several potential Single Points of Failure in the current infrastructure. The Primary MySQL database server
represents a critical SPOF; if it goes down, the entire site loses the ability to make changes, including user additions
or removals. Additionally, the server housing the load balancer and the application server connecting to the primary database
server are also identified as SPOFs, posing risks to overall system reliability.

- **Security Issues:**
  Security vulnerabilities are evident in the absence of encrypted data transmission. The lack of SSL certificates
  exposes transmitted data to potential spying by hackers. Furthermore, the infrastructure lacks a firewall on any
  server, making it unable to block unauthorized IPs and leaving the system susceptible to unauthorized access and
  potential cyber threats.

- **Lack of Monitoring:**
  The absence of a monitoring system renders the status of each server unknown. Without monitoring, there is no real-time
  insight into the performance, health, or potential issues of individual servers. Monitoring is essential for proactive
  identification and resolution of problems, ensuring the overall stability and reliability of the infrastructure.
