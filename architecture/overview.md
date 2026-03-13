# Architecture Overview

<!-- This file is referenced by CLAUDE.md and used by agents to understand the system. -->
<!-- Customize it for your project's architecture. -->

## Architecture Style

<!-- Choose and describe your architecture. Examples below. -->

<!-- Option 1: Hexagonal Architecture -->
<!--
We follow Hexagonal Architecture (Ports and Adapters).

```
         ┌────────────────────────────────┐
         │           Adapters             │
         │  (API, DB, External Services)  │
         │                                │
         │    ┌──────────────────────┐    │
         │    │       Ports          │    │
         │    │   (Interfaces)       │    │
         │    │                      │    │
         │    │  ┌──────────────┐   │    │
         │    │  │   Domain     │   │    │
         │    │  │  (Core)      │   │    │
         │    │  └──────────────┘   │    │
         │    └──────────────────────┘    │
         └────────────────────────────────┘
```

### Layers

- **Domain** (`src/domain/`): Business logic, entities, value objects. No external dependencies.
- **Ports** (`src/ports/`): Interfaces that define how domain interacts with the outside world.
- **Adapters** (`src/adapters/`): Implementations of ports (database, API clients, etc).
- **API** (`src/api/`): HTTP layer. Routes, request/response schemas, middleware.

### Dependency Rules

- Domain MUST NOT import from adapters or API.
- Ports define interfaces; adapters implement them.
- API layer depends on domain and ports, never directly on adapters.
- Use dependency injection to wire adapters to ports at application startup.
-->

<!-- Option 2: Layered Architecture -->
<!--
We follow a standard layered architecture.

- **API Layer** (`src/api/`): HTTP handlers, request validation
- **Service Layer** (`src/services/`): Business logic orchestration
- **Repository Layer** (`src/repositories/`): Data access
- **Models** (`src/models/`): Data structures and schemas
-->

## Directory Structure

<!-- Document your project's directory layout. -->
<!-- Example: -->
<!--
```
src/
├── api/              # HTTP routes and schemas
│   ├── routes/
│   └── schemas/
├── domain/           # Business logic
│   ├── entities/
│   ├── services/
│   └── value_objects/
├── ports/            # Interface definitions
├── adapters/         # External service implementations
│   ├── database/
│   └── search/
└── config/           # Application configuration
tests/
├── unit/
├── integration/
└── fixtures/
```
-->

## Key Design Decisions

<!-- Link to ADRs for important decisions. -->
<!-- See decisions/ directory for Architecture Decision Records. -->

## Data Flow

<!-- Describe how a typical request flows through the system. -->
<!-- Example: -->
<!--
1. HTTP request → API route
2. Route validates input → calls domain service
3. Domain service executes business logic → uses port interfaces
4. Adapters implement ports → interact with external systems
5. Response flows back through the layers
-->
