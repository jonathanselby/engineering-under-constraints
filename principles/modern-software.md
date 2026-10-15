# Modern Software Lessons

The historical systems in this repository differ radically in purpose, era and technology. The recurring value is therefore not a shared implementation pattern. It is a set of recurring engineering decisions forced into the open by constraint.

## 1. Mission beats fashion

The MiG-25, Mirage 5, CK37 and Apollo examples all show architecture being pulled by a concrete mission rather than a generic technology ideal.

Modern question:

> What measurable job is this architecture supposed to make possible?

If the answer is vague, technology choice will tend to become the strategy.

## 2. Budgets create clarity

C64 memory, aircraft weight, spacecraft power and real-time compute all had hard ceilings.

Modern systems rarely need limits that severe, but they still benefit from explicit budgets for:

- latency;
- memory;
- queue depth;
- dependencies;
- API calls;
- model tokens;
- recovery time;
- operational complexity.

A budget is not deprivation. It is a decision about when the design has exceeded its intended envelope.

## 3. State should be visible

C64 programming made state physically legible. Apollo scheduling made task priority explicit. Mission systems made readiness and operating state consequential.

Modern question:

> Can an engineer explain the important system states and the transitions between them without reconstructing them from side effects?

## 4. Interfaces deserve disproportionate attention

The Sa'ar/Gabriel and Dowding cases are integration stories. Component quality mattered, but value emerged at the joins: sensor to filter, filter to command, missile to platform, electronics to crew, crew to maintenance.

Modern question:

> Which interfaces could make individually correct components fail as a system?

## 5. Design the whole operating system, not the hero component

Historical mission systems repeatedly combine machines, people, procedures, communications and support.

In modern software, the real system includes:

```text
code
+ data
+ identity
+ deployment
+ observability
+ operators
+ support
+ failure procedure
```

Ignoring the last four does not remove them. It merely leaves them undesigned.

## 6. Degraded operation matters

Apollo's priority executive could preserve critical work under overload. Expeditionary systems assume imperfect infrastructure. Small naval platforms could not rely on absorbing damage like large ships.

Modern question:

> When capacity, connectivity or a dependency disappears, what useful service remains?

Graceful degradation is often more valuable than nominal peak performance.

## 7. Remove heroics

Automation in CK37 reduced single-pilot calculation burden. Gabriel evolved away from time-critical manual guidance. Dowding industrialised information flow rather than relying on isolated local judgement.

Modern question:

> Which repeated expert action should become a system property rather than a heroic operator skill?

Do not automate judgement merely because it is human. Automate coordination and mechanical burden where doing so improves reliability.

## 8. Test in the real environment

Hardware and software that work in isolation can fail under clutter, weather, heat, load, latency, operator stress or poor connectivity.

Modern question:

> Which environmental assumption is most likely to be false in production?

Test that assumption first.

## 9. Simplification can be a performance feature

Mirage 5 removed equipment to improve mission fit. C64 software achieved rich behaviour through a small mechanism set. MiG-25 used available technology where more fashionable alternatives were not necessary to the mission.

Modern question:

> What could be removed while making the system better at its actual job?

## 10. Constraints should be chosen, not merely suffered

Historical engineers did not choose most of their constraints. Modern teams can choose useful ones deliberately:

- one authoritative state store until a second is justified;
- bounded queue and retry policy;
- dependency budget;
- latency objective;
- small public interface;
- explicit deployment target;
- clear acceptance authority.

The point is not minimalism as aesthetics. It is to stop accidental complexity becoming invisible.

## Closing rule

> **Use constraint to force decisions, not to glorify scarcity.**

The best historical lesson is not “they did more with less”. It is that when resources, interfaces and failure were impossible to ignore, engineers had to decide what mattered.
