# Experimental Protocol

## Before training

1. Freeze the research question, primary outcome, and inclusion criteria.
2. Audit dataset source, license, modality, labels, participants, sessions, frame rate, and missingness.
3. Define annotation rules and inter-annotator agreement procedure if manual labels are used.
4. Assign participant/session splits before creating windows.
5. Define baseline, model search space, compute budget, and random seeds.

## Data splitting

- Prefer train/validation/test partitions by participant.
- If participant count is too small, use grouped cross-validation and state the limitation.
- Never distribute overlapping windows from the same source recording across partitions.
- Fit normalization, feature selection, and thresholds using training/validation data only.

## Baselines and ablations

- Majority-class and simple rule baseline.
- Geometric/temporal features + conventional classifier.
- Landmark sequence + temporal model.
- Model without confidence gate versus model with gate.
- Ablations for sequence length, missing-frame handling, and selected feature groups.

## Metrics

Classification: accuracy, macro-F1, per-class precision/recall, confusion matrix.

Command events: false directional activations per minute/session, missed intended commands, false Stop events, command delay, No Command rejection rate.

Runtime: end-to-end latency, throughput/FPS, dropped-frame rate, hardware/software environment.

## Statistical reporting

Report participant-level distributions, not only pooled windows. Include confidence intervals and paired comparisons where sample size and design permit. Avoid claims of statistical significance without an appropriate test and assumptions check.

## Safety evaluation

Use only an offline simulator in this research phase. Define scenarios for ambiguous motion, tracking loss, low confidence, conflicting classes, delayed frames, and stale commands. A high accuracy score is not evidence of physical safety.
