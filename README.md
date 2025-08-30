# Spelling-Savvy-Spell-Checker-Project
This project implements a **Spell Checker** using Python, inspired by [Peter Norvig's algorithm](https://norvig.com/spell-correct.html).   
It uses a probability-based approach on a large text corpus (`big.txt`) to suggest the most likely corrections for misspelled words.

---

## 🚀 Features
- **Vocabulary Extraction**: Extracts all unique words from a text corpus (`big.txt`).
- **Word Probability Distribution**: Computes the probability of each word based on frequency.
- **Edit Operations**:
  - **Delete** → `"loave"` → `"love"`
  - **Swap** → `"lvoe"` → `"love"`
  - **Replace** → `"lave"` → `"love"`
  - **Insert** → `"lve"` → `"love"`
- **Spell Checking**:
  - **Level 1 (Edit Distance = 1)** → Suggestions from words one edit away.
  - **Level 2 (Edit Distance = 2)** → Suggestions from words two edits away.
- **Persistent Storage**: Saves and loads probability distributions via JSON.

---

## 📂 Project Structure
```bash
Spelling-Savvy/
│── big.txt                 # Training corpus
│── word_probability.json   # Stored word probabilities
│── Spelling Savvy.ipynb    # Main implementation
│── README.md               # Project documentation
```

---

## ⚙️ How It Works
1. **Build Vocabulary**  
  - Extract words from `big.txt`, clean them, and create a vocabulary set.

2. **Compute Probabilities**
  - P(word) = Count(word) / Total_words
  - This helps rank candidate corrections.

3. **Generate Edits**  
  - Possible variations of a word are generated using:
    - Insertions
    - Deletions
    - Replacements
    - Transpositions

4. **Find Predictions**  
  - **Level 1**: Suggests corrections from edits one step away.
  - **Level 2**: Suggests corrections from edits two steps away.

---

## 🖥️ Example Usage
```python
# Level 1 Prediction
spell_check("tha")
# Output: ['the', 'that', 'than', 'tea', 'ha']

# Level 2 Prediction
spell_check_edit_2("fameli")
# Output: ['family', 'namely', 'fame', 'camelia', 'amelie']
```

---

## 📊 Sample Results
| Input Word | Suggested Corrections                |
|------------|---------------------------------------|
| tha        | the, that, than, tea, ha              |
| fameli     | family, namely, fame, camelia, amelie |
| lvoe       | love, live, lore, lose, lave          |

---

## 🛠️ Requirements

- Python 3.x
- pandas
- tqdm
- regex (re)
- json

Install dependencies:
```bash
pip install pandas tqdm
```
---

## 📌 References

- Peter Norvig’s Spell Checker
- NLP basics for text cleaning and preprocessing

---

## ✨ Future Improvements

- Add custom corpus training support.
- Optimize with frequency dictionaries instead of .count() (improves speed).
- Support for multi-language spell checking.
- Deploy as a Flask/FastAPI web app or CLI tool.

---

## 👨‍💻 Author

Rishita Priyadarshini Saraf

📧 rishitasarafp@gmail.com
