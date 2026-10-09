# Stage 4 — AI-Assisted Coding

[← Back to stages](../README.md)

> You solve a coding problem **with an AI assistant inside the test**. The test is **scaffolded**: you give clear inputs at each step to unlock the next, ending with code generation.
> **You are graded on the process, not just the final code.**

## What's evaluated (from Capgemini's briefing)

| # | Criterion | In plain words |
|---|---|---|
| 1 | **AI literacy** | Do you understand the question and respond meaningfully at each step? |
| 2 | **Prompt quality** | Structured, relevant prompts, **not** random one-liners |
| 3 | **Problem solving** | Do *you* choose the approach and guide the AI to it? |
| 4 | **Review & adapt** | Do you check and improve the code instead of copy-pasting? |

---

## The 4-step prompt template

Memorise this. It matches the scaffolding.

| Step | You tell the AI | Template |
|---|---|---|
| **1. FRAME** | The problem in your own words, with inputs, output, **constraints from the statement** and edge cases | *"Problem: … Input: … Output: … Constraints: n ≤ 10⁵, values can be negative. Edge cases: empty array, one element, duplicates."* |
| **2. APPROACH** | Your plan, and ask it to compare | *"I plan to use a HashMap to store seen values, giving O(n) time. Compare this with brute force O(n²) and confirm it fits the constraints."* |
| **3. IMPLEMENT** | Language, function signature, what to handle | *"Write this in Java as `int[] twoSum(int[] nums, int target)`. Return `{-1, -1}` if no pair exists. Add brief comments."* |
| **4. REVIEW** | Ask for edge cases and tests, then **read the code yourself** | *"List the edge cases this code could fail and give 5 test cases including boundaries."* Then fix anything that's off and submit. |

---

## Worked example

**Problem:** *Given an integer array `nums` and an integer `target`, return the indices of two numbers that add up to `target`. Each input has at most one solution.*

| ❌ Weak prompt | ✅ Strong prompt |
|---|---|
| "write code" | "Problem: find indices of two numbers in `nums` that sum to `target`. Input: int array (length up to 10⁴, values from −10⁹ to 10⁹) and int target. Output: an array of two indices. Edge cases: no valid pair, negative numbers, same value used twice (e.g. [3,3], target 6)." |
| "best approach?" | "Brute force checks every pair, O(n²). I want a single pass with a HashMap from value to index: for each number, check whether `target - num` is already in the map. Is that O(n) time and O(n) space? Any pitfalls?" |
| "give java code" | "Implement the HashMap approach in Java as `public int[] twoSum(int[] nums, int target)`. Check the map **before** inserting the current number so the same element isn't used twice. Return `new int[]{-1, -1}` if no pair is found." |
| *(submits without reading)* | "Give 5 test cases: [2,7,11,15] target 9, [3,3] target 6, [-1,-2,-3] target -5, [1,2] target 10, a single-element array." *Then you trace one test by hand before submitting.* |

---

## Review checklist (before you submit)

- [ ] Does the function signature match what the problem asked for?
- [ ] Did the AI use the **sample values as fixed constraints**? (A common trap: never hard-code the sample input.)
- [ ] Loop bounds correct? Any off-by-one?
- [ ] Handles empty input, one element, duplicates and negatives?
- [ ] Time complexity fits the constraints?
- [ ] Do **you** understand every line? If not, ask: *"Explain line 7."*

---

## Dos and don'ts (from Capgemini's briefing)

| ✅ DO | ❌ DON'T |
|---|---|
| Read each question and instruction carefully | Type vague prompts like "write the code" |
| **Think first**, then tell the AI your plan | Copy sample text or numbers as constraints |
| Check and edit code before running it | Rely blindly on the AI or submit code you don't understand |
| Test with a couple of examples if time permits | Use external tools or phones, or discuss with others |

---

## 🧪 How to practise (free)

1. Pick 2 easy problems a day from [Striver A2Z](https://takeuforward.org/prep-hub/strivers-a2z-dsa-sheet) or [NeetCode](https://neetcode.io/practice).
2. Open any free assistant ([ChatGPT](https://chatgpt.com), [Claude](https://claude.ai), [Gemini](https://gemini.google.com), or [GitHub Copilot Free](https://github.com/features/copilot) in VS Code).
3. Solve the problem **only through prompts**, following the 4 steps above. Save your prompts.
4. Then ask the AI: *"Rate my prompts on clarity, structure and completeness out of 10 and tell me what to improve."*

## 🔵 Go deeper
- [Anthropic Prompt Engineering Tutorial](https://github.com/anthropics/prompt-eng-interactive-tutorial), chapters 1–6
- [FACE Prep — Exceller AI-assisted coding guide](https://faceprep.in/article/capgemini-exceller-ai-assisted-coding-round-2026/)
- [Capgemini-2027 community repo — AI-assisted coding chapter](https://github.com/himanshulokhande26/Capgemini-2027-Preparation/blob/main/sections/04-ai-assisted-coding.md), with weak vs strong prompt examples
