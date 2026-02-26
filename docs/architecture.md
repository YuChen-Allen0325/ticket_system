** Caching Strategy **

✅ Cache Aside Pattern (Lazy Cache)
Flow:
⭐ Read from Redis → If miss → Query DB → Write back to Redis → Return result

Benefits:
1️⃣ Reduces DB pressure
2️⃣ Improves read performance


✅ TTL Design
● Hot data: Short TTL
● Config data: Long TTL
● maxmemory-policy: volatile-lru

Prevents:
1️⃣ Cache avalanche
2️⃣ Stale data accumulation


✅ Cache Invalidation (Ensure data consistency)
● Delete cache on update
● Use distributed lock to avoid race condition