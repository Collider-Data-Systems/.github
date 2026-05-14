# Collider-Data-Systems

Collider-Data-Systems builds **mo:os**: a small rewriting runtime for a large idea.

The premise is simple enough to audit and strange enough to matter: people, agents, programs, machines, calendars, project boards, websites, files, and future applications can share one typed hypergraph without pretending that any external service is the source of truth.

In mo:os, the log is truth. State is derived. Every graph change is one of four rewrites:

```text
ADD    create a node with typed properties
LINK   create a typed relation between nodes
MUTATE change one property on one existing node
UNLINK remove one relation
```

Everything else is discipline around that tiny core: an ontology, an operad of legal port pairs, session liveness, authority gates, projection contracts, readback, reconciliation, and explicit actuator boundaries.

## What We Publish

| Repository | Role |
|---|---|
| **[moos-kernel](https://github.com/Collider-Data-Systems/moos-kernel)** | The Go runtime. It folds append-only rewrite logs into graph state, validates the loaded ontology, enforces session liveness and admin authority, exposes HTTP/MCP transports, derives HDC indexes, and keeps external actions at explicit boundary leaves. |
| **[moos-router](https://github.com/Collider-Data-Systems/moos-router)** | The WF16 federation gateway. It routes graph traffic by URN prefix and type map, fans out broad reads, cascades node lookups through peers, and reports downstream kernel health without owning graph truth. |
| **Project mo:os** | The public project-board surface for the convergence arc. Board rows are useful operator projections, but HG state remains authoritative; a row becomes a rewrite candidate only when it has stable graph identity. |

The private control workspace holds the ontology, projection planners, operator reports, and local dashboards. The runtime repositories stay narrow on purpose: kernel correctness in one place, federation routing in another, application/domain work above both.

## The Architecture In One Pass

Each kernel owns a sovereign log. Replay folds that log into a typed hypergraph. The loaded ontology currently models sessions, agents, programs, purposes, groups, claims, derivations, calendar events, channels, kernels, transports, gates, causal links, and more through 21 rewrite families.

Sessions are the working unit. A session is not just a chat window or a process. It is a purpose-colored context with scope, purpose, host, owner, and occupant represented by graph relations. Before an envelope reaches the fold, the runtime asks two questions:

- **M11 liveness:** does the actor have a live session context?
- **M12 authority:** is this rewrite admin-scoped, and if so, can the actor govern that scope?

That makes agent work inspectable. A VS Code conversation, a Claude Desktop window, an Antigravity surface, and a background process are harnesses. The graph occupant is the relation the kernel sees. The actor on an envelope must reconcile with that occupant before graph truth changes.

## Projection, Ingest, And Readback

mo:os treats external systems as surfaces, not truth stores.

```text
folded HG state
  -> planner artifact
  -> explicit writer or local view
  -> external object with stable graph identity
  -> readback observation
  -> reconciliation report
  -> gate or dashboard
```

That loop is the current proof style. The same pattern applies to Calendar events, GitHub Project rows, VS Code session context, Workspace artifacts, dashboards, DNS, websites, and future application surfaces.

Recent work proved the loop on a live Calendar and visualization lane: folded graph state projects into Calendar plans, graph lenses, DOT/SVG views, Cytoscape.js inspectors, recommendation plans, reconciliation reports, and a local dashboard. Calendar observations ingest back as `calendar_event` nodes with session pins; deferred source-anchor rows stay deferred until the operad says they are safe. That is intentional: the system would rather show an honest warning than blur the boundary.

## Current Frontier

The active May 2026 arc is about making the graph useful across real workstations and real agents while keeping the runtime boring.

- The hp-laptop primary kernel is live on ontology v3.16.1 with the governance session occupied by a VS Code/Copilot agent surface.
- The T194/T200 topology sprint split upcoming work into scoped idle lanes for Calendar readback, GitHub Project bridging, S0 conversation staging, application surface mapping, and Z440 rejoin.
- The projection dashboard currently reports a warning state with all safe Calendar/recommendation rows converged; the remaining warning is visual root coverage, not hidden failed work.
- HP ProDesk has a proven setup session. Z440 remains the larger federation and specialist-seat host, with rejoin work staged before GPU/HDC or long-running delegation resumes.

Those details change, but the invariant does not: a surface may help humans and agents work, but the append-only log plus folded HG state is where truth lives.

## Applications Live Above The Runtime

`my-tiny-data-collider` is the first named application group in the graph. It may own websites, DNS, servers, Calendar and GitHub surfaces, Workspace channels, data products, and public or private content. It does not become `moos-kernel`, and it does not belong inside `moos-router`.

This boundary is important. Kernel code should stay focused on log, fold, operad, sessions, authority, transport, and actuator correctness. Router code should stay focused on federation routing. Applications grow as graph groups, purposes, programs, channels, and external surfaces that use the runtime.

## Why This Is Interesting

Most automation systems hide their state in process memory, SaaS fields, local files, or prompt lore. mo:os pushes the opposite direction:

- external tools are named surfaces;
- agent sessions are graph relations;
- projected artifacts carry stable identity;
- causation is topology, not a timestamp guess;
- dashboards are generated read models;
- writers are explicit actuator boundaries;
- pending, applied, and deferred rows are visible at the same time.

The result is not a monolith. It is a graph substrate where agents can coordinate across machines, humans can inspect the exact boundary between plan and action, and applications can be built without smuggling their concerns into the runtime.

## Entry Points

- Start with **[moos-kernel](https://github.com/Collider-Data-Systems/moos-kernel)** if you care about the rewrite runtime, ontology validation, session liveness, authority gates, HTTP/MCP transport, or HDC-derived indexes.
- Start with **[moos-router](https://github.com/Collider-Data-Systems/moos-router)** if you care about federation, sharding, peer cascade, fan-out reads, and keeping routing stateless.
- Watch **[Project mo:os](https://github.com/orgs/Collider-Data-Systems/projects/4)** if you care about the current convergence arc and graph-aware project identity.

## Teams

- **[@Collider-Data-Systems/sam](https://github.com/orgs/Collider-Data-Systems/teams/sam)** owns kernels, delegates, and most sessions.
- **[@Collider-Data-Systems/moos](https://github.com/orgs/Collider-Data-Systems/teams/moos)** carries the multimodal curation lane.

## Contact

Use repository issues for project-specific discussion. The work advances in rounds: readback first, explicit changes second, reconciliation before claims of completion.
