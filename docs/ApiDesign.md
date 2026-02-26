** API Layered Architecture **

1️⃣ Controller Layer (DRF View Layer)
● Handles HTTP request / response
● Parameter validation
● Authentication & authorization
● Calls service layer only (no business logic here)

2️⃣ Service Layer
● Core business logic
● Transaction control
● Distributed lock (Redis / Redlock)

3️⃣ Repository Layer
● Pure data access logic
● PostgreSQL ORM
● No business logic