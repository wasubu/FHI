# Fractional Hex Indexing (FHI)

## What is FHI?
Fractional Hex Indexing (FHI) is a system for assigning unique, lexically sortable IDs to notes, cards, or objects. Its key feature: you can always insert a new item **between any two existing items** without renumbering anything else.

Unlike decimal-based or hierarchical IDs, FHI uses **hexadecimal fractions** to create infinitely flexible, insertion-friendly IDs.

---

## 🌟 Core Principles

### ✅ Fractional Hex IDs
- IDs are written as `n.xxx`, where:
  - `n` is the base number (1, 2, 3, …)
  - `.xxx` is a hexadecimal fractional part (`0` to `F` per digit).

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

### ✅ Suffixes for Follow-ups
- You can add suffixes like `-1`, `-2`, `-z` for extensions.
- Example: `1.A3-1`, `1.A3-2`.

---

## 📊 Example Use Case: Zettelkasten
You’re writing notes in sequence but want the freedom to insert related ideas between existing notes without breaking the ID system.

- Original: `3`, `4`
- Insert between: `3.8`
- Insert another: `3.4`, `3.C`, etc.
- Never need to change `3` or `4`.

---

## 🆚 Comparison to Other Systems

| Feature               | FHI (Fractional Hex Indexing)         | Decimal IDs / Folgezettel              |
|-----------------------|---------------------------------------|----------------------------------------|
| Sortable in filenames  | ✅ Yes                               | ❌ Manual adjustments often needed     |
| Insertions between IDs | ✅ Always possible by midpoint        | ❌ Limited, requires renumbering        |
| Renumbering required   | ❌ Never                             | ✅ Often when adding between items      |
| Complexity growth      | ✅ Logarithmic (hex-based)            | ❌ Exponential in decimal / hierarchy   |

---

## 🟡 Why Not Decimal Fractions?
Decimal fractions like `1.1`, `1.11`, `1.111` hit practical limits:
- Harder to insert in dense sequences.
- IDs get longer quickly.
- Many decimal values are "impossible" to create without renumbering.
- Hexadecimal provides more granularity per digit.

---

## 🚀 Advantages of FHI
- Infinite insertions between any two IDs.
- Works beautifully with filenames & filesystem sorting.
- Simple mental model: **just find the hex midpoint**.
- Avoids rigid tree structures and hierarchy traps.
- IDs are stable — no renumbering ever.

---

## ⚠️ Known Trade-offs
While FHI is robust, consider:
- Over-inserting may lead to visually long IDs (`1.ABCDEF`), but they're still functional.
- Users must stay mindful to insert logically, not compulsively.
- Requires basic comfort with hexadecimal (0-9, A-F).

---

## 📝 FHI Formula (For Nerds)
Cards between `n` and `n+1` using 3-digit hex fraction + suffixes:
- `4096` positions per gap (`.000` to `.FFF`).
- Suffixes allow `-0` to `-z` (36 per position).
- Total: `4096 x 36 = 147,456` unique IDs per gap.

Between IDs `1` and `2`:  
→ 147,456 unique cards possible.

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

## End.
