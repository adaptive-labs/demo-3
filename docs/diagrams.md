# Diagram Examples - All Supported Types

This document demonstrates all diagram types supported by the Shoehorn docs viewer.

## 1. Mermaid Flowchart

Mermaid diagrams render client-side for the best performance:

```mermaid
flowchart LR
  customer[Customer]

  subgraph shop[Online Shop System]
    web[Web App<br/>React]
    api[API<br/>Node.js]
    db[(Database<br/>PostgreSQL)]
  end

  payment[Payment Provider<br/>External]
  email[Email Service<br/>External]

  customer -->|Uses HTTPS| web
  web -->|Calls HTTPS/JSON| api
  api -->|Reads/Writes| db
  api -->|Charges card| payment
  api -->|Sends confirmation| email
```

## 2. Mermaid Sequence Diagram

Perfect for API interactions:

```mermaid
sequenceDiagram
    participant U as User
    participant W as Web App
    participant A as API Gateway
    participant S as Search Service
    participant T as Typesense

    U->>W: Search "kubernetes"
    W->>A: GET /api/search?q=kubernetes
    A->>S: gRPC SearchRequest
    S->>T: Query Index
    T-->>S: Results
    S-->>A: SearchResponse
    A-->>W: JSON Results
    W-->>U: Display Results
```

## 3. Mermaid Class Diagram

Great for architecture documentation:

```mermaid
classDiagram
    class Entity {
        +String id
        +String name
        +String type
        +String tenantId
        +getStatus()
        +getMetadata()
    }

    class Team {
        +String id
        +String name
        +List members
        +addMember()
        +removeMember()
    }

    class Repository {
        +String url
        +String provider
        +clone()
        +sync()
    }

    Entity "1" --> "*" Repository : owns
    Team "1" --> "*" Entity : manages
```

## 4. Mermaid Entity Relationship Diagram

Database schema visualization:

```mermaid
erDiagram
    ENTITY ||--o{ REPOSITORY : owns
    ENTITY ||--o{ TEAM : "managed by"
    ENTITY {
        uuid id PK
        string name
        string type
        uuid tenant_id FK
        timestamp created_at
    }
    REPOSITORY {
        uuid id PK
        string url
        string provider
        uuid entity_id FK
    }
    TEAM {
        uuid id PK
        string name
        uuid tenant_id FK
    }
```

## 5. GraphViz/DOT Diagram

Low-level graph visualization:

```dot
digraph G {
    rankdir=LR;
    node [shape=box, style=rounded];

    start [label="Start" shape=ellipse];
    validate [label="Validate Input"];
    process [label="Process Request"];
    cache [label="Check Cache" shape=diamond];
    execute [label="Execute Query"];
    respond [label="Send Response"];
    end [label="End" shape=ellipse];

    start -> validate;
    validate -> process;
    process -> cache;
    cache -> execute [label="miss"];
    cache -> respond [label="hit"];
    execute -> respond;
    respond -> end;
}
```

## 6. Nomnoml Diagram

ASCII-art style diagrams:

```nomnoml
[<frame>Shoehorn Platform|
  [Web App]
  [API Gateway]
  [<database>PostgreSQL]
  [Search Service]
]

[User] -> [Web App]
[Web App] -> [API Gateway]
[API Gateway] -> [Search Service]
[API Gateway] -> [<database>PostgreSQL]
```

## 7. Math/LaTeX

Mathematical equations using KaTeX:

```math
f(x) = \int_{-\infty}^\infty \hat f(\xi)\,e^{2 \pi i \xi x} \,d\xi
```

```latex
\begin{aligned}
\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} &= \frac{4\pi}{c}\vec{\mathbf{j}} \\
\nabla \cdot \vec{\mathbf{E}} &= 4 \pi \rho \\
\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} &= \vec{\mathbf{0}} \\
\nabla \cdot \vec{\mathbf{B}} &= 0
\end{aligned}
```