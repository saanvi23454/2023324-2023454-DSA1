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

## Notebook layout
| Section | Content |
|---|---|
| Data | Builds D (one-hot encoding, drop constant columns, min–max scaling); prints n and d |
| Q1 (a) | k-means on D: cost(D,B) and time |
| Q1 (b)–(d) | Gaussian projection E = DAᵀ for m ∈ {5,…,25}, 5 runs each: B̂ and B⁺ ratios, times, plots |
| Q1 (e) | Pairwise distance ratios and cost_E(C_D)/cost_D(C_D), shown as box plots |
| Q2 (a) | Full least squares: Loss(D,y,b) and time |
| Q2 (b)–(c) | CountSketch for m ∈ {50,…,5000}, 5 runs each: loss, ratio, sketched loss, times, log–log plot |
| Q2 (d) | ‖Sv‖²/‖v‖² histograms over 100 sketches |
| Q2 (e) | CountSketch vs dense Gaussian sketch on a fixed 50,000-row subset |
