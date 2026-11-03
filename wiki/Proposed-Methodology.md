# Proposed Methodology

1. Acquire timestamped RGB frames under a documented protocol.
2. Estimate hand landmarks and track detection quality.
3. Normalize coordinates and construct temporal sequences.
4. Compare interpretable geometric/temporal baselines with LSTM or TCN candidates.
5. Predict Forward, Backward, Left, Right, Stop, or No Command.
6. Apply a separately evaluated confidence/persistence gate.
7. Evaluate offline using participant-wise splits and safety-oriented metrics.

The pipeline is proposed and must be updated as implementation and data decisions are finalized.
