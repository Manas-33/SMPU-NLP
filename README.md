# Rule-Based Math Word Problem Solver

A natural language processing (NLP) application that automatically solves elementary math word problems. The system classifies the problem type and predicts the arithmetic operation required, then computes the answer.

## Overview

The solver uses a rule-based NLP pipeline to:
1. Parse and preprocess the input question using [spaCy](https://spacy.io/)
2. Resolve coreferences using [neuralcoref](https://github.com/huggingface/neuralcoref)
3. Classify the problem into one of four categories: **compare**, **combine**, **change**, or **div_mul**
4. Predict the arithmetic operation: **addition**, **subtraction**, **multiplication**, or **division**
5. Extract the relevant numbers and return the answer

## Features

- Handles a wide range of elementary math word problem types
- Coreference resolution to correctly interpret pronouns (e.g., "he", "she", "they")
- Simple web-based UI built with Bootstrap 5
- Desktop app experience powered by [Python Eel](https://github.com/python-eel/Eel)

## Problem Categories

| Category  | Description                                            | Example                                                  |
|-----------|--------------------------------------------------------|----------------------------------------------------------|
| `compare` | Compares two quantities using comparative adjectives   | "Anne weighs 67 pounds. How much heavier is she than Bob?" |
| `combine` | Asks for the total of multiple quantities              | "John has 5 apples and 3 oranges. How many does he have altogether?" |
| `change`  | Involves a quantity that increases or decreases        | "Sara had 10 cookies. She ate 4. How many are left?"     |
| `div_mul` | Involves rates, groups, or equal distribution          | "Betty has 24 oranges in 3 boxes. How many per box?"     |

## Tech Stack

- **Python** — core solver logic
- **spaCy** — tokenization, POS tagging, lemmatization, named entity recognition
- **neuralcoref** — coreference resolution
- **Eel** — serves the web UI as a desktop application
- **HTML / CSS / JavaScript** — frontend interface
- **Bootstrap 5** — UI styling

## Project Structure

```
SMPU-NLP/
├── app.py                                  # Eel application entry point
├── data.json                               # Math word problem dataset
├── Rule_based_Math_Word_Problem_Solver.ipynb  # Core NLP solver notebook
└── web/
    ├── index.html                          # Main UI page
    ├── app.js                              # Frontend JS (Eel bridge)
    └── style.css                           # Custom styles
```

## Getting Started

### Prerequisites

- Python 3.7+
- pip

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Manas-33/SMPU-NLP.git
   cd SMPU-NLP
   ```

2. Install the required Python packages:
   ```bash
   pip install eel spacy
   python -m spacy download en_core_web_sm
   pip install https://github.com/huggingface/neuralcoref/archive/master.zip
   ```

### Running the App

```bash
python app.py
```

This will open the web interface in your default browser. Type a math word problem into the input field and click **Solve** to get the answer.

### Running the Notebook

Open `Rule_based_Math_Word_Problem_Solver.ipynb` in Jupyter to explore and experiment with the solver logic directly:

```bash
jupyter notebook Rule_based_Math_Word_Problem_Solver.ipynb
```

## Example Questions

- *"John has 15 marbles. He gives 7 to his friend. How many does he have left?"*
- *"A train travels 60 miles per hour. How far does it go in 3 hours?"*
- *"Sara has 24 stickers to share equally among 6 friends. How many does each friend get?"*
- *"Tom has 8 more apples than Jerry. Jerry has 5 apples. How many does Tom have?"*
