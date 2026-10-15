# Engineering Under Constraints

**What early computers and mission systems can still teach modern software engineers about constraints, state, interfaces, failure and simplicity.**

Modern software is built with extraordinary amounts of compute, memory and abstraction. That makes older systems easy to dismiss as technically obsolete.

I think that is a mistake.

Early personal computers, radar networks, aircraft avionics, missile systems, naval combat systems and spacecraft were built under severe limits of memory, processing power, electrical power, weight, cost, reliability and logistics. Their designers had to make state, timing, interfaces and failure visible because the machine and operating environment left little room to hide complexity.

This repository asks a narrow question:

> **Which engineering habits remain useful when the original constraints disappear?**

## Engineering research, not politics

This is an engineering research exercise, not a political statement.

The systems here are included because they are historically significant examples of solving difficult technical problems under severe constraints. Inclusion does **not** imply endorsement of a government, military policy, conflict, ideology or political position.

That rule applies consistently across the repository. Israel is studied for the same reason as Sweden, France, the United Kingdom, the United States, NASA and the Soviet/Eastern Bloc tradition: particular systems were widely recognised for technical innovation, integration, effectiveness or unusually strong adaptation to constraints.

The analysis stays at the level of systems, engineering decisions, evidence and trade-offs. Contemporary political argument is outside scope unless it is necessary to explain a technical constraint.

## The method

Every study follows the same structure:

```text
MISSION / PROBLEM
       |
       v
CONSTRAINTS
       |
       v
ENGINEERING RESPONSE
       |
       v
WHAT WAS EXCEPTIONAL?
       |
       v
LIMITS / FAILURES
       |
       v
TRANSFERABLE SOFTWARE LESSON
```

The point is not to imitate old hardware. It is to recover the judgement that the constraints forced engineers to exercise.

See [`METHODOLOGY.md`](METHODOLOGY.md).

## Studies

### Commodore 64

[`c64/lessons.md`](c64/lessons.md) uses the C64 as a compact laboratory for visible state, fixed resource budgets, hardware-shaped data, time-sharing scarce resources and designing rich behaviour from small mechanisms.

A short worked example in [`c64/worked-example.md`](c64/worked-example.md) translates those habits into a fictional modern service without pretending a cloud service should be programmed like an 8-bit computer.

### Israel — Gabriel and the Sa'ar missile-boat system

[`mission-systems/israel.md`](mission-systems/israel.md) examines the move from a failing manually guided missile concept toward autonomous guidance, sea-skimming flight and a tightly integrated small-ship combat system. The strongest lesson is system integration under asymmetric constraints, not any claim about politics or military policy.

### United Kingdom — Chain Home and the Dowding System

[`mission-systems/uk.md`](mission-systems/uk.md) looks at an early integrated air-defence information system: radar, human observation, filtering, command, communications and fighters treated as one operational chain rather than independent technologies.

### France — mission-specific simplification and system ownership

[`mission-systems/france.md`](mission-systems/france.md) uses the Mirage 5 and Mirage IV programmes to examine deliberate simplification, mission fit and concentrated responsibility for end-to-end system performance.

### Sweden — CK37 and the Saab 37 Viggen

[`mission-systems/sweden.md`](mission-systems/sweden.md) examines the CK37 central computer, where severe size, weight and environmental constraints helped drive early use of integrated circuits and central avionics integration in a single-seat aircraft.

### United States — smaller-service constraints

[`mission-systems/united-states-small-services.md`](mission-systems/united-states-small-services.md) looks at the US Marine Corps' expeditionary/austere operating model and the US Coast Guard's government-owned Minotaur mission architecture. The common theme is capability that must travel, integrate and remain supportable away from ideal infrastructure.

### Soviet / Eastern Bloc tradition

[`mission-systems/eastern-bloc.md`](mission-systems/eastern-bloc.md) uses the MiG-25 and Elbrus computing programme to examine simple-but-functional material choices, real-time/high-reliability requirements and the way mission constraints can produce architectures that look unfashionable but are rational in context.

### NASA / Apollo

[`mission-systems/nasa-spaceflight.md`](mission-systems/nasa-spaceflight.md) examines the Apollo Guidance Computer and flight software: hard memory limits, early software freeze, asynchronous priority scheduling, restart/recovery behaviour and explicit human-machine interaction.

## Synthesis

[`principles/modern-software.md`](principles/modern-software.md) brings the recurring lessons together.

The short version:

1. **Mission beats fashion.** Choose architecture against the job and environment.
2. **Budgets create clarity.** Make latency, memory, dependencies and operational complexity finite on purpose.
3. **State should be visible.** Hidden state makes failure harder to reason about.
4. **Interfaces deserve disproportionate attention.** Systems usually fail at joins before they fail at components.
5. **Design the whole operating system, not the hero component.** Sensors, software, people, procedures and recovery form one system.
6. **Degraded operation matters.** Useful partial service can be more valuable than brittle nominal perfection.
7. **Remove heroics.** Good systems reduce dependence on exceptional operator behaviour.
8. **Test in the real environment.** Elegant assumptions often die in weather, clutter, latency, logistics and load.
9. **Simplification can be a performance feature.** Removing capability can improve mission fit.
10. **Constraints should be chosen, not merely suffered.** Modern teams can recreate useful discipline without recreating obsolete hardware limits.

For a reusable review, see [`principles/constraint-review.md`](principles/constraint-review.md).

## Source discipline

The source register is in [`sources/bibliography.md`](sources/bibliography.md).

Preference order:

1. official technical/historical material;
2. national museums and institutional archives;
3. manufacturer historical archives for product facts;
4. reputable specialist histories for details not available in primary sources;
5. secondary summaries only when clearly labelled.

Corporate and military sources are useful evidence for design facts but are not treated as neutral judges of their own success. Where a source is institutionally interested, that limitation is stated.

## What this repository is not

It is not:

- an argument that old technology was better;
- a catalogue of military hardware;
- a political history;
- a doctrine for modern warfare;
- an instruction manual for weapons or military systems;
- an argument for artificial scarcity in software;
- a claim that every historical design choice transfers to modern systems.

The transferable object is **engineering judgement**, not the original implementation.

## Licence

MIT. See [`LICENSE`](LICENSE).
