```mermaid
erDiagram
    COUPON ||--o{ MEMBER_COUPON_MAPPING : has
    COUPON ||--o{ PRODUCTS_COUPON_MAPPING : has
    MEMBER ||--o{ MEMBER_COUPON_MAPPING : maps
    PRODUCTS ||--o{ PRODUCTS_COUPON_MAPPING : maps

    COUPON {
        BIGSERIAL id PK
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