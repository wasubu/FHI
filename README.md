# Fractional Hex Indexing (FHI)

## What is FHI?
Fractional Hex Indexing (FHI) is a system for assigning unique, flat, lexically sortable IDs to notes, cards, or objects. Its key feature: you can always insert a new item **between any two existing items** without renumbering anything else.

Unlike decimal-based or hierarchical IDs, FHI uses **hexadecimal fractions** to create infinitely flexible, insertion-friendly IDs.

---

## 🌟 Core Principles

### ✅ Fractional Hex IDs
- IDs are written as `n.x`, where:
  - `n` is the base number (1, 2, 3, …)
  - `.x` is a hexadecimal fractional part (base 16: `0` to `F`).
  - example: `1.8`, `30.C`, `4.18`

### ✅ Lexical Sortability
- IDs are purely alphanumeric and naturally sortable in filenames, text files, and databases.
- Sorting by filename = correct logical order.

### ✅ Midpoint Insertion (Core Mechanic)
- You can always calculate a **midpoint** between any two IDs in hexadecimal.
- No renumbering or restructuring needed.
- Example:
  - Between `1` and `2`: insert `1.8`
  - Between `1` and `1.8`: insert `1.4`
  - Between `1.8` and `2`: insert `1.C`
  - Between `1.7` and `1.8`: insert `1.78`

### ✅ Suffixes for Follow-ups
- You can add suffixes like `-1`, `-2`, `-z` if notes have a limited character space. base 36 is ideal (1 to 9, 0 and a to z)
- Example: `1.3-1`, `1.3-2`.

---

## 📊 Example Use Case: Zettelkasten
You’re writing notes in sequence but want the freedom to insert related ideas between existing notes without breaking the ID system.

- Original: `3`, `4`
- Insert between: `3.8`
- Insert another: `3.4`, `3.C`, etc.
- Never need to change `3` or `4`.

---

## 🟡 Why Not other methods?
- Harder to insert in dense sequences.
- IDs get longer quickly.
- Some IDs are "impossible" to create without renumbering or referencing.

---

## 🚀 Advantages of FHI
- Infinite insertions between any two IDs.
- Works beautifully with filenames & filesystem sorting.
- Simple mental model: **just find the hex midpoint**.
- Keeps IDs **flat yet expandable** — no tree depth explosion.
- IDs are stable — no renumbering ever.
- IDs tends to be shorter with dense sequences than other methods

---

## 🔥 Comparison Table

| Feature                    | FHI (Fractional Hex Indexing)                                     | Folgezettel with Base-36 IDs                                  |
|----------------------------|-------------------------------------------------------------------|---------------------------------------------------------------|
| **ID Format**               | `n.xxx`, where `.xxx` is a hex fraction (0-9, A-F per digit)      | Hierarchical numbers like `1`, `1a`, `1a1`, `1a1b`, etc.      |
| **Sorting Mechanism**       | Lexical sort by alphanumeric order (natural for filenames)        | Lexical sort works, but hierarchy gets messy at deep levels    |
| **Insertions Between IDs**  | Always possible by calculating hexadecimal midpoint              | Requires planning; inserting between `1a` and `1b` forces `1a1` |
| **Scalability**             | Infinite insertions, logarithmic growth with hex fractions        | Limited by depth of hierarchy, base-36 mitigates but still rigid |
| **Visual Complexity**       | Controlled growth (`1.A3F2`) stays compact longer                | Can explode in depth (`1a1b2c3d`)                              |
| **Mental Model**            | Binary tree, always midpoint between two IDs                     | Tree-like hierarchy, requires structure planning               |
| **Over-insertion Behavior** | Fractions get longer but sorted order is always correct          | IDs become nested and hard to manage in deep hierarchies       |
| **Practical in Filenames**  | Yes, perfect for file explorers & systems                        | Works, but deeply nested IDs become unwieldy                   |
| **Human Readability**       | Needs hex familiarity, but stays logical                         | Familiar at first, but deeply nested IDs become cryptic        |
| **Core Philosophy**         | Immutability of existing IDs, never forces renumbering            | IDs are mutable, renumbering happens as tree grows             |

---

## ⚠️ Known Trade-offs
While FHI is robust, consider:
- Over-inserting may lead to visually long IDs (`1.ABCDEF`), but they're still functional.
- Users must stay mindful to insert logically, not compulsively.
- Requires basic comfort with hexadecimal (0-9, A-F).

---

## 📊 Formulas for Nerds:

### 1. Number of Possible IDs Between Two Cards
For `d` hexadecimal fractional digits:
```
Total IDs = 16^d
```

---

### 2️. Total IDs Including Suffixes (-s)
```
Total IDs with suffixes = 16^d × 36
```

---

### 3️. Total IDs in a Range of N Cards
```
Total IDs in range = (N - 1) × 16^d × 36 + N
```

---

### 4️. Midpoint Calculation
```
midpoint = (a + b) / 2
```
Where `a` and `b` are hexadecimal fractional values.

---

### 5️. Relationship Between Digits and Resolution
```
Resolution per digit = 1 / 16^d
```

---

### 6️. Logarithmic Growth of ID Length
```
d = ⌈ log₁₆(n) ⌉
or
d = ⌈ log₂(n) / 4 ⌉
```

---

## 🔎 Why FHI is Different
> **FHI's core mechanic is built on the principle of immutability. IDs are permanent once assigned. Inserting a new note never forces you to change existing IDs.**

This is the opposite of systems where "renumbering" or "shuffling IDs" is necessary.

---

## 📂 Ideal For:
- Zettelkasten systems.
- File & folder ordering.
- Game object IDs.
- Any system where **order matters** but **renumbering is a headache**.

---

## License
MIT License — Free to use, modify, and share.

---

Edited by a large language model, Reviewed and developed by me.
