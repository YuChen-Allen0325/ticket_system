```mermaid
erDiagram
    PRODUCTS ||--o{ PRODUCTS_DETAIL_IMAGE : has
    PRODUCTS ||--o{ STORE_PRODUCTS : contains
    PRODUCTS ||--o{ PRODUCTS_CHANNEL_MAPPING : maps
    PRODUCTS ||--o{ PRODUCTS_COUPON_MAPPING : maps
    PRODUCTS ||--o{ PRODUCTS_ENTERPRISE : associates
    PRODUCTS ||--o{ PRODUCT_AUDIT_LOG : tracks
    STORE ||--o{ STORE_PRODUCTS : supplies
    CHANNEL ||--o{ PRODUCTS_CHANNEL_MAPPING : channels
    COUPON ||--o{ PRODUCTS_COUPON_MAPPING : offers
    STORE_ENTERPRISE ||--o{ PRODUCTS_ENTERPRISE : manages
    USERS ||--o{ PRODUCT_AUDIT_LOG : performs

    PRODUCTS {
        UUID id PK
    }

    PRODUCTS_DETAIL_IMAGE {
        int id PK
        UUID products_id FK
    }

    STORE_PRODUCTS {
        int id PK
        int store_id FK
        UUID products_id FK
    }

    PRODUCTS_CHANNEL_MAPPING {
        int id PK
        UUID channel_id FK
        UUID products_id FK
    }

    PRODUCTS_COUPON_MAPPING {
        int id PK
        bigint coupon_id FK
        UUID products_id FK
    }

    PRODUCTS_ENTERPRISE {
        int id PK
        int store_enterprise_id FK
        UUID product_id FK
    }

    PRODUCT_AUDIT_LOG {
        int id PK
        int user_id FK
        UUID modify_id FK
    }

    STORE {
        int id PK
    }

    CHANNEL {
        UUID id PK
    }

    COUPON {
        bigint id PK
    }

    STORE_ENTERPRISE {
        int id PK
    }

    USERS {
        int id PK
    }