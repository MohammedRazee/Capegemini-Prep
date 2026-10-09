# 🧪 Debugging Practice — 10 Bugs

[← Back to Stage 3](README.md)

> Each program has **one or more** bugs. Give yourself **10 minutes**. Find them by reading first, then compile and run to check.
> Every answer has been compiled and tested (GCC / Java 21).

| # | Problem | Language | Level |
|---|---|---|---|
| 1 | [Sum of an array](#1-sum-of-an-array) | Java | Easy |
| 2 | [Maximum element](#2-maximum-element) | C | Easy |
| 3 | [Compare usernames](#3-compare-usernames) | Java | Easy |
| 4 | [Factorial up to 20](#4-factorial-up-to-20) | C | Easy |
| 5 | [Binary search](#5-binary-search) | Java | Medium |
| 6 | [Palindrome check](#6-palindrome-check) | C | Medium |
| 7 | [First non-repeating character](#7-first-non-repeating-character) | Java | Medium |
| 8 | [Height of a binary tree](#8-height-of-a-binary-tree) | Java | Hard (Trees) |
| 9 | [Unique paths in a grid](#9-unique-paths-in-a-grid) | Java | Hard (2D DP) |
| 10 | [Number of islands (DFS)](#10-number-of-islands-dfs) | Java | Hard (Graphs) |

---

## 1. Sum of an array
**Level:** Easy · **Language:** Java · **Expected:** Should print `108`.

```java
public class Bug1 {
    static int sumArray(int[] arr) {
        int sum;
        for (int i = 0; i <= arr.length; i++) {
            sum += arr[i];
        }
        return sum;
    }
    public static void main(String[] args) {
        System.out.println(sumArray(new int[]{4, 8, 15, 16, 23, 42}));
    }
}
```

<details>
<summary><b>Hint</b></summary>

There are **2** bug(s) to fix.

</details>

<details>
<summary><b>Answer</b></summary>

- **Compile error:** `int sum;` is never initialised → `int sum = 0;`
- **Runtime error:** `i <= arr.length` reads past the end (`ArrayIndexOutOfBoundsException`) → `i < arr.length`

**Fixed code:**

```java
public class Bug1 {
    static int sumArray(int[] arr) {
        int sum = 0;
        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];
        }
        return sum;
    }
    public static void main(String[] args) {
        System.out.println(sumArray(new int[]{4, 8, 15, 16, 23, 42}));
    }
}
```

</details>

---

## 2. Maximum element
**Level:** Easy · **Language:** C · **Expected:** Should print `-2` (largest of all-negative numbers).

```c
#include <stdio.h>

int findMax(int arr[], int n) {
    int max = 0;
    for (int i = 0; i < n; i++) {
        if (arr[i] < max)
            max = arr[i];
    }
    return max;
}

int main() {
    int a[] = {-5, -2, -9, -14};
    printf("%d\n", findMax(a, 4));
    return 0;
}
```

<details>
<summary><b>Hint</b></summary>

There are **2** bug(s) to fix.

</details>

<details>
<summary><b>Answer</b></summary>

- **Wrong initial value:** `max = 0` is bigger than every element in an all-negative array → `max = arr[0]` (loop can start at `i = 1`)
- **Wrong comparison:** `arr[i] < max` finds the minimum → `arr[i] > max`

**Fixed code:**

```c
#include <stdio.h>

int findMax(int arr[], int n) {
    int max = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] > max)
            max = arr[i];
    }
    return max;
}

int main() {
    int a[] = {-5, -2, -9, -14};
    printf("%d\n", findMax(a, 4));
    return 0;
}
```

</details>

---

## 3. Compare usernames
**Level:** Easy · **Language:** Java · **Expected:** Should print `true`.

```java
public class Bug3 {
    // Returns true if two usernames are the same, ignoring case
    static boolean sameUser(String a, String b) {
        return a.toLowerCase() == b.toLowerCase();
    }
    public static void main(String[] args) {
        System.out.println(sameUser("Priya", "PRIYA"));
    }
}
```

<details>
<summary><b>Hint</b></summary>

There is **1** bug(s) to fix.

</details>

<details>
<summary><b>Answer</b></summary>

- **String compared with `==`:** compares references, not content → `a.toLowerCase().equals(b.toLowerCase())` (or `a.equalsIgnoreCase(b)`)

**Fixed code:**

```java
public class Bug3 {
    // Returns true if two usernames are the same, ignoring case
    static boolean sameUser(String a, String b) {
        return a.toLowerCase().equals(b.toLowerCase());
    }
    public static void main(String[] args) {
        System.out.println(sameUser("Priya", "PRIYA"));
    }
}
```

</details>

---

## 4. Factorial up to 20
**Level:** Easy · **Language:** C · **Expected:** Should print `120` and `2432902008176640000`.

```c
#include <stdio.h>

/* Return n! for 0 <= n <= 20 */
int factorial(int n) {
    int fact = 1;
    for (int i = 0; i <= n; i++)
        fact *= i;
    return fact;
}

int main() {
    printf("%d\n", factorial(5));
    printf("%d\n", factorial(20));
    return 0;
}
```

<details>
<summary><b>Hint</b></summary>

There are **3** bug(s) to fix.

</details>

<details>
<summary><b>Answer</b></summary>

- **Loop starts at 0:** multiplying by 0 makes everything 0 → `i = 1`
- **Overflow:** 20! doesn't fit in `int` → use `long long` for the variable and return type
- **Format specifier:** `%d` → `%lld` for `long long`

**Fixed code:**

```c
#include <stdio.h>

/* Return n! for 0 <= n <= 20 */
long long factorial(int n) {
    long long fact = 1;
    for (int i = 1; i <= n; i++)
        fact *= i;
    return fact;
}

int main() {
    printf("%lld\n", factorial(5));
    printf("%lld\n", factorial(20));
    return 0;
}
```

</details>

---

## 5. Binary search
**Level:** Medium · **Language:** Java · **Expected:** Should print `4` then `-1`.

```java
public class Bug5 {
    // Return index of target in sorted array, or -1
    static int binarySearch(int[] a, int target) {
        int low = 0, high = a.length - 1;
        while (low < high) {
            int mid = (low + high) / 2;
            if (a[mid] == target) return mid;
            else if (a[mid] < target) low = mid;
            else high = mid - 1;
        }
        return -1;
    }
    public static void main(String[] args) {
        int[] a = {1, 3, 5, 7, 9};
        System.out.println(binarySearch(a, 9));
        System.out.println(binarySearch(a, 4));
    }
}
```

<details>
<summary><b>Hint</b></summary>

There are **2** bug(s) to fix.

</details>

<details>
<summary><b>Answer</b></summary>

- **Loop condition:** `low < high` skips the case where one element is left → `low <= high`
- **Infinite loop:** `low = mid` never moves past mid → `low = mid + 1`
- *(Good practice)* `mid = low + (high - low) / 2` avoids overflow for very large indexes

**Fixed code:**

```java
public class Bug5 {
    // Return index of target in sorted array, or -1
    static int binarySearch(int[] a, int target) {
        int low = 0, high = a.length - 1;
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (a[mid] == target) return mid;
            else if (a[mid] < target) low = mid + 1;
            else high = mid - 1;
        }
        return -1;
    }
    public static void main(String[] args) {
        int[] a = {1, 3, 5, 7, 9};
        System.out.println(binarySearch(a, 9));
        System.out.println(binarySearch(a, 4));
    }
}
```

</details>

---

## 6. Palindrome check
**Level:** Medium · **Language:** C · **Expected:** Should print `1` then `0`.

```c
#include <stdio.h>
#include <string.h>

/* Return 1 if s is a palindrome, else 0 */
int isPalindrome(char s[]) {
    int n = strlen(s);
    for (int i = 0; i < n / 2; i++) {
        if (s[i] != s[n - i])
            return 0;
    }
    return 1;
}

int main() {
    printf("%d\n", isPalindrome("level"));
    printf("%d\n", isPalindrome("hello"));
    return 0;
}
```

<details>
<summary><b>Hint</b></summary>

There is **1** bug(s) to fix.

</details>

<details>
<summary><b>Answer</b></summary>

- **Off-by-one index:** the mirror of index `i` is `n - 1 - i`, not `n - i` (that reads the `'\0'` terminator first)

**Fixed code:**

```c
#include <stdio.h>
#include <string.h>

/* Return 1 if s is a palindrome, else 0 */
int isPalindrome(char s[]) {
    int n = strlen(s);
    for (int i = 0; i < n / 2; i++) {
        if (s[i] != s[n - 1 - i])
            return 0;
    }
    return 1;
}

int main() {
    printf("%d\n", isPalindrome("level"));
    printf("%d\n", isPalindrome("hello"));
    return 0;
}
```

</details>

---

## 7. First non-repeating character
**Level:** Medium · **Language:** Java · **Expected:** Should print `t` then `_`.

```java
import java.util.*;

public class Bug7 {
    // Return the first character that appears exactly once, or '_' if none
    static char firstUnique(String s) {
        Map<Character, Integer> freq = new HashMap<>();
        for (char c : s.toCharArray()) {
            freq.put(c, freq.get(c) + 1);
        }
        for (char c : freq.keySet()) {
            if (freq.get(c) == 1) return c;
        }
        return '_';
    }
    public static void main(String[] args) {
        System.out.println(firstUnique("stress"));
        System.out.println(firstUnique("aabb"));
    }
}
```

<details>
<summary><b>Hint</b></summary>

There are **2** bug(s) to fix.

</details>

<details>
<summary><b>Answer</b></summary>

- **NullPointerException:** `freq.get(c)` is `null` the first time a character is seen → `freq.getOrDefault(c, 0) + 1`
- **Logic bug:** `HashMap` has no order, so looping over `freq.keySet()` doesn't give the *first* unique character (prints `r` instead of `t`) → loop over `s.toCharArray()` again

**Fixed code:**

```java
import java.util.*;

public class Bug7 {
    // Return the first character that appears exactly once, or '_' if none
    static char firstUnique(String s) {
        Map<Character, Integer> freq = new HashMap<>();
        for (char c : s.toCharArray()) {
            freq.put(c, freq.getOrDefault(c, 0) + 1);
        }
        for (char c : s.toCharArray()) {
            if (freq.get(c) == 1) return c;
        }
        return '_';
    }
    public static void main(String[] args) {
        System.out.println(firstUnique("stress"));
        System.out.println(firstUnique("aabb"));
    }
}
```

</details>

---

## 8. Height of a binary tree
**Level:** Hard (Trees) · **Language:** Java · **Expected:** Should print `4`.

```java
public class Bug8 {
    static class Node {
        int val; Node left, right;
        Node(int v) { val = v; }
    }
    // Height = number of nodes on the longest root-to-leaf path
    static int height(Node root) {
        if (root == null) return 1;
        return 1 + Math.min(height(root.left), height(root.right));
    }
    public static void main(String[] args) {
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.left.right = new Node(5);
        System.out.println(height(root));   // expected 4
    }
}
```

<details>
<summary><b>Hint</b></summary>

There are **2** bug(s) to fix.

</details>

<details>
<summary><b>Answer</b></summary>

- **Wrong base case:** an empty tree has height `0`, not `1`
- **Wrong function:** height is the *longest* path → `Math.max`, not `Math.min`

**Fixed code:**

```java
public class Bug8 {
    static class Node {
        int val; Node left, right;
        Node(int v) { val = v; }
    }
    // Height = number of nodes on the longest root-to-leaf path
    static int height(Node root) {
        if (root == null) return 0;
        return 1 + Math.max(height(root.left), height(root.right));
    }
    public static void main(String[] args) {
        Node root = new Node(1);
        root.left = new Node(2);
        root.right = new Node(3);
        root.left.left = new Node(4);
        root.left.left.right = new Node(5);
        System.out.println(height(root));   // expected 4
    }
}
```

</details>

---

## 9. Unique paths in a grid
**Level:** Hard (2D DP) · **Language:** Java · **Expected:** Should print `28` then `1`.

```java
public class Bug9 {
    // Number of ways to go from top-left to bottom-right of an m x n grid,
    // moving only right or down
    static int uniquePaths(int m, int n) {
        int[][] dp = new int[m][n];
        dp[0][0] = 1;
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                dp[i][j] = dp[i - 1][j] + dp[i][j - 1];
            }
        }
        return dp[m][n];
    }
    public static void main(String[] args) {
        System.out.println(uniquePaths(3, 7));   // expected 28
        System.out.println(uniquePaths(1, 5));   // expected 1
    }
}
```

<details>
<summary><b>Hint</b></summary>

There are **2** bug(s) to fix.

</details>

<details>
<summary><b>Answer</b></summary>

- **Base cases missing:** the first row and first column each have exactly 1 path → set `dp[i][0] = 1` and `dp[0][j] = 1`
- **Out of bounds:** the answer is at `dp[m - 1][n - 1]`, not `dp[m][n]`

**Fixed code:**

```java
public class Bug9 {
    // Number of ways to go from top-left to bottom-right of an m x n grid,
    // moving only right or down
    static int uniquePaths(int m, int n) {
        int[][] dp = new int[m][n];
        for (int i = 0; i < m; i++) dp[i][0] = 1;
        for (int j = 0; j < n; j++) dp[0][j] = 1;
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                dp[i][j] = dp[i - 1][j] + dp[i][j - 1];
            }
        }
        return dp[m - 1][n - 1];
    }
    public static void main(String[] args) {
        System.out.println(uniquePaths(3, 7));   // expected 28
        System.out.println(uniquePaths(1, 5));   // expected 1
    }
}
```

</details>

---

## 10. Number of islands (DFS)
**Level:** Hard (Graphs) · **Language:** Java · **Expected:** Should print `3`.

```java
public class Bug10 {
    // Count islands: groups of '1's connected up/down/left/right
    static void dfs(char[][] g, int r, int c) {
        if (r < 0 || c < 0 || r > g.length || c > g[0].length || g[r][c] == '0')
            return;
        dfs(g, r + 1, c);
        dfs(g, r - 1, c);
        dfs(g, r, c + 1);
        dfs(g, r, c - 1);
    }
    static int countIslands(char[][] g) {
        int count = 0;
        for (int r = 0; r < g.length; r++)
            for (int c = 0; c < g[0].length; c++)
                if (g[r][c] == '1') {
                    dfs(g, r, c);
                    count++;
                }
        return count;
    }
    public static void main(String[] args) {
        char[][] grid = {
            {'1', '1', '0', '0', '0'},
            {'1', '1', '0', '0', '0'},
            {'0', '0', '1', '0', '0'},
            {'0', '0', '0', '1', '1'}
        };
        System.out.println(countIslands(grid));   // expected 3
    }
}
```

<details>
<summary><b>Hint</b></summary>

There are **2** bug(s) to fix.

</details>

<details>
<summary><b>Answer</b></summary>

- **Boundary check:** `r > g.length` lets `r == g.length` through → `r >= g.length` (same for `c`)
- **Missing visited mark:** cells are never marked, so DFS bounces between neighbours forever (`StackOverflowError`) → set `g[r][c] = '0'` before recursing

**Fixed code:**

```java
public class Bug10 {
    // Count islands: groups of '1's connected up/down/left/right
    static void dfs(char[][] g, int r, int c) {
        if (r < 0 || c < 0 || r >= g.length || c >= g[0].length || g[r][c] == '0')
            return;
        g[r][c] = '0';   // mark visited
        dfs(g, r + 1, c);
        dfs(g, r - 1, c);
        dfs(g, r, c + 1);
        dfs(g, r, c - 1);
    }
    static int countIslands(char[][] g) {
        int count = 0;
        for (int r = 0; r < g.length; r++)
            for (int c = 0; c < g[0].length; c++)
                if (g[r][c] == '1') {
                    dfs(g, r, c);
                    count++;
                }
        return count;
    }
    public static void main(String[] args) {
        char[][] grid = {
            {'1', '1', '0', '0', '0'},
            {'1', '1', '0', '0', '0'},
            {'0', '0', '1', '0', '0'},
            {'0', '0', '0', '1', '1'}
        };
        System.out.println(countIslands(grid));   // expected 3
    }
}
```

</details>

---

**Done all 10?** Make your own: take any problem you've solved, ask a friend or an AI to *"insert 2 subtle bugs without telling me where"*, and fix them against the clock.