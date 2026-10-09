# Pseudocode & Output Prediction

[← Back to Stage 2](README.md)

> The "Programming Logic" part of Section 2 gives you short pseudocode and asks for the output. Speed comes from **one habit: the trace table.**

## The trace table method

Write one column per variable and one row per loop iteration, and update the values as you go. Don't do it in your head.

```
a = 5, b = 3
for i = 1 to 3:  a = a + b ; b = a - b
```
| i | a | b |
|---|---|---|
| start | 5 | 3 |
| 1 | 8 | 5 |
| 2 | 13 | 8 |
| 3 | 21 | 13 |

Output → `21 13`

## Traps to watch for
- **Integer division:** `7 / 2 = 3`, not 3.5.
- **`mod`** gives the remainder: `17 mod 5 = 2`.
- **Loop bounds:** `for i = 1 to 5` runs 5 times; `for (i = 0; i < 5; i++)` also runs 5 times; `i <= 5` starting at 0 runs **6** times.
- **Call by value vs reference:** changing a plain number inside a function doesn't change the caller's variable; changing an **array element** does.
- **Bitwise:** `&` AND, `|` OR, `^` XOR, `<<` multiply by 2, `>>` divide by 2.
- **Undefined behaviour in C**, e.g. `i++ + ++i`: if an option says "undefined/compiler dependent", that's often the right answer.

---

## 🧪 Practice (try each in under 1 minute)

**Q1**
```
Integer x = 10, count = 0
while x > 1
    x = x / 2          // integer division
    count = count + 1
print count
```

**Q2**
```
function f(n)
    if n <= 1 return 1
    return n * f(n - 2)
print f(7)
```

**Q3**
```
Integer a = 12, b = 10
print (a & b) + (a | b) + (a ^ b)
```

**Q4**
```
count = 0
for i = 1 to 4
    for j = i to 4
        count = count + 1
print count
```

**Q5**
```
Integer n = 4321, s = 0
while n > 0
    s = s * 10 + (n mod 10)
    n = n / 10
print s
```

**Q6**
```
function change(Integer x)
    x = x + 10
Integer a = 5
change(a)
print a
```

**Q7**
```
function modify(Array arr)
    arr[0] = 100
Array nums = [1, 2, 3]
modify(nums)
print nums[0]
```

**Q8**
```
Integer a = 7, b = 4, c = 9
if (a > b AND a > c) print a
else if (b > c) print b
else print c
```

<details>
<summary><b>Show answers</b></summary>

| Q | Answer | Why |
|---|---|---|
| 1 | **3** | 10→5→2→1, three divisions |
| 2 | **105** | 7 × 5 × 3 × 1 |
| 3 | **28** | 12=1100, 10=1010 → AND 8, OR 14, XOR 6 |
| 4 | **10** | 4 + 3 + 2 + 1 |
| 5 | **1234** | Reverses the digits |
| 6 | **5** | Call by value; the caller's `a` is unchanged |
| 7 | **100** | Arrays are passed by reference |
| 8 | **9** | a > c is false; b > c is false → else |

</details>

**More practice:** [PrepInsta Capgemini pseudocode](https://prepinsta.com/capgemini/) · [GeeksforGeeks quizzes](https://www.geeksforgeeks.org/quizzes/)
