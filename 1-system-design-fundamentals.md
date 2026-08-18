## 1. System Design Fundamentals

# 1. Functional vs. Non-functional Requirements

### Functional requirements

**What the system must do.**

Example: URL shortener:

* User can submit a long URL.
* System generates a short URL.
* User can open the short URL.
* System redirects them to the original URL.

Think:

> **"What features does the system provide?"**

### Non-functional requirements

**How the system should behave.**

For the same URL shortener:

* Redirect should be fast.
* System should be highly available.
* Should support millions of requests.
* Should not lose URLs.
* Should handle failures.

Think:

> **"What qualities/constraints does the system have?"**

### Example

> "Design Instagram."

**Functional**

* Users can upload photos.
* Users can follow other users.
* Users can like/comment.
* Users can view their feed.

**Non-functional**

* Feed should load quickly.
* System should support millions of users.
* High availability.
* Photos should not be lost.
* System should scale as traffic grows.

---

# 2. Scalability

Scalability means:

> **The system can handle increasing load by adding resources or changing the architecture.**

Suppose you have:

```text
Users
  ↓
Node.js Server
  ↓
PostgreSQL
```

At 1,000 users/day → fine.

At 10 million users/day → your single server probably becomes a bottleneck.

You need to scale.

### Vertical scaling

Make one machine more powerful:

```text
4 CPU
8 GB RAM
      ↓
32 CPU
128 GB RAM
```

Simple, but there are physical and cost limits.

### Horizontal scaling

Add more machines:

```text
             ┌── Server 1
Users → LB ──┼── Server 2
             └── Server 3
```

This is extremely important in system design.

**If you are asked answer:**

> "I'd prefer horizontal scaling for the application layer because it allows us to handle increasing traffic by adding more instances."

---

# 3. Availability

Availability means:

> **How often is the system operational and accessible when users need it.**

Imagine a service is supposed to operate 24/7.

If it goes down, users can't use it.

Availability is often expressed as a percentage.

| Availability | Approx. downtime/year |
| ------------ | --------------------: |
| 99%          |            ~3.65 days |
| 99.9%        |            ~8.8 hours |
| 99.99%       |           ~53 minutes |
| 99.999%      |            ~5 minutes |

You may hear:

> "Three nines"

That means **99.9% availability**.

### How do we improve availability?

Avoid a single point of failure.

Instead of:

```text
Users
  ↓
Server
```

Use:

```text
             ┌── Server 1
Users → LB ──┤
             └── Server 2
```

If Server 1 dies, Server 2 can continue serving requests.

---

# 4. Reliability

Reliability is slightly different from availability.

**Availability:**

> Is the system currently working?

**Reliability:**

> Does the system consistently perform correctly without losing/corrupting data or unexpectedly failing?

Example:

A banking system might be available 99.99% of the time but still be **unreliable** if it occasionally transfers money twice.

For example:

```text
User sends $100
       ↓
Payment service
       ↓
Database
```

If a network failure causes the request to be processed twice:

```text
$100
+
$100
=
$200 transferred ❌
```

That's a reliability problem.

This is where concepts like **idempotency, transactions, retries, replication, and consistency** become important later.

---

# 5. Performance

Performance is primarily about:

### Latency

How long one operation takes.

Example:

```text
Request → Server
          ↓
        50 ms
```

Lower latency = faster response.

### Throughput

How much work the system can handle over time.

Example:

```text
10,000 requests / second
```

That's throughput.

So:

> **Latency = how fast one request is handled.**
> **Throughput = how many requests the system can handle.**

A system can have good latency but poor throughput, or vice versa.

---

# 6. Fault Tolerance

Fault tolerance means:

> **The system continues operating even when some components fail.**

Suppose you have:

```text
          Database
             ↓
          Server
```

Database crashes → everything stops.

Not fault tolerant.

Instead:

```text
             ┌── DB 1
Server ──────┤
             └── DB 2
```

If DB 1 fails, DB 2 can potentially take over.

Other examples:

* Multiple application servers
* Database replication
* Multiple availability zones
* Message queues
* Retries
* Failover
* Backups

---

# 7. Maintainability

Maintainability means:

> **How easily can developers understand, modify, debug, and operate the system.**

Imagine two architectures.

### Architecture A

```text
One giant application
50,000 lines
Everything connected
```

Changing one feature can break five others.

### Architecture B

```text
Auth Service
Payment Service
Order Service
Notification Service
```

Each component has a clear responsibility.

Architecture B may be easier to maintain—but there's a trade-off.

More services also introduce:

* Network communication
* Deployment complexity
* Monitoring complexity
* Distributed-system problems

Which leads directly to the next topic.

---

# 8. Trade-offs

This is **one of the most important concepts in system-design interviews.**

There is rarely a perfect architecture.

You are constantly choosing between competing properties.

For example:

### Performance vs. consistency

Caching can make a system faster:

```text
User → Redis → Response
```

But cached data might be stale.

So:

> Faster response ↔ potentially stale data

### Availability vs. consistency

In distributed systems, you may have to make decisions about what happens when parts of the system cannot communicate.

### Simplicity vs. scalability

A single PostgreSQL server:

```text
Simple ✅
Easy to maintain ✅
Extremely scalable ❌
```

A distributed database architecture:

```text
Highly scalable ✅
More complex ❌
Harder to operate ❌
```

### Cost vs. reliability

You could run:

```text
1 server → cheap
```

or:

```text
20 servers across multiple regions → expensive
```

The second can provide much better resilience, but costs more.

---

# The mental model

When you're designing something, keep asking:

```text
What does it do? (Functional requirements)
       ↓
How well must it do it? (Non-functional requirements)
       ↓
How much traffic? (Scalability)
       ↓
Can it stay online? (Availability)
       ↓
Will it behave correctly? (Reliability)
       ↓
How fast? (Performance)
       ↓
What happens when things break? (Fault tolerance)
       ↓
How easy is it to change? (Maintainability)
       ↓
What are we sacrificing? (Trade-offs)
```

### One important interview habit

Don't just say:

> "We need high availability."

Say:

> "We need 99.99% availability, so I would avoid a single application server and deploy multiple instances behind a load balancer."

That's the difference between **knowing terminology** and **actually doing system design**.

---

## Assesment

Let's test these before moving on.

**Imagine you're designing a food-delivery app like Uber Eats. What are the functional and non-functional requirements for this system? Give me 3–5 functional and 3–5 non-functional requirements.**
