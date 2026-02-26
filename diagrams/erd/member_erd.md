```mermaid
erDiagram
    MEMBERS ||--o{ STORE_COMMENT : writes
    MEMBERS ||--o{ POINT_RECORD : has
    MEMBERS ||--o{ MEMBER_COUPON_MAPPING : owns
    MEMBERS ||--o{ MEMBER_RANK_RECORD : tracks
    MEMBERS ||--o{ FEEDBACK : submits
    MEMBERS ||--o{ MEMBERS_ENTERPRISE : belongs_to
    MEMBERS }o--|| CHANNEL : registered_in
    STORE ||--o{ STORE_COMMENT : receives
    COUPON ||--o{ MEMBER_COUPON_MAPPING : distributed_to
    FEEDBACK_ITEM ||--o{ FEEDBACK : categorizes
    CHANNEL ||--o{ FEEDBACK : receives
    CHANNEL_ENTERPRISE ||--o{ MEMBERS_ENTERPRISE : manages

    MEMBERS {
        int id PK
        uuid channel_id FK
    }
    STORE_COMMENT {
        int id PK
        int store_id FK
        int member_id FK
    }
    POINT_RECORD {
        int id PK
        int member_id FK
    }
    MEMBER_COUPON_MAPPING {
        int id PK
        bigint coupon_id FK
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
    MEMBERS_ENTERPRISE {
        int id PK
        int channel_enterprise_id FK
        int member_id FK
    }
    CHANNEL {
        uuid id PK
    }
    STORE {
        int id PK
    }
    COUPON {
        bigint id PK
    }
    FEEDBACK_ITEM {
        int id PK
    }
    CHANNEL_ENTERPRISE {
        int id PK
    }