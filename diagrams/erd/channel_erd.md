```mermaid
erDiagram
	direction TB
	CHANNEL {
		UUID id PK ""  
	}

	BRAND_CHANNEL_MAPPING {
		int id PK ""  
		int brand_id FK ""  
		UUID channel_id FK ""  
	}

	SERVICE {
		int id PK ""  
		UUID channel_id FK ""  
	}

	STORE_CHANNEL_MAPPING {
		int id PK ""  
		int store_id FK ""  
		UUID channel_id FK ""  
	}

	THEME_STORE {
		int id PK ""  
		UUID channel_id FK ""  
	}

	MEMBER {
		int id PK ""  
		UUID channel_id FK ""  
	}

	KEYWORD {
		int id PK ""  
		UUID channel_id FK ""  
	}

	COUPON {
		UUID id PK ""  
		UUID channel_id FK ""  
		int store_id FK ""  
	}

	ELECTRONIC_TICKET {
		UUID id PK ""  
		UUID channel_id FK ""  
		int store_id FK ""  
	}

	CHANNEL_POINT_RANK {
		int id PK ""  
		UUID channel_id FK ""  
	}

	USERS_CHANNEL_MAPPING {
		int id PK ""  
		int user_id FK ""  
		UUID channel_id FK ""  
	}

	COUPON_CHANNEL_MAPPING {
		int id PK ""  
		UUID channel_id FK ""  
		UUID coupon_id FK ""  
	}

	TICKET_CHANNEL_MAPPING {
		int id PK ""  
		UUID channel_id FK ""  
		UUID ticket_id FK ""  
	}

	PRODUCTS_CHANNEL_MAPPING {
		int id PK ""  
		UUID channel_id FK ""  
		UUID products_id FK ""  
	}

	RECOMMEND_STORE {
		bigint id PK ""  
		UUID channel_id FK ""  
		bigint store_id FK ""  
	}

	FEEDBACK {
		int id PK ""  
		UUID channel_id FK ""  
		int feedback_item_id FK ""  
		int member_id FK ""  
	}

	STORE_COMMENT {
		UUID channel_id FK ""  
	}

	RECOMMENDATION_ENROLL {
		int id PK ""  
		UUID channel_id FK ""  
	}

	STORE_RECOMMEND_LABEL {
		int id PK ""  
		UUID channel_id FK ""  
	}

	CHANNEL_ENTERPRISE {
		int id PK ""  
		UUID channel_id FK ""  
		int enterprise_id FK ""  
	}

	PRODUCTS {
		UUID id PK ""  
		bigint store_id FK ""  
		UUID channel_id FK ""  
	}

	BRAND {
		int id PK ""  
	}

	STORE {
		bigint id PK ""  
	}

	USERS {
		int id PK ""  
	}

	FEEDBACK_ITEM {
		int id PK ""  
	}

	MEMBERS {
		int id PK ""  
	}

	ENTERPRISE {
		int id PK ""  
	}

	CHANNEL||--o{BRAND_CHANNEL_MAPPING:"has"
	CHANNEL||--o{SERVICE:"has"
	CHANNEL||--o{STORE_CHANNEL_MAPPING:"has"
	CHANNEL||--o{THEME_STORE:"has"
	CHANNEL||--o{MEMBER:"has"
	CHANNEL||--o{KEYWORD:"has"
	CHANNEL||--o{COUPON:"has"
	CHANNEL||--o{ELECTRONIC_TICKET:"has"
	CHANNEL||--o{CHANNEL_POINT_RANK:"has"
	CHANNEL||--o{USERS_CHANNEL_MAPPING:"has"
	CHANNEL||--o{COUPON_CHANNEL_MAPPING:"has"
	CHANNEL||--o{TICKET_CHANNEL_MAPPING:"has"
	CHANNEL||--o{PRODUCTS_CHANNEL_MAPPING:"has"
	CHANNEL||--o{RECOMMEND_STORE:"has"
	CHANNEL||--o{FEEDBACK:"has"
	CHANNEL||--o{STORE_COMMENT:"has"
	CHANNEL||--o{RECOMMENDATION_ENROLL:"has"
	CHANNEL||--o{STORE_RECOMMEND_LABEL:"has"
	CHANNEL||--o{CHANNEL_ENTERPRISE:"has"
	CHANNEL||--o{PRODUCTS:"has"
	BRAND||--o{BRAND_CHANNEL_MAPPING:"has"
	STORE||--o{STORE_CHANNEL_MAPPING:"has"
	STORE||--o{COUPON:"has"
	STORE||--o{ELECTRONIC_TICKET:"has"
	STORE||--o{RECOMMEND_STORE:"has"
	STORE||--o{PRODUCTS:"has"
	COUPON||--o{COUPON_CHANNEL_MAPPING:"has"
	ELECTRONIC_TICKET||--o{TICKET_CHANNEL_MAPPING:"has"
	PRODUCTS||--o{PRODUCTS_CHANNEL_MAPPING:"has"
	USERS||--o{USERS_CHANNEL_MAPPING:"has"
	FEEDBACK_ITEM||--o{FEEDBACK:"has"
	MEMBERS||--o{FEEDBACK:"has"
	ENTERPRISE||--o{CHANNEL_ENTERPRISE:"has"
	STORE_COMMENT||--o{CHANNEL:"has"