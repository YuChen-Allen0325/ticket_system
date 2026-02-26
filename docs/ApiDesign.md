**API Layered Architecture**

1️⃣ Controller Layer (DRF View Layer)<br>
● Handles HTTP request / response<br>
● Parameter validation<br>
● Authentication & authorization<br>
● Calls service layer only (no business logic here)<br>
<br>
2️⃣ Service Layer<br>
● Core business logic<br>
● Transaction control<br>
● Distributed lock (Redis / Redlock)<br>
<br>
3️⃣ Repository Layer<br>
● Pure data access logic<br>
● PostgreSQL ORM<br>
● No business logic<br>