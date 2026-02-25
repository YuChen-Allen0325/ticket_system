```mermaid
erDiagram
    USERS ||--o{ USER_PERMISSION : has
    USERS ||--o{ USERS_CHANNEL_MAPPING : maps
    USERS ||--o{ USER_STORE : assigns
    USERS ||--o{ FORGOT_PASSWORD : requests
    USERS ||--o{ USER_FIRST_TIME_LOGIN : tracks
    USERS ||--o{ USERS_AUDIT_LOG : audits
    USERS ||--o{ STORE_AUDIT_LOG : modifies
    USERS ||--o{ PRODUCT_AUDIT_LOG : modifies
    USERS ||--o{ CHANNEL : creates
    USERS ||--o{ STORE : creates
    USERS ||--o{ PRODUCTS : creates
    PERMISSIONS ||--o{ USER_PERMISSION : grants
    CHANNEL ||--o{ USERS_CHANNEL_MAPPING : has
    STORE ||--o{ USER_STORE : assigns
    PRODUCTS ||--o{ PRODUCT_AUDIT_LOG : logs

    USERS {
        int id PK
        string user_name UK
        string display_name
        string user_password
    }

    USER_PERMISSION {
        int id PK
        int permission_id FK
        int user_id FK
    }

    PERMISSIONS {
        int id PK
    }

    USERS_CHANNEL_MAPPING {
        int id PK
        int user_id FK
        uuid channel_id FK
    }

    CHANNEL {
        uuid id PK
        int creator_id FK
    }

    USER_STORE {
        int id PK
        int user_id FK
        int store_id FK
    }

    STORE {
        int id PK
        int create_user_id FK
    }

    FORGOT_PASSWORD {
        int id PK
        int user_id FK
    }

    USER_FIRST_TIME_LOGIN {
        int id PK
        int user_id FK
    }

    USERS_AUDIT_LOG {
        int id PK
        int user_id FK
        int modify_id FK
    }

    STORE_AUDIT_LOG {
        int id PK
        int user_id FK
        int modify_id FK
    }

    PRODUCTS {
        uuid id PK
        int create_user_id FK
    }

    PRODUCT_AUDIT_LOG {
        int id PK
        int user_id FK
        uuid modify_id FK
    }