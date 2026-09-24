# OpenPCB Commons + Noepedia

> **Short description:** Noepedia is a persistent, addressable semiotic knowledge field. It stores objects, relations, provenance, uncertainty, revisions, and raw-artifact references outside any one person's or model's memory. Access to the persistent field is mediated by the Socratic Daimonion.

OpenPCB Commons is intended to become one of Noepedia's first practical domains.

The goal is simple:

> **Use Noepedia as the structured storage and search layer for OpenPCB knowledge, while AISocket provides bounded contact with real hardware and returns evidence.**

---

## Why OpenPCB needs Noepedia

A Git repository is excellent for source-controlled documents, project history, and human-readable records.

But OpenPCB eventually needs searches that are naturally relational:

~~~text
find every board containing this component marking

show all measurements that support this reconstructed net

find repair cases with the same failure pattern

find reusable motors with compatible electrical and mechanical relations

show all boards investigated by this instrument version

show what is still unknown about this board

show evidence that contradicts this schematic fragment
~~~

Those are not only filename or text-search problems.

They require addressable objects and relations.

Noepedia is intended to provide that layer.

---

## Division of responsibility

### OpenPCB Commons

OpenPCB defines the domain and the human-visible commons:

- boards;
- components;
- images;
- geometry;
- nets;
- measurements;
- schematic fragments;
- functional blocks;
- failures;
- repairs;
- second-life uses;
- instruments and methods;
- community explanations and documentation.

The repository may remain a readable project surface and export/archive location.

### AISocket

AISocket connects authorized intelligence and instruments to physical boards.

It produces structured traces of:

- observation;
- measurement;
- bounded experiment;
- action;
- result;
- local safety decision;
- body / passport / firmware context.

Those traces are evidence, not automatically settled knowledge.

### Noepedia

Noepedia becomes the persistent storage and search field for the structured knowledge.

It should preserve:

- stable object identities;
- triplet relations;
- network rules;
- labels and aliases;
- provenance;
- evidence and counterevidence;
- uncertainty;
- OPEN / disputed states;
- revision history;
- raw artifact references;
- permissions;
- search indexes;
- task-relevant relational retrieval.

### Socratic Daimonion

OpenPCB clients do not directly rewrite the persistent Noepedia field.

The Daimonion mediates:

~~~text
request / contribution
→ context clarification
→ permission check
→ identity reconciliation
→ placement or staging
→ search / retrieval
→ revision tracking
→ audit
~~~

---

## Proposed OpenPCB object families

The first implementation can begin with a small vocabulary:

~~~text
BOARD
BOARD_FAMILY
COMPONENT
COMPONENT_CANDIDATE
MARKING
PACKAGE
PAD
NET
CONNECTOR
IMAGE
GEOMETRY
MEASUREMENT
INSTRUMENT
CALIBRATION
EXPERIMENT
AISOCKET_TRACE
SCHEMATIC_FRAGMENT
FUNCTIONAL_BLOCK
FAILURE_MODE
REPAIR_CASE
PART
SECOND_LIFE_USE
SOURCE
RAW_BLOB
OPEN_QUESTION
~~~

This list is a pilot vocabulary, not a frozen ontology.

Because Noepedia is homoiconic, relations and network rules can later be revised without erasing why they changed.

---

## Example relations

~~~text
BOARD ── BELONGS_TO_FAMILY ──> BOARD_FAMILY
BOARD ── HAS_COMPONENT ──> COMPONENT
COMPONENT ── HAS_MARKING ──> MARKING
COMPONENT ── HAS_PACKAGE ──> PACKAGE
PAD ── CONNECTED_TO ──> NET
CONNECTOR ── HAS_PAD ──> PAD
MEASUREMENT ── OBSERVED_ON ──> PAD
MEASUREMENT ── PRODUCED_BY ──> INSTRUMENT
MEASUREMENT ── HAS_CALIBRATION ──> CALIBRATION
AISOCKET_TRACE ── ABOUT ──> BOARD
SCHEMATIC_FRAGMENT ── SUPPORTED_BY ──> MEASUREMENT
FAILURE_MODE ── OBSERVED_IN ──> REPAIR_CASE
REPAIR_CASE ── REPLACED ──> COMPONENT
PART ── SALVAGED_FROM ──> BOARD
PART ── REUSED_IN ──> SECOND_LIFE_USE
CLAIM ── CONTRADICTED_BY ──> EVIDENCE
~~~

A relation may remain provisional or disputed.

---

## Raw files and large artifacts

OpenPCB contains data that should not be forced into triplets:

- board photographs;
- microscope images;
- thermal images;
- waveforms;
- 3D geometry;
- binary captures;
- logs;
- datasheets;
- large scan files.

Noepedia should represent each artifact as an addressable RAW_BLOB object with a content hash, media type, provenance, permissions, and relations to the objects it documents.

The bytes may initially live in a separate content-addressed object/file store.

The important point is that search and provenance still enter through Noepedia.

---

## Contribution path

A contributor should not have to understand the final ontology before helping.

A practical path is:

~~~text
human / instrument / AISocket / model
        ↓
submit photograph / note / trace / measurement / hypothesis
        ↓
Noepedia staging inbox
        ↓
Socratic Daimonion
        ↓
identify / clarify / compare / link
        ↓
promote to structured knowledge
or
keep provisional / disputed / raw
~~~

The contributor can therefore say:

> "I found this."

without also having to know exactly where in the final graph it belongs.

---

## Search plan

The first OpenPCB Noepedia interface should support several complementary search modes.

### 1. Direct identity and label search

Search by:

- board number;
- product name;
- component marking;
- manufacturer part number;
- connector marking;
- known alias;
- Noepedia object ID.

### 2. Faceted search

Filter by:

- object type;
- board family;
- component/package;
- voltage/current range where supported;
- measurement type;
- instrument;
- failure mode;
- repair outcome;
- evidence status;
- OPEN / disputed state.

### 3. Relational search

Follow graph paths such as:

~~~text
board → component → marking
board → pad → net
claim → evidence → instrument
failure → repair → replacement part
part → compatibility → second-life use
~~~

### 4. Evidence-first search

A result should be able to expose:

~~~text
claim
→ supporting trace
→ raw artifact
→ instrument
→ calibration
→ conditions
→ contributor / actor
~~~

### 5. Task-relevant semiotic cut

For a repair or investigation task, the Daimonion should be able to return a compact relational package rather than the entire archive.

This is OpenPCB's practical use of Noepedia's **epistemic teleportation**.

---

## First pilot board

The first pilot should stay deliberately small.

For one board:

1. create the BOARD object;
2. attach top and bottom images;
3. identify several visible components;
4. keep at least one component identity provisional;
5. connect one AISocket instrument;
6. perform one safe measurement;
7. ingest the trace;
8. create one supported net or functional relation;
9. search that relation later;
10. revise one provisional relation without deleting its previous state.

Then add a second board and test cross-board search.

The first convincing moment will be when a fact discovered on one board helps investigate another board without either investigator needing the original chat.

---

## Relationship to this GitHub repository

GitHub remains useful for:

- public project documentation;
- contributor-readable files;
- versioned design documents;
- exported board packages;
- human review;
- backups and portable snapshots.

Noepedia is intended to become the **live structured storage and search layer**.

The two should not compete.

A future export can make a board's Noepedia structure readable as files in this repository, while imports from repository files can enter Noepedia through staging.

---

## Pilot technical requirements

The detailed cross-project technical requirements are kept in the Noepedia repository:

[Noepedia Pilot: AISocket + OpenPCB Commons](https://github.com/gakelytemp-creator/Noepedia/blob/main/PILOT_AISOCKET_OPENPCB.md)

That document defines the minimum identity, provenance, staging, blob, search, permissions, trace-envelope, revision, and acceptance-test requirements for the first implementation.

---

## Short formula

> **OpenPCB supplies the domain.**
>
> **AISocket touches the hardware.**
>
> **Noepedia stores and finds the structured knowledge.**
>
> **The Daimonion guards the transactions between them.**
