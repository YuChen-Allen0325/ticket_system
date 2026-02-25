# E-Commerce Backend Architecture Demo

This repository demonstrates a scalable backend architecture 
using FastAPI + PostgreSQL + Redis + Azure Blob.

erDiagram
    COUPON ||--o{ MEMBER_COUPON_MAPPING : has
    COUPON ||--o{ PRODUCTS_COUPON_MAPPING : has
    MEMBER ||--o{ MEMBER_COUPON_MAPPING : maps
    PRODUCTS ||--o{ PRODUCTS_COUPON_MAPPING : maps

    COUPON {
        BIGSERIAL id PK
        INTEGER product_type
        UUID trust_id
        VARCHAR product_code
        TIMESTAMPTZ start_time
        TIMESTAMPTZ end_time
        BOOLEAN used
    }

    MEMBER_COUPON_MAPPING {
        SERIAL id PK
        BIGSERIAL coupon_id FK
        INTEGER member_id FK
    }

    PRODUCTS_COUPON_MAPPING {
        SERIAL id PK
        BIGSERIAL coupon_id FK
        UUID products_id FK
    }

    MEMBER {
        INTEGER id PK
    }

    PRODUCTS {
        UUID id PK
    }
