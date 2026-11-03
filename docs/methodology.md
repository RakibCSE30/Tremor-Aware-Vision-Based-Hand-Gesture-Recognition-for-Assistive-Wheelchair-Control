# Proposed Methodology

## 1. Input and acquisition

Use RGB video from a documented camera setup. Record camera model, resolution, nominal frame rate, camera-to-hand distance, lighting, viewpoint, dropped frames, and session conditions. Obtain ethics approval and informed consent before collecting human-subject data.

## 2. Hand tracking

Evaluate a documented hand-landmark tracker (for example, MediaPipe Hands). Store tracker version, configuration, handedness handling, confidence thresholds, missing-landmark policy, and failure rate. A tracker output is an estimate, not ground truth.

## 3. Preprocessing

- Preserve timestamps and original frame indices.
- Normalize coordinates relative to a stable hand reference (for example, wrist and palm scale) while retaining any absolute information justified by the task.
- Handle missing detections explicitly; do not silently interpolate long gaps.
- Construct fixed-duration sequences only after participant/session splits are defined.
- Prevent overlapping windows from crossing split boundaries.

## 4. Feature/model candidates

**Baseline:** interpretable geometric and temporal statistics with a conventional classifier.

**Temporal candidates:** LSTM and/or temporal convolutional network (TCN) operating on landmark sequences or derived features.

**Optional frequency analysis:** only when frame-rate stability and sequence duration support meaningful spectral estimates. State the sampling assumptions and avoid treating aliased estimates as tremor ground truth.

## 5. Labels

Define gesture onset/offset, intended command, non-command interval, ambiguous event, and annotation confidence. If tremor labels are unavailable, do not create them from model predictions. Distinguish participant-reported diagnosis/status from video-derived movement descriptors and obtain appropriate consent for any sensitive label.

## 6. Command gate

The classifier produces class probabilities. A separate gate may require a confidence threshold, temporal persistence, and a valid state transition before issuing a directional command. Low-confidence or contradictory outputs should map to No Command. Define Stop behavior and timeout behavior explicitly. Thresholds must be tuned on validation data only.

## 7. Evaluation

Use participant-wise and, where possible, session-wise splits. Report classification metrics, event-level false activations, false stops, missed commands, rejection rate, end-to-end latency, FPS, and dropped frames. Include confidence intervals when justified by the number of independent participants.

## 8. Reproducibility

Record random seeds, package versions, hardware, configuration files, preprocessing parameters, model checkpoints, and exact dataset versions/licenses. Keep test data isolated until the final evaluation.
