# DSA1

Group: 2023324 Mohammad Umar, 2023454 Saanvi Singh

## Files
- `Code.ipynb` – all code for Q1 (JL for k-means) and Q2 (JL / CountSketch for least squares)
- `Report.pdf` – answers, tables and plots

## Requirements
Python 3.9+ with:
```
pip install numpy pandas matplotlib scikit-learn jupyter
```

## Running
```
jupyter notebook Code.ipynb
```
Then **Kernel → Restart & Run All**. Cells must run top to bottom, in order: every random draw comes from one shared generator, so the order fixes the results.

- The first run downloads the KDD Cup 99 10% dataset through `sklearn.datasets.fetch_kddcup99` and caches it in `~/scikit_learn_data`. An internet connection is needed only that first time.
- Expected runtime: about 5–10 minutes. Most of it is the k-means runs in Q1.
- Memory: about 3–4 GB of RAM. D is 494,021 × 116.

## Reproducibility
- All randomness is seeded: `SEED = 42` for the numpy generator and for the KMeans `random_state`. The Q2(e) subset uses its own generator seeded with `SEED`.
- Every cost, loss and ratio in the report reproduces exactly when all cells are run in order.
- Wall-clock times depend on the machine and will differ, but their relative comparisons hold.
