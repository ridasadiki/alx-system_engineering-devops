Scaled Up Web Infrastructure

Description:
- **Addition of a New Server:
  The inclusion of an additional server serves several purposes. Firstly, it allows for the separation of each component
  (web server - Nginx, application server - code base, and database - MySQL) onto their own dedicated servers. This separation
  enhances modularity, simplifies maintenance, and provides better isolation for troubleshooting and updates. Additionally,
  having one extra server with all components acts as a backup, ensuring redundancy in case of component or server failures,
   thereby improving overall system reliability.

- **Incorporation of Load Balancer:
  The introduction of an extra load balancer is essential for handling increased traffic across the entire infrastructure.
  Load balancers distribute incoming requests among multiple servers, optimizing resource utilization and preventing any single
  server from becoming a bottleneck. This ensures efficient handling of growing traffic volumes, improving both performance and
  scalability.

- **Server Monitoring:
  Implementing monitoring on each server enables real-time tracking of server health and performance. Monitoring tools analyze key
  metrics, detect issues, and promptly alert administrators to potential problems. This proactive approach allows for timely
  interventions, minimizing downtime and enhancing the overall stability of the infrastructure.

- **Firewall Implementation:
  Each server being equipped with a firewall adds an additional layer of security. Firewalls act as barriers, blocking
  unauthorized access and protecting against potential security threats. This security measure helps safeguard the network and
   its components, ensuring a more robust defense against unwanted and unauthorized access attempts.
