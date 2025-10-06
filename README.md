# 🛡️ Knights and Knaves AI Solver

This project implements a solver for **Knights and Knaves** logic puzzles, inspired by Raymond Smullyan’s classic puzzles.  
Using **propositional logic** and **model checking**, the program determines whether each character in a puzzle is a **knight** (always tells the truth) or a **knave** (always lies).

---

## 📖 Overview

In a Knights and Knaves puzzle:

- Each character is either a knight or a knave.  
- Knights always tell the truth; knaves always lie.  
- Characters make statements, and the objective is to deduce each character's type.  

The program uses **propositional logic** to represent each character’s statements and a **model-checking algorithm** to deduce their identity.

### Example

**Puzzle 0:**  
A says: “I am both a knight and a knave.”

- If A were a knight, the statement would be true — impossible.  
- Therefore, A must be a knave.

---

## ⚙️ How It Works

1. **Propositional Symbols**: Each character has two symbols:  
   - `AKnight`, `AKnave` (for character A)  
   - `BKnight`, `BKnave` (for character B)  
   - `CKnight`, `CKnave` (for character C)  

2. **Knowledge Bases**: Each puzzle has a knowledge base (`knowledge0`, `knowledge1`, `knowledge2`, `knowledge3`) containing logical sentences about the puzzle.

3. **Logical Connectives**: Statements are represented using classes like `And`, `Or`, `Not`, and `Implication` from `logic.py`.  

4. **Model Checking**: The `model_check` function evaluates which statements are entailed by the knowledge base, deducing which characters are knights or knaves.

5. **Puzzle Solver**: `puzzle.py` loops over all puzzles and prints the conclusions inferred from the knowledge base using model checking.

---

## 🧩 File Structure

```text
knights-and-knaves/
│
├── logic.py            # Propositional logic classes and model checking
├── puzzle.py           # Puzzle definitions and knowledge bases
├── LICENSE             # MIT License
└── README.md           # Documentation (this file)
```
### 🧠 Puzzle Examples
**Puzzle 0**
- Character A says: “I am both a knight and a knave.”
- AI deduces: A is a knave.

**Puzzle 1**
- Characters: A, B
- A says: “We are both knaves.”
- B says nothing.
- AI deduces: A is a knave, B is a knight.

**Puzzle 2**
- Characters: A, B
- A says: “We are the same kind.”
- B says: “We are of different kinds.”
- AI deduces: A is a knave, B is a knight.

**Puzzle 3**
- Characters: A, B, C
- A says either “I am a knight.” or “I am a knave.” (unknown which)
- B says: “A said ‘I am a knave.’” and “C is a knave.”
- C says: “A is a knight.”
- AI deduces: A is a knight, B is a knight, C is a knave.

### ▶️ Usage

1. Clone the repository:
```python
git clone https://github.com/yourusername/knights-and-knaves.git
cd knights-and-knaves
```
2. Install dependencies:
```python
pip install -r requirements.txt
```
3. Run the puzzle solver:
```python
python puzzle.py
```
### 🧩 Dependencies / Requirements
- Python 3.8 or higher
- No external libraries are required (uses only built-in Python modules)

### 🏁 Credits

Inspired by Raymond Smullyan’s Knights and Knaves puzzles and CS50 AI course logic exercises.

### 📄 License

```text
MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM,
DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```
