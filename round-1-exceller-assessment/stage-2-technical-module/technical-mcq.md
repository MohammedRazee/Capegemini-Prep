# Technical MCQ One-Liners

[← Back to Stage 2](README.md)

> Quick revision of the Section 2 topics. If any line is new to you, look it up in the linked resource.

---

## OOP
- **4 pillars:** Encapsulation (hide data behind methods), Abstraction (show *what*, hide *how*), Inheritance (reuse a parent's features), Polymorphism (one interface, many forms).
- **Overloading** = same method name, different parameters (compile time). **Overriding** = child redefines the parent's method (runtime).
- **Abstract class** can have state and concrete methods; a class extends only one. **Interface** is a contract; a class can implement many.
- **Constructor** has no return type and runs when the object is created. Java calls the parent's constructor first.
- `static` belongs to the class, not the object. `final` means it can't be changed, overridden or extended.
- Access: `private` < default (package) < `protected` < `public`.

## DBMS & SQL
- **Primary key**: unique + not null. **Foreign key**: references another table's primary key. **Candidate key**: any column(s) that could be the primary key.
- **Normalisation:** 1NF (atomic values), 2NF (no partial dependency), 3NF (no transitive dependency). It reduces redundancy.
- **ACID:** Atomicity, Consistency, Isolation, Durability.
- **JOINs:** INNER (matches only), LEFT (all left + matches), RIGHT, FULL (all from both).
- `WHERE` filters rows **before** grouping; `HAVING` filters groups **after** `GROUP BY`.
- `DELETE` removes rows (can roll back, has WHERE). `TRUNCATE` removes all rows (fast). `DROP` removes the table.
- Order of execution: FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY → LIMIT.
- Second highest salary: `SELECT MAX(salary) FROM emp WHERE salary < (SELECT MAX(salary) FROM emp);`

## REST APIs & HTTP
| Method | Use | Safe? | Idempotent? |
|---|---|---|---|
| GET | Read | ✅ | ✅ |
| POST | Create | ❌ | ❌ |
| PUT | Replace/update fully | ❌ | ✅ |
| PATCH | Partial update | ❌ | ❌ (usually) |
| DELETE | Remove | ❌ | ✅ |

- **Status codes:** 200 OK · 201 Created · 204 No Content · 301 Moved · 400 Bad Request · 401 Unauthorized (not logged in) · 403 Forbidden (logged in, not allowed) · 404 Not Found · 500 Server Error · 503 Service Unavailable.
- **REST** = stateless, resource-based URLs (`/users/42`), usually JSON.
- **Idempotent** = calling it many times has the same effect as calling it once.

## Git
- `git init` · `clone` · `add` (stage) · `commit` (save a snapshot) · `push` (upload) · `pull` (= fetch + merge) · `branch` · `checkout`/`switch` · `merge` · `rebase` · `stash` (park changes).
- **Merge conflict** = two branches changed the same lines. You fix it manually, then commit.
- `.gitignore` lists files Git should not track.

## Client-server, cloud, networking
- **Client** requests, **server** responds. HTTP runs over TCP. **HTTPS** = HTTP + TLS encryption.
- **IaaS** (you manage the OS: AWS EC2) · **PaaS** (you manage only the code: Heroku, App Engine) · **SaaS** (you just use it: Gmail).
- **Public / private / hybrid** cloud. Benefits: scalability, pay-as-you-go, high availability.
- **DNS** converts a domain name to an IP address. **TCP** = reliable and ordered (web, email). **UDP** = fast, no guarantee (video, gaming).
- Ports: 22 SSH · 53 DNS · 80 HTTP · 443 HTTPS · 3306 MySQL.
- OSI layers: Physical, Data Link, Network, Transport, Session, Presentation, Application.

## API keys vs tokens (asked specifically!)
| API key | Token (e.g., OAuth / JWT) |
|---|---|
| Identifies the **application/project** | Represents an **authenticated user/session** |
| Usually long-lived, static | Short-lived, **expires**, can be refreshed |
| Coarse access | **Scoped** permissions |
| Keep it secret; never commit it to GitHub | Sent in the `Authorization: Bearer <token>` header |

## Cybersecurity basics
- **CIA triad:** Confidentiality, Integrity, Availability.
- **Phishing** = fake messages that trick you into giving credentials. **SQL injection** = malicious SQL in an input field; prevent it with parameterised queries. **XSS** = injected scripts in web pages.
- **Hashing** (one-way, used for passwords) vs **encryption** (two-way, needs a key).
- **MFA**, least privilege, patching, strong passwords.

## Agile, DevOps, Docker
- **Agile/Scrum:** short **sprints** (1–4 weeks), daily **stand-up**, **product backlog**, sprint review and retrospective. Roles: Product Owner, Scrum Master, Dev Team.
- **DevOps** = dev + ops working together; automation; **CI** (auto build/test on every commit) and **CD** (auto deploy).
- **Docker container** = app + its dependencies, sharing the host OS kernel. Lightweight compared with a **VM**, which has a full guest OS.
- **Image** = blueprint, **container** = running instance, **Dockerfile** = recipe to build the image.

## DSA — complexity table
| Operation | Time |
|---|---|
| Array access by index | O(1) |
| Linear search | O(n) |
| Binary search (sorted) | O(log n) |
| HashMap get/put (average) | O(1) |
| Bubble / Insertion / Selection sort | O(n²) |
| Merge sort / Heap sort | O(n log n) |
| Quick sort | O(n log n) average, O(n²) worst |
| Nested loop over n | O(n²) |
| Halving loop (`i = i/2`) | O(log n) |

- **Stack** = LIFO (undo, recursion). **Queue** = FIFO (scheduling, BFS).
- **Hashing** is used for counting frequencies, finding duplicates and two-sum problems.
