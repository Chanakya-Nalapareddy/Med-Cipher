# Med-Cipher


# 🔐 Adversarial Privacy Protection in Clinical Text

This project implements a privacy-preserving pipeline for clinical notes using **adversarial perturbations**. It identifies sensitive entities (e.g., names, dates), perturbs them realistically, and evaluates both **privacy leakage** and **utility retention** using re-identification risk and downstream classification tasks.

---

## 🧠 Key Features

- **Sensitive Entity Detection**: Uses rule-based and regex methods to extract names and dates.
- **Adversarial Perturbation**: Injects noise while preserving naturalness using substitution.
- **Utility Evaluation**: Measures similarity (BLEU, cosine) and downstream classification performance before and after perturbation.
- **Privacy Risk Evaluation**: Assesses how many sensitive entities are still recoverable post-perturbation.

---

## 🗃️ Dataset

- Input: A subset of the [MIMIC-III](https://physionet.org/content/mimiciii/1.4/) dataset.
- The CSV should include at least:
  - `TEXT`: The clinical note
  - `CATEGORY`: Note category (e.g., "Discharge summary")

Make sure your file is named:
```
NOTEEVENTS_random.csv
```

## 🧪 How to Run the Project

```bash
python project.py
```

This script will:
- Preprocess clinical notes
- Detect and perturb sensitive information
- Train a binary classifier (discharged vs in-hospital)
- Evaluate privacy (re-identification risk) and utility (BLEU, cosine, accuracy)

---

## 📊 Evaluation Metrics

- **BLEU Score**: Measures how close the perturbed text is to the original.
- **Cosine Similarity**: Compares vector similarity of texts.
- **Classifier Accuracy**: Assesses if the perturbation harms prediction (e.g., discharge classification).
- **Correct Re-identifications Before/After**: Measures privacy impact.

---

## 📈 Sample Output

```
Classifier training accuracy: 0.9731
Average BLEU score: 0.71
Average Cosine similarity: 0.86
Average correct identifications before perturbation: 2.7
Average correct identifications after perturbation: 0.8
Average downstream accuracy (original): 0.88
Average downstream accuracy (perturbed): 0.85
```

---

## 🚀 Future Work

- Use neural NER for better entity detection.
- Train adversarial models instead of rule-based perturbation.
- Expand to multimodal data (e.g., EHR + images).
- Improve downstream tasks to include more labels and regression outputs.

---

## 📚 Dependencies

- `transformers`
- `scikit-learn`
- `nltk`
- `pandas`
- `torch`

Install them using:

```bash
pip install -r requirements.txt
```

---

## 👨‍⚕️ Authors

- Chanakya Nalapareddy, Rishit Epari, Areef Syed — Drexel University (2025)

---

## 📝 License

This project is for academic use only.
