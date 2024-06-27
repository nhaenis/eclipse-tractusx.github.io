---
id: delta-production
title: Simulated Delta Production
description: Solve bottlenecks using pre- and post production
sidebar_position: 3
---

![DCM kit banner](/img/kit-icons/dcm-kit-icon.svg)

## Business Roles and Functions

Delta production data is embedded into the WeekBasedCapacityGroup aspect model. This means that only suppliers provide delta production related data and customers consume it.

|Function / Role|Customer|Supplier|
|-|-|-|
|Solve bottleneck via pre production||X|
|Solve bottleneck via post production||X|
|Inform customer||X|
|Acknowledge that bottleneck has been solved|X||

## Sequence Diagram

```mermaid
sequenceDiagram
Participant c as Customer
Participant s as Supplier
rect rgb(157,93,00) 
c->>s: I need 100 blue toys each in weeks 47, 48, 49 and 50
end
s->>s: Manage Capacities
s->>s: There is a bottleneck in week 50
s->>s: It is solvable via pre-production in weeks 48 and 49  

rect rgb(64,74,00)
s-->>c: I can produce 100 in week 47, 0 in week 50 and 150 in weeks 48 and 49
s->>c: 50 each in weeks 48 und 49 are pre-produced to cover the demand in week 50
end
```

For further details, please refer to [CX-0128 Demand and Capacity Management Data Exchange][StandardLibrary].

[StandardLibrary]: https://catena-x.net/de/standard-library