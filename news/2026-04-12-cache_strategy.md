# cache strategies: LRU vs TTL 🧠

**Date:** 2026-04-12  
**Category:** CS / Cache / System Design

## What I learned

Recently, I reviewed two cache strategies that appear very often:

- **LRU Cache (Least Recently Used)**
- **TTL Cache (Time To Live)**

Both are ways to answer one question:

**"💁 When should cached data be removed?"**

But they solve that question in different ways!

---

## 🫸LRU Cache — remove the least recently used data

**Core idea:**  
👉 *"If data hasn't been used for a while, it's less likely to be used again soon."*

- When the cache is full
- the system removes the **least recently used** item

### Example

```text
cache size = 3

put(A) → [A]
put(B) → [A, B]
put(C) → [A, B, C]

get(A) → [B, C, A]   // A became recently used

put(D) → [C, A, D]   // B was removed
```

### 🔮 Characteristics
- Based on access pattern
- Good at keeping hot data
- Common as a default cache eviction strategy

### ➕ Pros
- Reflects actual usage
- Usually improves cache hit rate
- Makes good use of limited memory

### ➖ Cons
- Frequently used stale data can stay in cache for a long time
- Does not consider whether data is still fresh or valid over time

---

# 🕛 TTL Cache — remove data after a fixed amount of time

Core idea:
👉 "Some data becomes less useful or invalid after a certain time."

Each cache entry has an expiration time
Once the time is over, the entry is removed

### Example

```text
A (TTL: 10s)
B (TTL: 5s)

after 5 seconds  → B expires
after 10 seconds → A expires
```

### 🔮 Characteristics
- Based on time
- Good for keeping data fresh
- Removes entries even if they are still frequently accessed

### ➕ Pros
- Helps prevent stale data
- Easy to reason about
- Useful when data validity depends on time

### ➖ Cons
- Frequently used data may still be removed
- Can reduce cache hit rate if TTL is too short

---

## Long story short, LRU vs TTL — key difference
| Aspect            | LRU                        | TTL                                 |
| ----------------- | -------------------------- | ----------------------------------- |
| Removal basis     | Usage                      | Time                                |
| Removal condition | Not used recently          | Expired                             |
| Main goal         | Better efficiency          | Better freshness                    |
| Typical use case  | Query results, image cache | Tokens, session data, API responses |

---

## So which one is better?

It depends on what matters more!! 

If you want to keep the most useful data in memory, LRU is often better 🐈‍⬛ <br/>
If you want to guarantee freshness and remove old data automatically, TTL is often better 🐈 <br/>

In real systems, they are often used together.

---
## Why this is interesting

I thought considering cache strategy is for backend, os .. optimization. <br/>
But apperently, we should consider it on frontend side as well😮 <br/>

- API response caching
- database query caching
- authentication/session storage

