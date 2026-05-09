# Collider-Data-Systems

> A semantic functorial network over distributed compute.

Collider-Data-Systems builds **mo:os**: a categorical hypergraph runtime for people, agents, kernels, programs, and external surfaces that need to stay in one typed graph without pretending every outside system is the source of truth.

The core idea is intentionally small. The log is truth. State is derived. Everything that changes the graph is one of four rewrites: `ADD`, `LINK`, `MUTATE`, or `UNLINK`. Above that log, an ontology/operad declares node types, port pairs, authority, sessions, purpose, causality, and time. External systems such as Calendar, GitHub Projects, websites, DNS, Workspace, and local OS services are projection or ingest surfaces with explicit adapters.

## What we publish

| Repository | What it is |
|---|---|
| **[moos-kernel](https://github.com/Collider-Data-Systems/moos-kernel)** | The OS-facing rewriting runtime: Go, stdlib-first, append-only log, fold-derived state, ontology validation, session liveness, admin capability, HTTP/MCP transport, HDC derivation, and explicit actuator boundaries. Current private workspace ontology: v3.16.1, 53 node types, WFs WF01-WF21. |
| **[moos-router](https://github.com/Collider-Data-Systems/moos-router)** | The WF16 federation gateway: stateless HTTP routing by URN prefix and type map, peer cascade, and fan-out reads across sovereign kernels. |

Together they form a federation. Each kernel owns a sovereign log. The router helps clients find the right kernel or fan out across peers. Twin-kernel synchronization and host-level OS integration are runtime substrate work, not application logic.

## The shape, briefly

The kernel state is a hypergraph that grows by four rewrites:

```
ADD    — create a node with typed properties
LINK   — create a relation (hyperedge) between two nodes via a typed port pair
MUTATE — change one property value on one existing node
UNLINK — remove a relation
```

`state(t) = fold(log[0..t])`. Log is truth; state is derived.

Above that, an operad declares the legal types and ports. Above the operad, sessions inhabit kernels as purpose-colored contexts: scope, purpose, host, owner, and occupant. Envelopes pass two gates before fold:

- **§M11 liveness** — every envelope must have a live session context (explicit or inferable via `has-occupant`)
- **§M12 admin-capability** — admin-scope rewrites walk `WF02 governs` from actor through superadmin

The result is a categorical substrate where:

- **Sessions** are purpose-colored occasions of work, with durable scope carried by relations.
- **Programs** decompose intent into graph structure rather than process-local memory.
- **Channels** are explicit F/G boundaries for Gmail, Drive, Calendar, GitHub, websites, DNS, and other external systems.
- **Calendar events** and Project rows are projections with stable graph identity, not competing truth stores.
- **Causation** is topology (`WF21 causes/caused-by`), distinct from temporal succession.
- **Application groups** such as `my-tiny-data-collider` run on the hypergraph through kernels; they are not the kernel itself.

## Current projection work

The active T189/T200 lane is about identity-stable projection surfaces:

- Folded HG state projects to local dashboards, DOT/SVG graph lenses, Cytoscape.js inspector tabs, Google Calendar events, GitHub Project rows, and future website/DNS surfaces.
- External observations ingest back as typed graph evidence: `knowledge_item`, `claim`, `derivation`, `calendar_event`, status `MUTATE`, or a more specific node type.
- Every external artifact should carry a graph-derived identity such as an HG URN, projection contract, or stable `moos_projection_id`.

The local pipeline currently proves the pattern on Calendar and graph lenses: 16 Google Calendar projection events have stable IDs, corresponding `calendar_event` nodes exist in HG, and the remaining source-anchor relations are held back until the WF07 operad declaration is cleaned up. That is the intended shape: planner first, writer second, readback third, graph truth always visible.

## Applications on top

`my-tiny-data-collider` is the first named application group in this model. It may own websites, DNS, servers, Calendar/GitHub/Workspace surfaces, data products, and public/private content, but it remains an HG group/purpose/program/channel family above the runtime substrate. The runtime repositories stay small and principled; application domains grow through the graph.

## Teams

- **[@Collider-Data-Systems/sam](https://github.com/orgs/Collider-Data-Systems/teams/sam)** — owns kernels, delegates, and most sessions
- **[@Collider-Data-Systems/moos](https://github.com/orgs/Collider-Data-Systems/teams/moos)** — multimodal curation lane

## Project board

Active work surfaces on **[Project mo:os](https://github.com/orgs/Collider-Data-Systems/projects/4)**: round-by-round iterations with HG-aware fields such as Agent ID, HG URN, Phase, Owner Role, Collider Category, and Branch Role. The board is a projection/control surface. HG remains authoritative; board edits become rewrite candidates only after the row resolves to an HG URN.

## Background

mo:os is being built toward a May 2026 convergence arc: reliable kernel/federation runtime, identity-stable projection surfaces, Calendar/GitHub readback, and application groups that can use the graph without leaking application concerns into runtime code. The substrate doctrine, ontology, and round-by-round reasoning live in a private workspace; the public face is the two runtime repos, this organization profile, and selected project-board surfaces.

If you're a category theorist, hypergraph-rewriting researcher, or distributed-systems engineer interested in the substrate, the kernel README is the entry point.

## Contact

Reach out via repository issues or the maintainer's GitHub profile. Solo-builder cadence — responses arrive in rounds rather than in real time.
