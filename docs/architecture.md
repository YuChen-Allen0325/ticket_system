**Caching Strategy**

<br>✅ Cache Aside Pattern (Lazy Cache)<br>
Flow:<br>
⭐ Read from Redis → If miss → Query DB → Write back to Redis → Return result<br>
Benefits:<br>
1️⃣ Reduces DB pressure<br>
2️⃣ Improves read performance<br>
<br>

✅ TTL Design<br>
● Hot data: Short TTL<br>
● Config data: Long TTL<br>
● maxmemory-policy: volatile-lru<br>
Prevents:<br>
1️⃣ Cache avalanche<br>
2️⃣ Stale data accumulation<br>
<br>

✅ Cache Invalidation (Ensure data consistency)<br>
● Delete cache on update<br>
● Use distributed lock to avoid race condition<br>

**DB Design**

<br>✅1-to-N relationship<br>
✅leverage database transaction locks to enforce isolation between conflicting operations<br>
✅Composite index for high-frequency queries<br>
✅Avoid full table scan<br>
✅Covering index optimization<br>


**Worker Design**

<br>✅heavy batch service<br>
✅daily processing tasks<br>