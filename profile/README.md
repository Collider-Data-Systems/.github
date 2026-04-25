# Collider-Data-Systems

> *A semantic functorial network over distributed compute.*

Collider-Data-Systems builds **mo:os** — a categorical hypergraph rewriting kernel where all components, hardware and programs alike, are considered categorically. The session is the centerpiece for human and AI inference; its relations both make it findable (observing surfaces like Drive, Gmail, Calendar, GitHub) and capable of writing the programs that pull the levers (emitting envelopes through leaves).

## What we publish

| Repository | What it is |
|---|---|
| **[moos-kernel](https://github.com/Collider-Data-Systems/moos-kernel)** | The rewriting kernel — Go, stdlib-first. Four primitives (ADD / LINK / MUTATE / UNLINK), append-only log, fold-derived state. Runtime gates §M11 + §M12. Ontology v3.13.0 with 52 node types and WFs WF01–WF20 (WF21 in the v3.14 candidate set). |
| **[moos-router](https://github.com/Collider-Data-Systems/moos-router)** | The WF16 federation gateway — URN-prefix shard routing across multiple kernels. Stateless. |

Together they form a federation: each kernel owns a sovereign log, the router cascades reads across shards, and twin kernels per-host carry replication via `twin_link` edges.

## The shape, briefly

The kernel state is a hypergraph that grows by four rewrites:

```
ADD    — create a node with typed properties
LINK   — create a relation (hyperedge) between two nodes via a typed port pair
MUTATE — change one property value on one existing node
UNLINK — remove a relation
```

`state(t) = fold(log[0..t])`. Log is truth; state is derived.

Above that, an operad declares the legal types and ports. Above the operad, sessions inhabit kernels (5-facet tuples: scope, purpose, host, owner, occupant) and emit envelopes that have to pass two gates before fold:

- **§M11 liveness** — every envelope must have a live session context (explicit or inferable via `has-occupant`)
- **§M12 admin-capability** — admin-scope rewrites walk `WF02 governs` from actor through superadmin

The result is a categorical substrate where:

- **Sessions** are program-authoring layers (where derivations happen)
- **Channels** are cooperads upstream of ingestion (Gmail, Drive, GitHub, etc.)
- **Leaves** are partially-applied morphisms: any structure that surfaces values back to a session's open arguments
- **Time** runs on multiple clocks (kernel sweep, T-day calendar, custom event-driven), each generalized via `keeps-time-with` LINKs
- **Causation** is distinct from temporal succession (`causes` vs `scheduled-after`), expressed as its own WF

## Teams

- **[@Collider-Data-Systems/sam](https://github.com/orgs/Collider-Data-Systems/teams/sam)** — owns kernels, delegates, and most sessions
- **[@Collider-Data-Systems/moos](https://github.com/orgs/Collider-Data-Systems/teams/moos)** — multimodal curation lane

## Project board

Active work surfaces on **[Project mo:os](https://github.com/orgs/Collider-Data-Systems/projects/4)** — round-by-round iterations with custom HG-aware fields (Agent ID, HG URN, Phase, Owner Role, Collider Category, Branch Role).

## Background

mo:os is being built toward an MVP gate sequence (G1–G6) targeting May 2026. The substrate doctrine, ontology, and round-by-round reasoning live in a private workspace; the public face is the two repos above plus their READMEs.

If you're a category theorist, hypergraph-rewriting researcher, or distributed-systems engineer interested in the substrate, the kernel README is the entry point.

## Contact

Reach out via repository issues or the maintainer's GitHub profile. Solo-builder cadence — responses arrive in rounds rather than in real time.
