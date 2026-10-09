# Round 2 — Technical Interview

[← Back to main README](../README.md)

> **Reported format:** 20–35 minutes, virtual or in person. Covers your **projects**, **core CS** (OOP, DBMS, DSA, OS, CN), maybe a **small coding or debugging task**, and **awareness of current tech** (cloud, security, DevOps, and now AI). You may be asked to explain code you wrote in the assessment.

---

## 1. Your project story (prepare this first)

Interviewers spend the most time here. Prepare a **2-minute script** for your best project:

| Part | What to say | Example |
|---|---|---|
| **Problem** | What it solves, for whom | "Students at our college had no way to track lab bookings…" |
| **Your role** | What *you* built (say "I", not "we") | "I built the backend and database." |
| **Stack + why** | Technologies and why you chose them | "Spring Boot for REST APIs, MySQL because the data is relational." |
| **Hard part** | One bug or challenge and how you solved it | "Double bookings happened when two users clicked at once. I fixed it with a unique constraint and a transaction." |
| **Result** | Outcome, a number if possible | "Used by 3 labs, about 200 bookings in the first month." |
| **Improve** | What you'd do next | "Add email reminders and deploy with Docker." |

**Be ready to:** draw the architecture, explain the database tables, and say how you'd use AI to improve it.

---

## 2. Top questions to prepare

### OOP
1. Explain the 4 pillars of OOP with a real-life example.
2. Overloading vs overriding?
3. Abstract class vs interface? When would you use each?
4. What is a constructor? Can it be private?
5. What does `static` mean? `final`?

### DBMS & SQL
6. What is normalisation? Explain 1NF, 2NF, 3NF.
7. Primary key vs unique key vs foreign key?
8. Types of JOIN, with an example.
9. Write a query for the second-highest salary.
10. What are ACID properties?
11. `DELETE` vs `TRUNCATE` vs `DROP`?

### DSA & coding
12. Array vs linked list?
13. Stack vs queue, with real uses.
14. What's the time complexity of binary search? Why?
15. Reverse a string / check palindrome / find duplicates in an array (*write it*).
16. What is a HashMap and how does it work internally?
17. What is recursion? What happens without a base case?

### OS & networks
18. Process vs thread?
19. What is deadlock? Its 4 conditions?
20. What happens when you type a URL into a browser?
21. TCP vs UDP?

### Modern tech & AI (Capgemini now asks these)
22. What is cloud computing? IaaS / PaaS / SaaS?
23. What is Docker and why is it used?
24. What is Agile / Scrum?
25. **What is an LLM? What are its limitations?**
26. **What is RAG? Why is it used?**
27. **How do you use AI tools like ChatGPT or Copilot in your coding? How do you check their output?**
28. GET vs POST? What is a REST API?
29. API key vs token?
30. What is Git? Merge vs rebase?

> 📝 Answers to most of these are in [technical-mcq.md](../round-1-exceller-assessment/stage-2-technical-module/technical-mcq.md) and [ai-literacy.md](../round-1-exceller-assessment/stage-2-technical-module/ai-literacy.md).

---

## 3. How to answer

Use **Definition → Example → Where you used it**.

> *"Polymorphism means one interface with many forms. For example, a `Shape` class with a `draw()` method that `Circle` and `Square` override. In my project, I used it for different payment types sharing a `pay()` method."*

- **Don't know?** Say *"I'm not sure, but I think…"* and reason aloud. Never bluff.
- **Coding task?** Talk while you think: input → approach → edge cases → code → dry run.

---

## 🟢 Start here
| Resource | Cost | Use it for |
|---|---|---|
| [InterviewBit — Technical interview questions](https://www.interviewbit.com/technical-interview-questions/) | Free | Top questions per subject (OOP, DBMS, OS, CN, Java, SQL) |
| [GeeksforGeeks — Capgemini interview experiences](https://www.geeksforgeeks.org/interview-experiences/capgemini-interview-experience-for-analyst-on-campus-3/) | Free | Read 3–5 recent ones to see what's actually asked |
| [Tech Interview Handbook](https://www.techinterviewhandbook.org) | Free | How to behave in a coding interview |

## 🔵 Go deeper
- [Glassdoor — Capgemini interview reviews](https://www.glassdoor.co.in/Interview/Capgemini-Interview-Questions-E3803.htm)
- [Aced (formerly Exponent) — free peer mock interviews](https://www.tryexponent.com/practice) (Pramp moved here)
- YouTube: [Apna College](https://www.youtube.com/@ApnaCollegeOfficial) and [Gate Smashers](https://www.youtube.com/@GateSmashers) for quick concept revision

## 🧪 Mock it
Pair up with a classmate. One asks 5 random questions from the list above, the other answers on camera. Swap. Watch the recording once and fix filler words ("basically", "actually", "umm").
