# Will This Asteroid Panic Us? A Classification Story

*By Beakale Amenu Tefera*

---

## The Question

Thousands of asteroids pass by Earth every year.
Most go unnoticed. Some make headlines.

But what actually determines whether an approaching 
asteroid causes public panic — or gets ignored?

That question is what started this project.

---

## What I Built

A binary classification model that predicts whether 
an approaching asteroid would trigger **high panic** 
or **low panic**, using a publicly available NASA 
asteroid dataset from Kaggle.

Two models were trained and compared:

| Model | Accuracy |
|---|---|
| Logistic Regression | 77.8% |
| Random Forest | 97.7% |

---

## The Twist

The 97.7% felt too good.

So I investigated.

A correlation analysis revealed **structural target leakage** — 
the features used to train the model shared a common origin 
with the engineered target variable. `distance_au` was acting 
as a proxy for `risk_score`, which was used to build the labels 
in the first place.

The Random Forest had partially learned the formula 
behind the labels, not genuine patterns in the data.

**The honest number is 77.8%.**

This was a beginner's mistake — and catching it was 
the most important lesson of the project.

---

## What I Learned

- How to build an end-to-end classification pipeline
- The difference between accuracy and honest accuracy
- What target leakage looks like in practice
- That questioning your own results matters more 
  than celebrating them

---

## Dataset

NASA Asteroid Impact Dataset — Kaggle  
89,227 asteroid close approach records (2020–2100)

---

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook notebook/asteroid-panic-level-classification.ipynb
```

---

## Tech Stack

Python · pandas · scikit-learn · matplotlib · seaborn
