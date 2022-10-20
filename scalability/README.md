# Understanding Scalability for System Design

## Scalability Basics

**How many simultaneous connections can a single server handle? What does it depend on?**

**Scaling for 10,000 Req/s users:**
Do nothing with 8GB RAM and 100GB memory

**Scaling from 10,000 Req/s users to 1L Req/s user:**

Each connection has some required memory associated with it to maintain the connection. For IPv4 connections the protocol itself has only 16 bits for the port number, so only 65,535 connections of any TCP/IP or UDP/IP type can exist simultaneously on a single computer.

Buys more RAM and Memory, and new processor. Now we have 128GB RAM and 500GB of hard disk. This is called "Vertical Scaling". That is you are scaling your computer vertically and making it bigger and bigger.

**Scaling from 1L Req/s to 1M Req/sec:**

Mark is in a big problem now. If anyone trips over the power cable, all the system shuts down in a fraction of second. He recognizes it is a single point of failure.

Soon Mark gets 20 such servers to handle a million requests.

By scaling this way, he ensured that if after a few years even if his user base starts to decrease, he can just sell the extra servers. He can also keep on adding more servers whenever he feels the need of adding more servers. Even if any server fails, another server can take charge. Now there is no single point of failure. This way he has introduced Resiliency.

**What is resiliency**

System resilience is an ability of the system to withstand a major disruption and to recover within an acceptable time. If one server crashes, another server in the pool can start to serve traffic. 

## Load Balancing