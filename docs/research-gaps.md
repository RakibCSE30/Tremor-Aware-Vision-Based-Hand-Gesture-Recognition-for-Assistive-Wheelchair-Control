# Research Gap Analysis

The following are **candidate gaps to validate through a systematic literature review**, not claims that no prior work exists.

## Gap 1 — Intended gesture versus involuntary motion

A system may recognize a hand pose or detect tremor-like movement without determining whether a particular wheelchair command was intentionally issued. The project should investigate command-level interpretation and explicitly represent ambiguous or non-command motion.

**Evidence required:** compare published task definitions, annotation schemes, and evaluation protocols. Do not infer a lack of prior work from paper titles alone.

## Gap 2 — Temporal overlap and motion variability

Intentional gestures and involuntary movement may share spatial patterns or temporal frequency components. A fixed smoothing or frequency filter may suppress useful gesture dynamics or retain confounding motion.

**Research direction:** compare raw normalized landmark sequences, interpretable temporal features, and carefully justified frequency features. Report camera frame rate, sequence duration, dropped frames, and filtering delay.

## Gap 3 — Data alignment and annotation

A meaningful evaluation may require synchronized RGB video, intended command labels, event boundaries, non-command intervals, and participant/session metadata. Public tremor datasets may contain sensor signals without camera video or intended wheelchair commands.

**Research direction:** audit each dataset separately and, if necessary, define a consent-based annotation protocol. Never claim synchronized ground truth when it does not exist.

## Gap 4 — Safety-oriented evaluation

Overall accuracy or macro-F1 does not reveal how often a model issues an unintended directional command. For assistive control, event-level false activations, missed commands, false stops, latency, and safe rejection are important.

**Research direction:** evaluate the complete classifier-plus-gate pipeline in an offline simulator, with participant-wise testing and predefined failure criteria.

## Gap validation checklist

- Search multiple scholarly databases with reproducible queries and dates.
- Include recent and foundational studies; record inclusion/exclusion criteria.
- Extract modality, participants, labels, task, model, split strategy, metrics, and limitations.
- Distinguish a genuinely unaddressed gap from a gap addressed under different conditions.
- Update this document with citations and counter-evidence.
