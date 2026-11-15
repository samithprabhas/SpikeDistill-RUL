# SpikeDistill-RUL

Project Statement 1 implementation for NASA C-MAPSS FD001–FD004. The main deliverables are:

- `SpikeDistill_RUL.ipynb` — preprocessing, model training, evaluation, ablations, explainability, and edge profiling hooks.
- `output/pdf/SpikeDistill_RUL_Report.pdf` — methodology, research context, evaluation plan, and reporting template.
- `output/pptx/SpikeDistill_RUL_Presentation_Final_v2.pptx` — 10-slide project presentation.

## Run the notebook

1. Install the packages in `requirements.txt` in a PyTorch-compatible Python environment, or use Google Colab.
2. Extract the supplied C-MAPSS archive and set `DATA_DIR` in the notebook to its folder. The notebook checks `/content/archive`, `archive`, and the supplied local archive path by default.
3. Run all cells from top to bottom with `QUICK_RUN = False`. The default run covers FD001–FD004 and seeds 17, 42, and 2026. It can take substantial compute time.
4. Retain `results_by_seed.csv` and `results_summary.csv`. Replace pending report/slide metrics only with these measured results.
5. Run the Jetson profiling cell on the physical Jetson Orin Nano. Record power mode, precision, average power, and board logs; desktop measurements do not substitute for Jetson results.

The notebook uses an engine-level training/validation split and the official test split and RUL labels. It implements conventional RNN/LSTM/GRU/BiLSTM/CNN-LSTM and DeepNN/WideNN baselines, output-only KD, ANN-to-SNN rate conversion, a surrogate-gradient LIF baseline, and the proposed hidden-state-aware LIF student.

## Current result status

The notebook source is prepared, but its training cells have not been executed here because the available local runtime lacks PyTorch. Predictive metrics and Jetson measurements are therefore marked pending in the report and slides. The candidate novelty claim is also explicitly provisional pending a systematic literature review.
