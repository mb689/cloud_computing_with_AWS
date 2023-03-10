# Two-tier architecture
- A two-tier architecture in AWS is a type of architecture that is commonly used for web applications. It is a client-server architecture that consists of two tiers: the web tier and the database tier.
- The web tier is the front-end of the application, which serves the user interface and handles user requests. It is typically hosted on one or more EC2 instances, which can be configured with a web server such as Apache or Nginx.
- The database tier is the back-end of the application, which stores and manages the data used by the application. It is typically hosted on a separate set of EC2 instances, which can be configured with a database server such as MySQL or PostgreSQL.
- Communication between the web tier and the database tier is typically done over a private network, using VPC (Virtual Private Cloud) or VPN (Virtual Private Network) technology to secure the connection.


# Availability Zones 
- Availability Zones (AZs) in AWS are geographically distinct data centers within a region that are designed to provide high availability and fault tolerance for applications and services. 
- An Availability Zone is a physically separate location within a region that is designed to be isolated from failures in other Availability Zones in the same region.
- Each Availability Zone has independent power, cooling, and networking infrastructure, and is connected to the other Availability Zones in the region through high-speed, low-latency links.


# Requirements for our 2 tier arch
- Deploy app instance so that it has a public ip
- Deploy a second instance for our database with the correct dependencies -> `Ubuntu 18.04`, `MongoDB installed` and change mongod.conf to `0.0.0.0`
- Create a security group for database instance -> 27017 which allows from anywhere -> allow only from app instance.
- Create env var the db endpoint
- Relaunch app
