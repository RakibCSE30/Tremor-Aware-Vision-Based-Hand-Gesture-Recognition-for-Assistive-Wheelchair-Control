# Experimental Protocol

- Define primary outcomes before final test evaluation.
- Split by participant and/or session before window generation.
- Keep overlapping windows from one recording in one partition.
- Fit preprocessing and tune thresholds on training/validation only.
- Compare simple baselines, temporal models, and gated/ungated variants.
- Report macro-F1, per-class errors, false directional events, false stops, missed commands, rejection rate, latency, FPS, and dropped frames.
- Use an offline simulator only in the current research phase.
