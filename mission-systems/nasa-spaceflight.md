# NASA — Apollo Guidance Computer and Flight Software

Sources: [NASA-1], [NASA-2], [NASA-3], [NASA-4] in the [source register](../sources/bibliography.md).

## Problem

Apollo required autonomous guidance, navigation and control in an environment where ground support could not always act quickly enough and where a computing failure could jeopardise the mission.

## Constraints

- tiny memory by modern standards;
- severe size, weight and power limits;
- real-time deadlines;
- software that had to be delivered early enough for core-rope manufacture and test;
- human operators working under extreme workload;
- no opportunity to patch software casually after launch.

NASA records Block II AGC hardware at roughly 70 pounds and 70 watts, with fixed core-rope memory and very small erasable memory. [NASA-1]

## Engineering response

### 1. Priority over completeness

During the Apollo 11 landing, the guidance computer's executive could shed lower-priority work while preserving critical tasks. NASA's Lunar Surface Journal explains that lower-priority jobs could fall off the queue rather than allowing all scheduled work to overrun the processor. [NASA-3]

Modern lesson: overload policy must be architectural. If everything is equally important, nothing is prioritised when capacity disappears.

### 2. Software freeze became a physical constraint

Core-rope software had to be finalised months before flight because manufacture and testing took time and changes were difficult after fabrication. [NASA-1]

Modern lesson: deliberate release gates and immutability can improve reliability, but only when backed by strong verification rather than bureaucracy.

### 3. Human-machine interaction was part of the system

Apollo crew interaction through DSKY was not an afterthought. NASA records thousands of keystrokes across a lunar mission and repeated efforts to reduce unnecessary interaction. [NASA-2]

Modern lesson: operator workload is an engineering variable.

### 4. Reliability was designed and measured

NASA's reliability history describes unusually strict quality control, failure reporting and system integration discipline around the AGC. [NASA-4]

Modern lesson: resilience is not a property conferred by a technology choice. It comes from architecture, verification, manufacturing/build quality and operational discipline together.

## What was exceptional?

The AGC combined constrained hardware, real-time priority scheduling, human interaction and mission software in a system that had to remain dependable under conditions where recovery options were limited.

Its significance is not that old software was inherently better. It is that the constraints forced explicit decisions about priority, memory, operator interaction and recovery.

## Limits

- Apollo software development still experienced schedule and complexity problems; NASA created review structures specifically because of concern about software readiness. [NASA-2]
- core-rope immutability made late fixes expensive;
- heavy verification cost time and money;
- the approach was appropriate to a safety-critical spacecraft, not every business application.

## Transferable software lesson

> **When failure matters, make priorities, recovery and operator interaction explicit before the system is under stress.**
