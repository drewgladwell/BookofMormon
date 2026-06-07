# Book of Mormon — Authorship & Linguistic Analysis

A data analytics project exploring the writing styles of different authors in the Book of Mormon using Python, NLP, and Tableau. This started as a personal project to combine my interest in data analytics with my faith, and ended up being one of the more interesting datasets I've worked with.

---

## Overview

The Book of Mormon has multiple authors — Nephi, Jacob, Mormon, Moroni, and others — each writing in their own voice and historical context. The goal of this project was to use data analytics to see if those differences are actually measurable. Spoiler: they are.

The analysis covers:
- **Word Frequency Analysis** — what words does each author reach for most?
- **Vocabulary Richness** — how diverse is each author's vocabulary?
- **TF-IDF Authorship Fingerprinting** — what words are uniquely signature to each author?
- **Verse Length Distribution** — do some authors write longer, more complex verses?
- **Word Clouds** — visual representation of each author's language, both thematically and stylistically

---

## Dashboard

> 📸 **[INSERT SCREENSHOT OF TABLEAU DASHBOARD HERE]**
> *(Recommended: export from Tableau as a PNG and drag into this section, or publish to Tableau Public and paste the link)*

---

## Key Findings

A few things that stood out:

- **Jacob's vocabulary is almost entirely shaped by the Zenos allegory** — words like `vineyard`, `branches`, `fruit`, and `tree` dominate his TF-IDF fingerprint in a way that no other author comes close to
- **Moroni's signature word is `jared`** — reflecting his abridgment of the book of Ether, which is unique to him among all authors
- **Mormon wrote nearly 100,000 words**, far more than any other author, which naturally lowers his vocabulary richness score — an important caveat worth noting
- **Enos and Jarom score highest on vocabulary richness**, but this is partly a function of their short length — a known limitation of richness scoring on small samples
- **"Lord" and "God" appear consistently across every author** — which is itself a meaningful finding for a religious text. These words were intentionally kept in the thematic word clouds but removed from the TF-IDF analysis to focus on stylistic differences

---

## Visualizations

### Word Frequency by Author
> 📸 **[INSERT outputs/word_frequency_by_author.png HERE]**

### Vocabulary Richness
> 📸 **[INSERT outputs/vocab_richness.png HERE]**

### Verse Length Distribution
> 📸 **[INSERT outputs/verse_length.png HERE]**

### Word Clouds — Authorship Fingerprints (Expanded Stopwords)
> 📸 **[INSERT word cloud fingerprint images HERE — e.g. outputs/wordcloud_jacob_fingerprint.png, outputs/wordcloud_nephi_fingerprint.png]**

### Word Clouds — Thematic (Minimal Stopwords)
> 📸 **[INSERT word cloud thematic images HERE — e.g. outputs/wordcloud_jacob_thematic.png, outputs/wordcloud_nephi_thematic.png]**

---

## A Note on Methodology

One decision worth explaining: for the TF-IDF analysis, I used an expanded stopword list that removed words like "Lord", "God", "people", and "land" — even though these are some of the most frequently used words in the entire book. The reason is that TF-IDF is designed to find what makes each author *distinct* from the others, and words that every author uses equally don't help with that comparison.

That said, the fact that every single author uses those words heavily is itself a meaningful finding — it speaks to the unified religious purpose of the text. So those words were preserved in the word cloud analysis where the goal is thematic rather than stylistic.

---

## Tech Stack

- **Python** — core analysis
- **Pandas** — data manipulation
- **NLTK** — stopwords and text processing
- **scikit-learn** — TF-IDF vectorization
- **Matplotlib** — visualizations
- **WordCloud** — word cloud generation
- **Tableau** — interactive dashboard

---

## Data

The dataset (`data/book_of_mormon.csv`) contains 6,585 verses with the following columns:

| Column | Description |
|---|---|
| `Book_Order` | Numeric order of the book (1–14) |
| `Book` | Book name (e.g. "1 Nephi") |
| `Chapter` | Chapter number |
| `Verse` | Verse number |
| `Author` | Primary author assigned to that book |
| `Word_Count` | Number of words in the verse |
| `Text` | Full verse text |

Author attribution follows traditional and scholarly consensus — Mormon is credited as the abridger of Mosiah, Alma, Helaman, 3 Nephi, and 4 Nephi; Moroni abridged Ether and wrote the closing book.

---

## How to Run

1. Clone the repo
2. Install dependencies:
```bash
pip install pandas nltk scikit-learn matplotlib wordcloud
```
3. Open `01_exploration.ipynb` in VS Code or Jupyter
4. Run all cells in order

---

## About

Built by Drew Gladwell as a portfolio project while preparing to apply to the BYU Information Systems program. Feedback welcome.
