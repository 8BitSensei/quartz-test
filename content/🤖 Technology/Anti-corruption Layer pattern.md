---
date: 2023-06-23
draft: false
tags:
  - DesignPattern
---
A façade or adapter layer that sits between two systems that don't share the same semantics. This layer translates requests from the new system to make it acceptable to the old system, without forcing the new system to adapt to match the old system.

Maintains access between new and legacy systems without forcing the new system to adhere to at least some of the legacy system's APIs or data models, this would corrupt, what is otherwise a cleanly designed modern system.

#### Solution
Isolate the different subsystems by placing an ant-corruption layer between them, which will translate communications between the two systems, allowing one system to remain unchanged while the other can avoid compromising its design.
![[anti-corruption.png]]


#### Fantasy
Two castles, one old, one new, the new one relies on the old for supplies but uses a new type of wagon and horse, this wagon and horse barely fits through the gate at the old castle, it's not the right shape on the inside for the crates! The old castle is constantly complaining, the new castle refuses to change the carts, the new ones are better after all! A carpenter sees an opportunity, she sets up a business on the road halfway between the two castles to modify the carts to fit in the old castle on the way there, and back to the new version on the way back.

---
# References
