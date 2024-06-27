---
id: rfu
title: Request for Update
description: Request updates from your partner
sidebar_position: 5
---

![DCM kit banner](/img/kit-icons/dcm-kit-icon.svg)

## Business Roles and Functions

Request for update uses its own aspect model and API. Request for update is provided and consumed by both customer and supplier.

|Function / Role|Customer|Supplier|
|-|-|-|
|Identify demand or capacity data that is not recent|X|X|
|Inform business partner about data that needs updating|X|X|
|Provide business partner with fresh data|X|X|
|Show users how fresh the data is |X|X|

## Sequence Diagram

```mermaid
sequenceDiagram
Participant c as Customer / Supplier
Participant s as Supplier / Customer
c->>c: One of my users is viewing some data
c->>c: This data from my partner is 6 months old and I received the last update 2 months ago.
rect rgb(4,107,153) 
c->>s: I have data known by ID e03ac75f with timestamp 2023.12.12 do you have a more recent version?

end
c->>c: Inform user that I am synchronized the data
alt Data not in sync
s->>c: Here is a more recent version of data e03ac75f
else Data still in sync
s->>c: You already have the most recent version of data e03ac75f

end
c->>c: Show user how old the data is and when was the last time it got synchronized.
```

For further details, please refer to [CX-0128 Demand and Capacity Management Data Exchange][StandardLibrary].

[StandardLibrary]: https://catena-x.net/de/standard-library