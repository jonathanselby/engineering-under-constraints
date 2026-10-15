# Methodology

This repository studies engineering under constraint. It is not a ranking of countries, armed forces or political systems.

## Research question

For each historical system, ask:

1. **What problem had to be solved?**
2. **Which constraints materially shaped the design?**
3. **What engineering response followed from those constraints?**
4. **What was genuinely unusual or effective?**
5. **Where did the design fail, compromise or impose cost?**
6. **Which lesson transfers to modern software without copying obsolete implementation detail?**

## Evidence standard

Evidence is preferred in this order:

1. official technical or historical records;
2. national museums and institutional archives;
3. manufacturer historical archives for product facts;
4. contemporary professional journals and reputable specialist histories;
5. secondary summaries where better evidence is unavailable.

A manufacturer or military organisation is a useful source for design facts, but not automatically a neutral judge of its own success. Claims of exceptional performance are therefore separated from directly observable design facts where possible.

## Political neutrality

Inclusion means only that a system is useful to study as engineering history.

It does not endorse:

- a government;
- a military action;
- an ideology;
- a contemporary political position;
- the use of a technology.

Israel, the Soviet Union, the United States, Britain, France and Sweden are treated under the same research rule: **study the engineering, its context and its limitations.**

## Safety boundary

This is a historical engineering study. It does not reproduce weapon construction details, targeting procedures, operational attack instructions or other material intended to enable harmful use.

Technical description is limited to the level needed to understand architecture, constraints, interfaces, reliability, human factors and systems engineering.

## Translation rule

A historical lesson is included only if it can be translated into a modern software question.

For example:

```text
HISTORICAL OBSERVATION
Fixed memory forced explicit allocation.

NOT THE LESSON
Modern software should use 64 KB.

TRANSFERABLE QUESTION
What resource budgets should be explicit before growth becomes accidental?
```

## Anti-romanticism

Constraint is not automatically good. Scarcity can also produce brittle systems, poor ergonomics, hidden technical debt and dangerous compromises.

Every study therefore includes a **limits** section. The point is to recover useful judgement, not romanticise deprivation.
