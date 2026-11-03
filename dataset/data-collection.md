# Data Collection and Annotation Protocol (Draft)

This is a protocol template, not authorization to collect data. Obtain ethics review and informed consent before recruitment or recording.

## Recording protocol fields

- Camera make/model, resolution, nominal and measured FPS
- Camera position, distance, view angle, lighting
- Session identifier and pseudonymous participant identifier
- Gesture instruction and randomized trial order
- Rest/non-command intervals and ambiguous trials
- Tracking failures, dropped frames, and protocol deviations

## Annotation schema

| Field | Description |
|---|---|
| participant_id | Pseudonymous identifier |
| session_id | Recording session identifier |
| start_time / end_time | Event timestamps |
| intended_command | Forward / Backward / Left / Right / Stop / No Command / Ambiguous |
| annotator_id | Pseudonymous annotator code |
| confidence | Predefined annotation confidence scale |
| notes | Non-identifying protocol note |

Do not label an event as Parkinsonian tremor solely from appearance. If a clinical status label is collected, it is sensitive health data and requires explicit ethical and privacy safeguards.
