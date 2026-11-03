# Research Proposal

## Working title

**Tremor-Aware Vision-Based Hand Gesture Recognition for Assistive Wheelchair Control**

## Summary

This research investigates whether temporal RGB-camera hand-motion representations and uncertainty-aware command generation can improve the reliability of hand-gesture interfaces intended for assistive wheelchair control when involuntary tremor-like movement is present.

## Background

Vision-based hand gesture interfaces can avoid requiring the user to wear dedicated motion sensors. Yet a single-frame pose classifier may not capture the temporal structure of an intentional gesture, and movement variability can produce ambiguous observations. A wheelchair interface must distinguish an intended command from uncertain motion and should prefer withholding a directional command over issuing an unsupported one.

## Aim

Design and evaluate a camera-only research pipeline for temporal hand-gesture interpretation and conservative command generation.

## Objectives

1. Review vision-based wheelchair control, hand tracking, tremor analysis, and safety-oriented human-computer interaction.
2. Audit available datasets and determine which contain compatible RGB video, gesture labels, tremor-related information, and participant metadata.
3. Define an ethically appropriate data collection and annotation protocol if existing data are insufficient.
4. Establish interpretable baselines before evaluating temporal models.
5. Evaluate a confidence-aware command gate using both recognition and safety-oriented metrics.
6. Report limitations, generalization risks, and requirements for any future supervised physical testing.

## Proposed method

RGB frames are quality-checked, hand landmarks are extracted, and sequences are normalized into temporal samples. Candidate spatial and motion features are compared with learned temporal representations. Models are evaluated against a participant-wise protocol. A separate command gate maps predictions to Forward, Backward, Left, Right, Stop, or No Command. The gate must be evaluated independently; it must not be assumed safe merely because classifier accuracy is high.

## Expected research outputs

- A documented dataset audit and annotation protocol.
- Reproducible camera-based preprocessing and baseline experiments.
- A comparison of temporal recognition approaches.
- A safety-oriented evaluation protocol and error analysis.
- A clear account of what the available data can and cannot establish.

These are planned outputs, not completed contributions.

## Scope boundaries

The proposed deployed pipeline is RGB-camera-only. Sensor datasets may inform background literature or a separately reported exploratory analysis, but sensor measurements are not camera input and cannot establish camera-only performance. Clinical diagnosis and unsupervised real-wheelchair operation are outside scope.

## Risks and mitigation

| Risk | Mitigation |
|---|---|
| No synchronized intended-command and tremor annotations | Design annotation protocol; mark labels unavailable rather than infer them |
| Dataset mismatch | Maintain a modality/label audit for every dataset |
| Participant leakage | Participant/session-wise split |
| False directional activations | Report event-level false activations and test conservative rejection |
| Overclaiming | Publish protocol, limitations, and negative results |
| Privacy risks | Consent, data minimization, access controls, no raw identifiable uploads |
