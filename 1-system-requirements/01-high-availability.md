# 1. High availability

1. Time-based and count-based availability
1. Design principles behind availability
1. Processes behind high availability
1. SLO and SLA

**Success ration** of requests (count-based)

**availability** = system uptime, the percentage of time the system has been working and available (timebased)

1 out of 100 = **99%** - the system was unavailable about 3.65 days a year

![clients persepective of availability](../resources/clients-vs-server-perspective.png)

> The server may be 100% fine but the request may fail. Availability should be seen from the client perspective and not the developer's. Perspective matters. The client's experience.

What does high availability really mean?

> 98%, 99% or 100% ? these lead to really complex and expensive and almost never justified for distributed systems. Software and hardware is never perfect and there could always be problems. None of these above is the goal for high availability

It is not about a number, it is about the **architechture** and **process**

![Single server](../resources/single-server.png)

> If the single server goes down, then the whole application system becomes unavailable, and no one knows when it will become available again

Systems are not static, they change.

1. We will add new features to the system
1. We will find and fix bugs
1. The load of the system may increase
1. We have to upgrade software
1. We have to apply security patches

> We need processes that help us safely make regulary changes to the system while maintaining high availability

**design principles behind high availability**

1. Build redundancy to eliminate single points of failure

   1. regions
   1. availability zones
   1. fallback
   1. data replication
   1. high availability pair

1. Switch from one server to another without losing data

   1. DNS
   1. Load balancing
   1. reverse proxy
   1. api gateway
   1. peer discovery
   1. service discovery

1. Protect the system from atypical client behavior (like too many expensive client requests)

   1. Load shedding
   1. Rate limiting
   1. Shuffle sharding
   1. Cell-based architecture

1. Protect the system from failures and performance degradation

   1. timeouts
   1. circuit breaker
   1. bulkhead
   1. retries
   1. idemprotency

1. Detect failures as they occur
   1. monitoring

**processes behind high availability**

> For Highly availabile systems a high uptime value is not the goal, it is a by product because is designed, implemented and maintained as such

1. Change management

   1. All code and configuration changes are reviewed and approved

1. QA

   1. Regularly exercise test to validate that newly introduced changes meet functional and non-functional requirements

1. deployment

   1. deploy changes to a production environement frequently, quickly, safely
   1. automated rollback quickly when errors are detected

1. Capacity planning

   1. Monitor system and add resources to meet growing demand

1. disaster recovery

   1. recover system quickly in the event of a disaster
   1. regularly test failover to distater recovery

1. Root cause analysis

   1. When a failure happens, establish the root cause of the failure and identify preventive measures

1. Operational readiness review

   1. evaluate system's operational state and identify gaps in operations
   1. define actions to remediate risks

1. game day

   1. during a game day, we simulate a failure or event and test system and team responses

1. team culture
   1. good team promotes process discipline

**software developer**

Service Level Objective (SLO)

> my system is highly available. It guarantees a monthly uptime percentage of 99.99% (LSO). If you experience lower availability, I will refund you

Service Level Agreement (SLA)

> The commitment between service providers and clients of our system is called an SLA (Service Level Aggreement).
