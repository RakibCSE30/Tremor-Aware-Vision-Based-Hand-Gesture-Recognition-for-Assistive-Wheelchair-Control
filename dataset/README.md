# Dataset Documentation and Data Governance

## Purpose

This directory documents candidate datasets and approved metadata. It should not contain raw identifiable videos, medical records, consent forms, or private participant data.

## Dataset audit template

For every candidate dataset, record:

| Field | Required detail |
|---|---|
| Official name and source | Publisher/repository and canonical URL |
| License | Exact license and permitted use |
| Modality | RGB video, depth, IMU, EMG, audio, or other |
| Task | Tremor characterization, gesture recognition, wheelchair control, etc. |
| Labels | Exact label definitions and annotation process |
| Participants | Count, relevant inclusion criteria, session structure |
| Sampling | FPS or Hz, resolution, timestamp quality |
| Synchronization | Whether modalities are synchronized and how |
| Availability | Access conditions and redistribution restrictions |
| Suitability | Which research question it can support and why |

## Compatibility warning

A dataset containing IMU measurements is not an RGB video dataset. It may support background review or a separate sensor-based analysis, but it cannot be represented as direct input or validation data for the camera-only deployed pipeline. Likewise, generic gesture datasets do not automatically contain tremor labels, Parkinsonian participants, wheelchair commands, or intended-command ground truth.

Candidate datasets must be individually checked against their original documentation before being listed as used. Do not infer content or licensing from a repository name.

## Data collection and annotation

If new video is collected, obtain institutional ethics approval where required, informed consent, and a data-management plan. Define intended command, non-command, ambiguous interval, onset/offset, annotation confidence, and adjudication procedure. Minimize collection of faces and background identifiers where possible.

## Storage policy

- Keep raw data outside Git.
- Use access-controlled storage and encryption where appropriate.
- Publish only data explicitly cleared for release.
- Document transformations and maintain a data dictionary.
- Never commit participant names, contact details, health records, or consent documents.

See [data collection protocol](data-collection.md).
