System design is a broad field focused on building scalable, reliable, maintainable, and efficient software systems. Here are the major topics, roughly grouped from fundamentals to advanced concepts.

## 1. System Design Fundamentals

* Functional vs. non-functional requirements
* Scalability
* Availability
* Reliability
* Maintainability
* Performance
* Fault tolerance
* Trade-offs in design

## 2. Capacity Planning

* Estimating traffic (QPS/RPS)
* Storage estimation
* Bandwidth estimation
* Memory requirements
* CPU utilization
* Growth projections

## 3. Networking Basics

* TCP vs. UDP
* HTTP/HTTPS
* HTTP/2 and HTTP/3
* DNS
* TLS/SSL
* WebSockets
* REST APIs
* gRPC
* Load balancing basics

## 4. Databases

### SQL Databases

* Normalization
* Indexes
* Transactions
* ACID properties
* Query optimization
* Replication

### NoSQL Databases

* Key-value stores
* Document databases
* Column-family databases
* Graph databases

### Database Scaling

* Read replicas
* Sharding
* Partitioning
* Consistent hashing
* Multi-region databases

## 5. Caching

* Why caching
* Cache-aside
* Write-through
* Write-back
* Read-through
* Cache eviction (LRU, LFU)
* Distributed cache
* Cache invalidation

## 6. Load Balancing

* Layer 4 vs. Layer 7
* Round Robin
* Least Connections
* IP Hash
* Health checks
* Reverse proxies

## 7. Distributed Systems

* Distributed computing basics
* Consensus
* Leader election
* Replication
* Quorum
* Eventual consistency
* Split brain
* Distributed locks

## 8. CAP Theorem

* Consistency
* Availability
* Partition tolerance
* Trade-offs

## 9. Consistency Models

* Strong consistency
* Eventual consistency
* Causal consistency
* Read-after-write consistency
* Monotonic reads

## 10. Messaging Systems

* Message queues
* Publish-subscribe
* Event-driven architecture
* Dead-letter queues
* Retry mechanisms
* Idempotency

## 11. Storage Systems

* Object storage
* Block storage
* File storage
* Blob storage
* CDN integration

## 12. Microservices

* Service decomposition
* Service discovery
* API Gateway
* Inter-service communication
* Circuit breaker
* Service mesh
* Distributed tracing

## 13. API Design

* REST
* GraphQL
* gRPC
* Versioning
* Pagination
* Authentication
* Rate limiting

## 14. Authentication & Authorization

* Sessions
* Cookies
* JWT
* OAuth
* OpenID Connect
* RBAC
* ABAC
* API keys

## 15. Scalability Techniques

* Horizontal scaling
* Vertical scaling
* Auto-scaling
* Stateless services
* Sticky sessions

## 16. Reliability

* Redundancy
* Failover
* Disaster recovery
* Backup strategies
* High availability
* Replication

## 17. Monitoring & Observability

* Logging
* Metrics
* Distributed tracing
* Dashboards
* Alerting
* Health checks
* SLI/SLO/SLA

## 18. Security

* Encryption at rest
* Encryption in transit
* DDoS protection
* Firewalls
* WAF
* Secrets management
* Rate limiting
* Input validation

## 19. Cloud & Infrastructure

* Virtual machines
* Containers
* Docker
* Kubernetes
* Serverless
* Infrastructure as Code
* CI/CD
* Multi-cloud

## 20. Common Design Patterns

* CQRS
* Event sourcing
* Saga pattern
* Bulkhead
* Circuit breaker
* Retry
* Backoff
* Sidecar
* Strangler pattern

## 21. Search Systems

* Full-text search
* Inverted index
* Ranking
* Autocomplete
* Fuzzy search

## 22. Streaming Systems

* Real-time processing
* Batch processing
* Stream processing
* Windowing
* Event time vs. processing time

## 23. Content Delivery

* CDN
* Edge caching
* Geo-replication
* Media optimization

## 24. Specialized Systems

* Recommendation systems
* Notification systems
* Chat systems
* Video streaming
* URL shortener
* Ride-sharing
* Payment systems
* Social media feed
* Search engine
* Real-time collaboration

## 25. System Design Interview Problems

Common practice problems include:

* URL Shortener
* TinyURL
* WhatsApp
* Instagram
* Twitter/X
* Facebook News Feed
* YouTube
* Netflix
* Uber
* Airbnb
* Google Drive
* Dropbox
* Google Docs
* Zoom
* Slack
* Notification Service
* Distributed Cache
* Rate Limiter
* Web Crawler
* Search Autocomplete
* Distributed File Storage

### Suggested Learning Order

1. Networking fundamentals
2. Databases (SQL and NoSQL)
3. Caching
4. Load balancing
5. Distributed systems basics
6. CAP theorem and consistency
7. Message queues
8. Scalability patterns
9. Microservices
10. Cloud and containers
11. Monitoring and observability
12. Security
13. Common architecture patterns
14. End-to-end design of real-world applications

This progression builds the foundation before tackling large-scale architecture and interview-style design problems.
