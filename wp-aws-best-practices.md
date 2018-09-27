# Notes for the AWS_Cloud_Best_Practices.pdf aws whitepaper
[Original PDF of the Whitepaper](https://d1.awsstatic.com/whitepapers/AWS_Cloud_Best_Practices.pdf)

### Abstract
- Intended for solutions architects and developers
- For building solutions of aws deployments
- Provide architectural patterns and advice 
- Systems to be secure, reliable, high performing, cost efficient
- Discussion on the advantage of cloud computing dynamic nature
- Covers general patters, which evolving and being applied in cloud computing

### Introduction
Even "Lift and Shift" approach (migrating to aws w/o much change)
- provides secured and cost-efficient infrastructure.
- Most elasticity and agility, needs evolving architectures 

New applications cloud-specific IT architecture pattern
- more efficiency and scalability
- support real-time analytics of Internet-scale data
- to apps with unpredictable traffic from thousands of IoT or mobile devices

Whitepaper covers whether to migrate or design a new app.

## The Cloud Computing Difference

### IT Assets Become Programmable Resources
non-cloud env: provision capacity based on guess
- expensive resources idle
- insufficient capacity

cloud computing: access more or less, dynamically scale
- meet actual demand
- paying for what you use

on aws, servers, databases, storage and higher-level application components can be instantiated within seconds
- treat as temporary and disposable resources
- free from inflexibility of fixed and finite IT infrastructure
- resets the approach change management, testing, reliability and capacity planning

### Global, Available, and Unlimited Capacity
using global aws infrastructure, deploying apps to aws region meets your needs.
- reduce latency to end users using CloudFront CDN
- easier to operate production applications and databases across multiple data centers
- achieve high availability and fault tolerance
- virtually unlimited on-demand capacity
- think differently about future expansion of IT

### Higher Level Managed Services
Apart Amazon EC2 (Elastic Compute Cloud), also provides storage, database, analytics, application and deployment services
- instantly available to developers
- reduce dependency on skills
- deliver new solutions faster
- services are managed by aws
- lower operational complexity and cost
- designed for scalability and high availability
- reduce risk for implementations

### Security Built In
infrastructure of traditional IT: security auditing is periodic and manual process.
awd cloud: continuous monitoring of config changes to IT resources.
- aws assets are programmable resources, security policy can be formalized and embedded in design of infrastructure
- With spinning of temp env, security testing can be part of Continuous delivery pipeline.
- plethora of native AWS security and encryption achieving higher levels of data protection and compliance

## Design Principles

### Scalability
System expected to grow overtime, built on scalable architecture.
- support growth in users, traffic, data size with no drop in performance
- should provide scale in linear manner by adding extra resources
- at least proportional increase to serve additional load
- should introduce economies of scale
- cost should follow the same dimension of system business value generation

Cloud computing provides virtually unlimited on-demand capacity
- deisgn needs to take advantage of resources
- vertically and horizontally scale an IT architecture

#### Scaling Vertically
increase specs of an individual resource
- larger hard drive
- faster CPU

on Amazon EC2
- stopping an instrance
- resizing it to more RAM, CPU, IO or networking capabilities
- eventually may be a limit
- not always cost efficient or highly available approach
- very easy to implement and be sufficient in the short term

#### Scaling Horizontally
increase in the number of resources 
- more hard drives to storage array
- adding more servers to support an app
- great way for internet-scale apps leveraging cloud elasticity
- not all architectues are designed to distribute workload to multiple resources

**Stateless Applications**
Stateful: series of interaction that form a session
Stateless: no knowledge of previous no session information.
- same input same response
- scale horizontally
- add more compute resources as needed
- terminate no longer needed capacity
- just need to distribute the workload to resources

__Two models for distribution load__
- Push model 
  - load balancing solution Elastic Load Balacing (ELB)
  - implement a DNS round robin (Amazon Route 53) - low TTL is not enforced
  - caching DNS resolvers are outside of control
- Pull model
  - Asynchronous event-driven workloads do not need a load balancing
  - tasks need to be performed
  - data need to be process
  - cloud be stored as messages in a queue using Amazon Simple Queue Service (Amazon SQS)
  - or cloud be a streaming data solution Amazon Kinesis.
  Multiple compute nodes can pull and consume, process in a distributed fasion.
  
  

