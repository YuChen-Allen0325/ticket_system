```mermaid
flowchart LR
    SDK[SDK Client]  -->|request| LB[Load Balancer]
    LB -->|request| ClientBackend[Client-facing Backend]
    ClientBackend --> |request| Redis[(Redis)]
    ClientBackend --> |request| Database[(PostgreSQL)]
    ClientBackend --> |request| Blob[(Azure Blob)]
    Redis -->|response| ClientBackend
    Database -->|response| ClientBackend
    Blob -->|response| ClientBackend


    User[Client] -->|request| LB[Load Balancer]
    LB --> |request| Frontend[Internal admin/Frontend]
    Frontend --> |request| Backend[Internal admin/Backend]
    Backend --> |request| Redis
    Backend -->|request| Database
    Backend -->|request| Blob
    Backend -->|request| Worker[Async Worker]
    Redis -->|response| Backend
    Database -->|response| Backend
    Blob -->|response| Backend