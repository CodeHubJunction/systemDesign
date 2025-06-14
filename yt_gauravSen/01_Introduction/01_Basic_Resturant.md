# System Design Notes (Based on Restaurant Analogy)

---

## 1. Introduction to System Design

- System design is about building scalable, reliable systems.
- To simplify understanding, the speaker uses the analogy of opening and running a pizza restaurant.

---

## 2. Vertical Scaling

- **Scenario**: One chef handles all pizza orders.
- **Problem**: Increased orders overwhelm the chef.
- **Solution**: Ask the chef to work harder, invest more.
- **Concept**: This is _vertical scaling_ – increasing capacity of a single resource (CPU, RAM).

---

## 3. Optimization through Preprocessing

- **Idea**: Pre-make pizza bases during non-peak hours.
- **Benefit**: Frees chef during busy hours to serve more customers.
- **Concept**: Pre-computation / background tasks / caching/ Cron jobs.

---

## 4. Fault Tolerance and Redundancy

- **Scenario**: Chef calls in sick.
- **Problem**: No backup leads to loss of business.
- **Solution**: Hire a backup chef.
- **Concept**: Avoid Single Point of Failure (SPOF); add redundancy (e.g., standby servers).

---

## 5. Horizontal Scaling

- **Scenario**: Hire multiple chefs to meet growing demand.
- **Concept**: _Horizontal scaling_ – adding more machines of the same type to distribute load.

---

## 6. Load Distribution by Specialization

- **Scenario**:

  - Chefs 1 & 3: Pizza specialists
  - Chef 2: Garlic bread specialist

- **Naïve routing**: Randomly assign tasks.
- **Optimized routing**: Send garlic bread orders to Chef 2; pizzas to Chefs 1 & 3.
- **Benefits**:

  - Efficient task allocation
  - Easier updates & tracking

---

## 7. Microservices Architecture

- **Teams**:

  - Garlic bread team: 3 chefs
  - Pizza team: 7 chefs

- **Concept**: Divide responsibilities into services based on functionality.
- **Microservices** = Specialized teams with well-defined responsibilities.

---

## 8. Distributed Systems & Disaster Recovery

- **Issue**: What if power fails or license gets suspended?
- **Solution**: Open another shop in a different location.
- **Concept**: Geographical distribution for resilience.

---

## 9. Distributed Request Routing

- **Challenge**: Decide which pizza shop should serve an order.
- **Factors**:

  - Queue wait time
  - Preparation time
  - Delivery time

- **Example**:

  - Shop 1: 1 hr wait + 5 min prep + 10 min delivery = 75 mins
  - Shop 2: 5 min wait + 5 min prep + 5 min delivery = 15 mins

- **Routing Decision**: Send to shop 2.
- **Concept**: Load Balancer

---

## 10. Decoupling & Separation of Concerns

- **Observation**:

  - Pizza shop and delivery agent can operate independently.
  - They don’t care who the end party is.

- **Solution**: Decouple systems.
- **Benefit**: Each system can evolve or fail independently.

---

## 11. Observability and Metrics

- **Why**:

  - Track if a pizza oven fails or a delivery bike breaks.
  - Measure delays.

- **Approach**:

  - Logging
  - Event tracking
  - Metrics aggregation

- **Purpose**: Identify and act on bottlenecks and failures.

---

## 12. Extensibility

- **Scenario**:

  - Today it’s pizza.
  - Tomorrow it’s burgers.

- **System**: Should not assume what’s being delivered.
- **Example**: Amazon scaled from books to everything.
- **Key**: Generalize components for future reuse.

---

## 13. Mapping to Technical Concepts

| Pizza Shop Analogy         | System Design Concept           |
| -------------------------- | ------------------------------- |
| Chef                       | Server or Compute Node          |
| Backup Chef                | Redundant / Failover Instance   |
| Pizza Base Prep            | Pre-processing / Caching        |
| Garlic Bread & Pizza Teams | Microservices                   |
| Second Shop                | Distributed System / Replica    |
| Routing Logic              | Load Balancer                   |
| Delivery Agent             | Client Service / Edge Component |
| Logging Times              | Metrics & Monitoring            |
| Flexible Delivery Options  | Extensibility / Decoupling      |

---

## 14. High-Level vs Low-Level Design

- **High-Level Design (HLD)**:

  - Focuses on system architecture.
  - How components interact (e.g., services, databases).

- **Low-Level Design (LLD)**:

  - Class diagrams, functions, signatures.
  - How actual logic is implemented.

---

## 15. Summary

- Start with real-world problems (scaling, reliability).
- Map to system design solutions (vertical/horizontal scaling, load balancing, microservices).
- Build for fault-tolerance, observability, and extensibility.

> This is how we define and scale systems. This process of abstracting problems and finding structured solutions is called **High-Level System Design**.

---

## Next Steps

- Learn LLD to write clean, maintainable code.
- Explore detailed architecture case studies (e.g., designing YouTube, Amazon).

---
