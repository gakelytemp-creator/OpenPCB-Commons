# OpenPCB Commons

> **Open the box. Understand it. Repair it. Give it another life. Leave what you learned for the next person.**

OpenPCB Commons is an open workshop, archive, research commons, and learning path for understanding real electronic hardware.

A circuit board can remain physically useful long after its documentation disappears, its manufacturer loses interest in it, or the product around it becomes obsolete. Someone may still want to repair it. Someone may want to reuse its motor, printhead, sensor, power supply, display, controller, or other parts in an entirely different machine. Someone may simply want to understand how it was made.

That person should not always have to begin from zero.

## Four connected sides of the Commons

OpenPCB Commons is growing around four mutually reinforcing activities:

1. **Real boards and evidence** — collect board photographs, measurements, reconstructed nets, functional blocks, schematics, failures, and investigation trails.
2. **Circuit patterns** — identify, classify, compare, and explain recurring schematic tricks and reusable functional structures across many products.
3. **Second life** — recover knowledge needed to reuse components, modules, mechanisms, and boards instead of discarding useful hardware.
4. **Preparatory learning** — grow future investigators by teaching electrical engineering as living, usable knowledge through discovery, principles, formalization, applications, play, and real experiments.

The first three preserve and expand technical knowledge.

The fourth makes sure there are always new curious people able to use it.

## This is not one machine

One of our first ideas is a compact two-sided PCB investigation machine: cameras, height measurement, electrical probes, and other sensing methods, connected through AISocket to an LLM that can choose useful experiments and combine their results.

But that machine is not the project.

Someone else may build a better probe. Someone may use a microscope, field sensing, an electrolyte, X-ray data, thermal imaging, a hand-held instrument, or a method we have never imagined.

**Good. We want many corridors into the black box.**

A result should never say only:

> We know this net.

It should also be able to say:

> We know it because this instrument, under these conditions, produced this measurement.

The method is part of the knowledge.

AISocket provides one route from real hardware into that knowledge system: bounded observations and experiments produce traces; those traces enter Noepedia through staging and the Socratic Daimonion rather than becoming settled knowledge automatically.

## What we want to build together

A public archive of real electronic objects — not only finished schematics.

For the live structured archive and search layer, OpenPCB Commons is intended to use **[Noepedia](https://github.com/gakelytemp-creator/Noepedia)**.

Noepedia is a persistent, addressable semiotic knowledge field: it keeps objects, relations, provenance, uncertainty, revisions, and raw-artifact references outside any one person's or model's memory. Its persistent field is mediated by the Socratic Daimonion.

In this project that means a board should eventually be searchable not only by filename or text, but through its relations:

board → component → marking  
board → pad → net  
claim → evidence → instrument  
circuit pattern → function → board examples  
failure → repair → replacement part  
part → compatibility → second-life use  
principle → lesson → experiment → real circuit

The repository remains the human-readable commons and portable project record. Noepedia is intended to become the live structured storage and search layer.

We want to preserve photographs, geometry, components, nets, measurements, block diagrams, partial schematics, known failures, repair experience, circuit patterns, alternative uses, reusable parts, unknowns, disagreements, educational explanations, and the history of how each conclusion was reached.

Incomplete knowledge is welcome.

If one person understands 20% of a board and another understands a different 15%, we have not failed. **We have begun.**

## Open boxes and black boxes

Some products help people understand, repair, reuse, and extend them. Others remain unnecessarily closed, sometimes even after their commercial life has ended.

We will document both.

The status is not permanent. A black box can become an open box tomorrow. If a manufacturer publishes useful documentation, schematics, protocols, repair information, or other technical knowledge, we will gladly record that change.

Our purpose is not to keep enemies.

**Our purpose is to keep knowledge.**

## A second life is part of design

A motor should not become useless merely because the printer around it died.

A sensor should not become electronic waste because its connector is undocumented.

A perfectly good actuator should not need to be manufactured again because nobody knows how to speak to the one already sitting in a discarded machine.

We want to make second-life usefulness visible and searchable.

Nobody has to be forced. Useful standards spread because people find them useful.

## Knowledge should also have a first life

A technical commons needs future investigators.

The PREPARATORY_COURSE folder is an experimental learning layer for electrical engineering. Its aim is not to make learners carry inert facts for examinations, but to turn principles into living tools.

The working structure uses four connected paths:

**Discovery → Principles → Formalization → Applications**

Lessons may begin as comics or slides and later become interactive browser scenes, voice-guided experiments, 3D simulations, or VR. The conceptual core should remain usable even on very simple hardware or on paper.

## Who are we looking for?

Not customers. Not followers.

**Curious people.**

Repair technicians. Electronics engineers. Students. Makers. Researchers. Firmware people. Mechanical designers. Reverse engineers. Teachers. People who keep old machines alive. People who cannot resist asking:

> What is inside this thing, and why did they do it this way?

You do not need to build our scanner. You do not need an expensive laboratory.

You can contribute one identified component, one measurement, one correction, one old board, one repair story, one circuit pattern, one better instrument, one disagreement supported by evidence, one lesson experiment, or one path that nobody else noticed.

## This project is not mine alone

**Founded by Giorgi (gakelytemp-creator), Georgia, 2026.**

I am beginning it and I am willing to put my name on that beginning.

But founded does not mean owned.

If other people join, their work, instruments, discoveries, lessons, and branches become part of what this project is.

Fork it. Improve it. Build the hardware yourself. Build a different version. Manufacture it if the applicable licenses permit it. Teach with it. Use it to open something we never expected.

Just leave enough of the road visible that the next curious person does not have to start again in darkness.

**We may be few. But for every black box, three of us will eventually find the time.**

## Come open one with us.

---

### Repository map

- NOEPEDIA_INTEGRATION.md — how Noepedia will be used as OpenPCB's live structured storage and search layer
- FOUNDING_PRINCIPLES.md — why this commons exists
- CONTRIBUTING.md — many small ways to participate
- INSTRUMENTS/ — tools and experimental methods
- BOARDS/ — investigated boards and evidence trails
- CIRCUIT_PATTERNS/ — reusable schematic patterns, tricks, and functional structures
- SECOND_LIFE/ — reuse, adaptation, and second-life knowledge
- PREPARATORY_COURSE/ — experimental electrical-engineering learning path and teaching philosophy
- OPEN_BOXES.md — open and repair-friendly products/manufacturers
- BLACK_BOXES.md — unnecessarily closed products

The detailed cross-project pilot requirements live in Noepedia: https://github.com/gakelytemp-creator/Noepedia/blob/main/PILOT_AISOCKET_OPENPCB.md

> **Decompose to understand. Compose to create.**

---

## Ecosystem Boundary: OpenPCB Commons vs Noepedia

OpenPCB Commons owns the **electronics-investigation domain**: boards, components, photographs, measurements, reconstructed nets, repair histories, donor-part knowledge, investigation methods, and the human-readable commons.

Noepedia owns the **persistent cross-context knowledge machinery**: object identity, relation networks, provenance, OPEN structures, revision, consolidation, and task-relevant relational retrieval.

OpenPCB therefore should not grow a second private Noepedia inside itself.

~~~text
board / image / measurement / hypothesis
        ↓
OpenPCB domain record
        ↓
Noepedia transaction boundary
        ↓
persistent relational knowledge
        ↓
task-relevant cut / OPEN requirement / next-test request
        ↓
OpenPCB / AISocket investigation
~~~

The Socratic Daimonion may be internally plural and parallel inside Noepedia, but OpenPCB should depend only on the stable mediated boundary.

> **OpenPCB owns the workshop and evidence trail. Noepedia owns the reusable knowledge field.**
