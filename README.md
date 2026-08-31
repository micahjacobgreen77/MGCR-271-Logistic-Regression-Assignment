# MGCR-271 — Logistic Regression Assignment

This repository contains the materials for the MGCR-271 logistic regression assignment: exploratory analysis, model training, evaluation, and a short write-up of results.

Contents

- README.md — this file
- data/ — (optional) dataset files used in the assignment
- notebooks/ — Jupyter notebooks with the analysis and modeling workflow
- src/ — (optional) scripts to train, evaluate, or preprocess data
- results/ — (optional) output such as model artifacts, saved figures, and metrics

Requirements

- Python 3.8+
- Install dependencies (if a requirements.txt file is provided):

  python -m venv .venv
  source .venv/bin/activate  # macOS / Linux
  .venv\Scripts\activate     # Windows (PowerShell)
  pip install -r requirements.txt

Usage

1. Clone the repository

   git clone https://github.com/micahjacobgreen77/MGCR-271-Logistic-Regression-Assignment.git
   cd MGCR-271-Logistic-Regression-Assignment

2. Run the analysis

- If the project includes a Jupyter notebook, open it and run the cells to reproduce the analysis:

  jupyter notebook

- If the project includes scripts under `src/`, you can run them directly. Common examples:

  python src/preprocess.py --input data/raw.csv --output data/processed.csv
  python src/train.py --data data/processed.csv --out results/model.pkl
  python src/evaluate.py --model results/model.pkl --test data/test.csv

If those exact scripts or paths don't exist in this repository, open the notebooks or inspect the `src/` directory to find the entry points used in this assignment.

What this assignment demonstrates

- Data cleaning and feature preparation for binary classification
- Training and regularizing logistic regression models
- Model evaluation using accuracy, precision/recall, ROC AUC, and confusion matrices
- Interpreting model coefficients and feature importance

Results

The repository contains (or will contain) artifacts and outputs that summarize the performance of the trained logistic regression models. Look in `results/` for saved figures, metrics, and model files.

Contributing

This repository is a coursework assignment. If you want to suggest improvements or corrections, open an issue or submit a pull request.

License

Specify a license here (e.g., MIT) or remove this section if not applicable.

Contact

micahjacobgreen77 — GitHub: https://github.com/micahjacobgreen77

---

Notes

If you'd like, I can:
- Customize the README with exact file names and commands after I list the repository files, or
- Add a requirements.txt, a short usage script, or a one-page summary of the assignment results.
