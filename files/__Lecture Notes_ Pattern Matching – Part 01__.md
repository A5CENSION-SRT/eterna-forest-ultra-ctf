<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" class="logo" width="120"/>

### **Lecture Notes: Pattern Matching – Part 01**

**1. 📝 High-Level Summary**
This lecture introduces the fundamentals of **pattern matching** in Linux using `grep` and `egrep`. It covers the syntax of regular expressions, essential metacharacters, and demonstrates practical examples of searching text files for specific patterns[^1].

**2. 🔑 Key Concepts Introduced**

- Definition of *regular expressions* and their role in text processing.
- Literal versus *meta–characters* (e.g., `.`, `^`, `$`, `\`, `[]`).
- *Anchors* to match beginning (`^`) and end (`$`) of a line.
- *Quantifiers* (`*`, `+`, `{m,n}`) for specifying repetition.
- *Character classes* (`[a–z]`, `[^0–9]`, `[1-5]`).
- Escaping meta–characters with backslashes (`\.` to match literal dot).
- Difference between *basic* (`grep`) and *extended* (`egrep` or `grep -E`) regular expressions.

**3. 💻 Commands Covered this Week**

* `grep`
    * **Purpose:** Search files for lines matching a basic regular expression.
    * **Syntax:** `grep [options] pattern [file...]`
    * **Common Options/Flags:**
        * `-i`: Case-insensitive search.
        * `-v`: Invert match (show non-matching lines).
        * `-n`: Show line numbers.
    * **Practical Example(s) from Video:**

```bash
cat file | grep 'pattern'
```

> **Explanation:** Pipes `file` content into `grep`, printing lines containing "pattern"[^1].
* `egrep` (or `grep -E`)
    * **Purpose:** Search using extended regular expressions.
    * **Syntax:** `egrep [options] pattern [file...]`
    * **Common Options/Flags:**
        * `-c`: Count matching lines.
        * `-o`: Only show matching part of line.
    * **Practical Example(s) from Video:**

```bash
cat file | egrep '(ma)\+'
```

> **Explanation:** Matches one or more occurrences of "ma"[^1].

**4. ✨ Best Practices \& Pro-Tips**

- Always **quote** patterns to prevent shell interpretation of meta–characters[^1].
- Use `\b` for **word boundaries** when matching whole words.
- Combine `^` and `$` anchors to match **exact lines**.
- Employ character classes (`[ ]`) to match a **range** or **set** of characters.
- Use `egrep` (or `grep -E`) for more **concise** expressions when leveraging `+`, `?`, or `|`.

**5. ⚠️ Common Pitfalls / "Gotchas"**

- Forgetting to **escape** meta–characters (e.g., `.` matches any character unless escaped as `\.`)[^1].
- Misusing quantifiers: `*` allows zero occurrences, while `+` requires at least one.
- Neglecting quotes, causing the shell to expand brackets or braces.
- Mixing up `grep` and `egrep`: some patterns (like `+`, `|`) require `egrep`.

**6. 🤔 Review Questions**

1. How do you match lines that end with the word “pattern”?
2. What is the difference between using `.*` and `[a-z]*` in a regex?
3. When should you use `egrep` instead of `grep`?

<div style="text-align: center">⁂</div>

[^1]: https://www.youtube.com/watch?v=1y85iTaqq8Y

