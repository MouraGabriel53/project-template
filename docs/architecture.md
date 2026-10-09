# Architecture

<!-- One paragraph: what the system is and how it is split. Then a diagram of the main flow. -->

```
<!-- e.g. Client -> HTTP adapter -> use case -> port -> database adapter -> DB -->
```

## Layers

<!-- Keep this table identical to the rules in the architecture test. -->

| Package | Role | May depend on |
| --- | --- | --- |
| `domain` | Core types and rules, no I/O | `domain` |
| `domain/ports` | Interfaces only: what the core needs from the outside | `domain` |
| `usecase` | Application logic that orchestrates the ports | `domain` |
| `infrastructure` | Adapters that implement the ports (database, HTTP, brokers...) | `domain`, `infrastructure` |
| `application` | Composition: builds the adapters and wires them | everything |

Dependency rule: `domain` ← `usecase` ← `infrastructure` ← `application`.
The architecture test fails when a layer imports one it may not, or when a new
top-level package appears without declared dependencies.

## Flows

<!-- The main flows step by step: startup, the main request or job, errors, shutdown. -->

## Adding a feature

<!-- Checklist of the files to touch for the most common kind of change. -->
