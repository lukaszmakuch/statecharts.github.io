---
title: Delayed transition
oneliner: A transition that executes automatically when a machine has been in a state for a particular amount of time
---

# Delayed transition

A delayed transition is an [transition](transition.html){:.glossary} that happens after a period of time, specifically being in a specific state for a certain amount of time.

Whenever such a delayed transition exists in a state, the state machine will execute the transition if and only if the machine has stayed continously in the state for a given period of time.  If the state has a [self transition](self-transition.html){:.glossary} which is executed, this causes the state to be [exited](exit.html){:.glossary} and then [entered](enter.html){:.glossary} again, interrupting any continuity.

## Notation

A delayed event uses the phrase "after <timespec>" as the name of the event

        after 3 s
     ---------------->

## SCXML

Delayed transitions are not part of Statechart XML.  Instead, you have to specify to send a [delayed event](delayed-event.html){:.glossary}, and a normal transition that handles that event.  The delayed event must be given a name, and also a unique identifier (in order to cancel the delayed event).

## xstate

It's possible to implement delayed transitions using the same mechanisms as in SCXML, however, there is a proposal to add them to the format to avoid the verbosity and housekeeping chores associated with delayed events.
