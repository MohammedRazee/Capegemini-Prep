# Stage 3 — Debugging Assessment

[← Back to stages](../README.md)

> **Format:** 1 question · ~20 minutes · **C, C++ or Java**.
> You get a problem statement and code with **one or more** bugs (logic, syntax or runtime). Fix it so it passes the test cases.
> Capgemini's briefing lists **trees, graphs, 2D dynamic programming and other advanced DSA** among the concepts covered.

---

## The 4-step routine

| Step | What to do | Time |
|---|---|---|
| **1. Review** | Read the problem statement fully. Note the input, the expected output and the constraints. Then read the code top to bottom **without editing**. | 4 min |
| **2. Identify** | Hunt by category: **syntax** (won't compile) → **runtime** (crashes: index, null, divide by zero) → **logic** (wrong answer). Assume there's **more than one bug**. | 6 min |
| **3. Fix** | Make the **smallest** change that fixes each bug. Don't rewrite the whole function. | 5 min |
| **4. Validate** | Dry-run with the sample input, then edge cases: **empty input, one element, all same, negatives, maximum size**. | 5 min |

---

## The usual suspects (check these first)

| # | Bug | Example | Fix |
|---|---|---|---|
| 1 | **Off-by-one** loop bound | `i <= n` on an array of size n | `i < n` |
| 2 | **Wrong initial value** | `max = 0` (fails for all-negative input) | `max = arr[0]` |
| 3 | **`=` vs `==`** (C/C++) | `if (x = 5)` | `if (x == 5)` |
| 4 | **String comparison** (Java) | `s1 == s2` | `s1.equals(s2)` |
| 5 | **Integer overflow** | `int` factorial of 20 | `long` / `long long` |
| 6 | **Integer division** | `avg = sum / n` with ints | `(double) sum / n` |
| 7 | **Missing `return` / `break`** | switch falls through; function returns nothing | add it |
| 8 | **Wrong base case** in recursion | `if (root == null) return 1` | `return 0` |
| 9 | **Infinite loop** | `low = mid` in binary search | `low = mid + 1` |
| 10 | **Null / missing key** | `map.get(c) + 1` on a new key | `map.getOrDefault(c, 0) + 1` |
| 11 | **Wrong index** in a mirror comparison | `s[n - i]` | `s[n - 1 - i]` |
| 12 | **Uninitialised DP table** | first row/column never set | initialise the base cases |
| 13 | **Missing `visited`** in graph DFS/BFS | infinite recursion on cycles | mark visited before recursing |
| 14 | **Wrong comparison operator** | `<` instead of `>` in sort or swap | flip it |

---

## 🧪 Practice

👉 **[practice-bugs.md](practice-bugs.md)**: 10 buggy programs in C and Java, from easy to tree/graph/DP, with answers hidden.

**How to practise:** 10 minutes per bug, no running the code at first; find the bugs by reading. Then run it to confirm.

## 🟢 Start here (outside this repo)
| Resource | Cost | What to do |
|---|---|---|
| [FACE Prep — Exceller debugging guide](https://faceprep.in/article/capgemini-exceller-debugging-assessment-2026/) | Free | Bug categories and practice routine for this exact stage |
| [Striver A2Z DSA Sheet](https://takeuforward.org/prep-hub/strivers-a2z-dsa-sheet) | Free | Solve easy array/string problems; you can't debug what you can't write |
| **Make your own bugs** | Free | Take any problem you solved, ask a friend or an AI to "inject 2 subtle bugs without telling me where", then fix them in 10 minutes |

## 🔵 Go deeper (for the "advanced DSA" topics)
- Trees: traversals (in/pre/post/level order), height, BST insert and search → A2Z Step 13–14
- Graphs: BFS/DFS on grids, visited arrays, number of islands → A2Z Step 15
- 2D DP: unique grid paths, minimum path sum, LCS → A2Z Step 16
- YouTube: [takeUforward](https://www.youtube.com/@takeUforward) (DP and graph playlists)

## 🐍 Python-only? Read this
Debugging is in **C, C++ or Java only**. Spend 2 hours learning to **read** Java: `for` loops, arrays (`int[] a = new int[n]`), `String` methods (`charAt`, `length()`, `equals`), `ArrayList`, `HashMap` (`put`, `get`, `getOrDefault`). You only need to read and fix it, not write it from scratch.
→ [takeUforward — Learn Java](https://takeuforward.org/strivers-a2z-dsa-sheet/learning/learn-java)
