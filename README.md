# Tremor-Aware Vision-Based Hand Gesture Recognition for Assistive Wheelchair Control

[![Research status](https://img.shields.io/badge/status-research%20in%20progress-orange)](#research-status)
[![Modality](https://img.shields.io/badge/input-RGB%20camera-blue)](#scope-and-design-principles)
[![Documentation](https://img.shields.io/badge/docs-available-brightgreen)](docs/)

> A research project investigating camera-based hand-gesture interpretation for assistive wheelchair command generation in the presence of Parkinsonian tremor.

## Abstract

Hand gestures can provide a natural, non-contact interface for assistive wheelchair control. However, involuntary hand motion associated with tremor may make gesture interpretation unreliable. This repository documents a research direction using RGB video, hand-landmark tracking, spatiotemporal motion features, temporal recognition models, and a safety-oriented command gate.

The proposed research direction uses RGB video, hand-landmark tracking, spatiotemporal motion features, temporal recognition models, and a safety-oriented command gate. The project is at the research design and documentation stage rather than a validated deployed system.

## Problem and motivation

A recognizer that classifies a hand pose in a single frame may confuse intended gestures with transient or involuntary motion. For wheelchair interaction, a false directional command can be more critical than a missed command. This project therefore focuses on temporal interpretation and conservative command generation.

## Scope and design principles

- **Input modality:** RGB camera video only for the proposed deployed pipeline.
- **Hand representation:** candidate 2D/3D hand landmarks (for example, MediaPipe Hands); tracker choice will be documented with version and configuration.
- **Temporal reasoning:** compare interpretable feature-based baselines with temporal models such as LSTM or TCN.
- **Command interface:** Forward, Backward, Left, Right, Stop, and No Command.
- **Safety:** confidence thresholding, temporal confirmation, command timeout, and explicit rejection of uncertain predictions are research design candidates, not yet validated safety guarantees.
- **Evaluation:** participant-independent testing where feasible, latency, false activations, and error analysis in addition to conventional classification metrics.

The use of camera-only input is a design constraint. Wearable IMU/EMG signals are not inputs to the proposed deployed system. Published or public sensor datasets may be useful only for clearly separate exploratory analyses.

## Research questions

1. How does hand-landmark and temporal-feature quality change in the presence of tremor-like motion?
2. Which temporal representation/model best distinguishes intended gesture sequences from uncertain or non-command motion under the available labels?
3. Can a confidence-aware temporal gate reduce unintended directional command activations without making the interface unusably slow?
4. How do performance and latency vary across participants, recording conditions, and gesture classes?

## Proposed pipeline

```text
RGB video
   ↓
Frame quality checks and hand tracking
   ↓
Landmark normalization and temporal sequence construction
   ↓
Spatial + temporal (+ carefully justified frequency) features
   ↓
Baseline and temporal gesture models
   ↓
Confidence / persistence / timeout gate
   ↓
Forward | Backward | Left | Right | Stop | No Command
   ↓
Offline simulator and safety-oriented evaluation
```

This is a proposed workflow. Components will be revised as the dataset, protocol, and experiments are established. Frequency-domain analysis must account for camera frame rate, dropped frames, sequence length, and missing data.

## Research documentation

- [Research proposal](docs/research-proposal.md)
- [Problem statement and objectives](docs/problem-and-objectives.md)
- [Research gaps](docs/research-gaps.md)
- [Research questions](docs/research-questions.md)
- [Methodology](docs/methodology.md)
- [System architecture](docs/system-architecture.md)
- [Dataset protocol](dataset/README.md)
- [Experimental protocol](docs/experimental-protocol.md)
- [Results template](results/README.md)
- [Wiki-style pages](wiki/README.md)

## Repository structure

```text
.
├── README.md
├── LICENSE
├── LICENSE-DECISION.md
├── CITATION.cff
├── CONTRIBUTING.md
├── CHANGELOG.md
├── .gitignore
├── docs/                 # Research design and protocols
├── dataset/              # Dataset inventory and data governance
├── experiments/          # Reproducible experiment plans
├── results/              # Result templates; no fabricated metrics
├── references/           # Bibliography
└── wiki/                 # Markdown source for GitHub Wiki pages
```

## Dataset and data governance

Do not assume that datasets with similar names contain compatible modalities, labels, participants, or sampling rates. Before use, record the original source, license, modality, task, label definition, and split policy.

Never commit identifiable participant videos, faces, health records, consent forms, or other sensitive raw data. Keep data outside version control and publish only approved, de-identified derivatives when necessary.

## Evaluation plan

Report, where applicable:

- Accuracy, macro precision, macro recall, macro-F1, and per-class results
- Confusion matrix and class-wise error analysis
- False directional command activations per minute/session
- False Stop rate, missed intended commands, and No Command rejection rate
- End-to-end latency, processing FPS, and dropped-frame rate
- Participant-wise results and confidence intervals where the sample size supports them

Split by participant (and, where relevant, by session) before generating overlapping windows. Never randomly split highly overlapping windows from the same recording across train and test. Keep preprocessing, threshold tuning, and model selection on the training/validation data only.

## Research status

| Work package | Status |
|---|---|
| Research topic and camera-only scope | Defined |
| Literature review and gap validation | In progress |
| Dataset audit and data protocol | Pending |
| Data collection / annotation protocol | Pending |
| Baseline implementation | Pending |
| Temporal model implementation | Pending |
| Safety-gate experiments | Pending |
| Participant-independent evaluation | Pending |

Update this table only when the corresponding work is actually completed and documented.

## Limitations and safety statement

This repository is for academic research and offline prototyping. It is not a medical device and must not be connected to an occupied or powered wheelchair based only on results from this project.

Tremor presence or severity must not be inferred as a clinical diagnosis from this system. The project concerns command interpretation under motion variability, not diagnosis or treatment of Parkinson's disease.

## References

- Huda, M. N., Ali, M. E., & Sadi, M. S. (2025). Developing a real-time hand-gesture recognition technique for wheelchair control. *PLOS ONE, 20*(4), e0319996. https://doi.org/10.1371/journal.pone.0319996
- Nguyen, et al. (2025). Vision-Based Hand Gesture Recognition Using a YOLOv8n Model for the Navigation of a Smart Wheelchair. *Electronics, 14*(4), 734. https://doi.org/10.3390/electronics14040734

See [references/bibliography.bib](references/bibliography.bib). Verify bibliographic metadata against publisher records before citing in a manuscript.

## Citation

If you use this repository, cite it using the metadata in [CITATION.cff](CITATION.cff). A DOI and final author list should be added when available.

## License

This project is licensed under the [MIT License](LICENSE). See also [LICENSE-DECISION.md](LICENSE-DECISION.md).

## Team

Repository owner: [RakibCSE30](https://github.com/RakibCSE30). Add all confirmed team members, affiliations, and contribution roles here with their consent.
