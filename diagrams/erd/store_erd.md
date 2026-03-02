```mermaid
erDiagram
    BRAND ||--o{ STORE : "references"
    CATEGORY ||--o{ STORE : "references"
    STORE ||--o{ STORE_CHANNEL_MAPPING : "has"
    STORE ||--o{ STORE_SERVICE_MAPPING : "has"
    STORE ||--o{ STORE_BUSINESS_TIME_MAPPING : "has"
    STORE ||--o{ THEME_STORE_MAPPING : "has"
    STORE ||--o{ STORE_DETAIL_IMAGE : "has"
    STORE ||--o{ STORE_COMMENT : "has"
    STORE ||--o{ USER_STORE : "has"
    STORE ||--o{ STORE_PRODUCTS : "has"
    STORE ||--o{ RECOMMEND_STORE : "has"
    STORE ||--o{ STORE_ENTERPRISE : "has"
    STORE ||--o{ STORE_AUDIT_LOG : "modified_by"
    CHANNEL ||--o{ STORE_CHANNEL_MAPPING : "references"
    CHANNEL ||--o{ RECOMMEND_STORE : "references"
    SERVICE ||--o{ STORE_SERVICE_MAPPING : "references"
    THEME_STORE ||--o{ THEME_STORE_MAPPING : "references"
    MEMBER ||--o{ STORE_COMMENT : "references"
    USERS ||--o{ USER_STORE : "references"
    USERS ||--o{ STORE_AUDIT_LOG : "references"
    PRODUCTS ||--o{ STORE_PRODUCTS : "references"
    CHANNEL_ENTERPRISE ||--o{ STORE_ENTERPRISE : "references"
    PRODUCTS ||--o{ STORE : "has_optional_ref"
    FEEDBACK ||--o{ STORE : "has_optional_ref"

    BRAND {
        int id PK
    }
    CATEGORY {
        int id PK
    }
    STORE {
        int id PK
        int brand_id FK
        int category_id FK
    }
    STORE_CHANNEL_MAPPING {
        int id PK
        int store_id FK
        uuid channel_id FK
    }
    STORE_SERVICE_MAPPING {
        int id PK
        int store_id FK
        int service_id FK
    }
    STORE_BUSINESS_TIME_MAPPING {
        int id PK
        int store_id FK
    }
    THEME_STORE_MAPPING {
        int id PK
        int store_id FK
        int theme_store_id FK
    }
    STORE_DETAIL_IMAGE {
        int id PK
        int store_id FK
    }
    STORE_COMMENT {
        int id PK
        int store_id FK
        int member_id FK
    }
    USER_STORE {
        int id PK
        int user_id FK
        int store_id FK
    }
    STORE_PRODUCTS {
        int id PK
        int store_id FK
        uuid products_id FK
    }
    RECOMMEND_STORE {
        bigint id PK
        uuid channel_id FK
        bigint store_id FK
    }
    CHANNEL {
        uuid id PK
    }
    SERVICE {
        int id PK
    }
    THEME_STORE {
        int id PK
    }
    MEMBER {
        int id PK
    }
    USERS {
        int id PK
    }
    PRODUCTS {
        uuid id PK
        bigint store_id FK
        uuid channel_id FK
    }
    CHANNEL_ENTERPRISE {
        int id PK
    }
    STORE_ENTERPRISE {
        int id PK
        int channel_enterprise_id FK
        int store_id FK
    }
    STORE_AUDIT_LOG {
        int id PK
        int user_id FK
        int modify_id FK
    }
    FEEDBACK {
        int id PK
        int store_id FK
    }