```mermaid
erDiagram
    CHANNEL ||--o{ MEMBERS : references
    CHANNEL ||--o{ FEEDBACK : references
    MEMBERS ||--o{ STORE_COMMENT : creates
    MEMBERS ||--o{ MEMBER_COUPON_MAPPING : uses
    MEMBERS ||--o{ MEMBER_TICKET_MAPPING : uses
    MEMBERS ||--o{ POINT_RECORD : accumulates
    MEMBERS ||--o{ MEMBER_RANK_RECORD : has
    MEMBERS ||--o{ FEEDBACK : provides
    MEMBERS ||--o{ MEMBERS_ENTERPRISE : associates
    STORE ||--o{ STORE_COMMENT : receives
    COUPON ||--o{ MEMBER_COUPON_MAPPING : maps
    COUPON ||--o{ MEMBER_TICKET_MAPPING : maps
    CHANNEL_ENTERPRISE ||--o{ MEMBERS_ENTERPRISE : references
    FEEDBACK_ITEM ||--o{ FEEDBACK : references

    MEMBERS {
        int id PK
        uuid channel_id FK
    }

    CHANNEL {
        uuid id PK
    }

    STORE_COMMENT {
        int id PK
        int store_id FK
        int member_id FK
    }

    STORE {
        int id PK
    }

    MEMBER_COUPON_MAPPING {
        int id PK
        int member_id FK
        uuid coupon_id FK
    }

    MEMBER_TICKET_MAPPING {
        int id PK
        int member_id FK
        uuid coupon_id FK
    }

    COUPON {
        uuid id PK
    }

    POINT_RECORD {
        int id PK
        int member_id FK
    }

    MEMBER_RANK_RECORD {
        bigint id PK
        bigint member_id FK
    }

    FEEDBACK {
        int id PK
        uuid channel_id FK
        int feedback_item_id FK
        int member_id FK
    }

    FEEDBACK_ITEM {
        int id PK
    }

    MEMBERS_ENTERPRISE {
        int id PK
        int channel_enterprise_id FK
        int member_id FK
    }

    CHANNEL_ENTERPRISE {
        int id PK
    }