# Problem Statement and Objectives

## Problem statement

A hand-gesture wheelchair interface must interpret a user's intended command from camera observations. In the presence of involuntary motion, transient pose changes and noisy trajectories may resemble intentional gestures. Frame-level classification alone may therefore be insufficient. The research problem is to investigate temporal interpretation and uncertainty-aware command generation under a camera-only constraint.

## General objective

To design and evaluate a vision-based hand-gesture recognition and command-gating framework that explicitly studies motion variability associated with Parkinsonian tremor.

## Specific objectives

1. Identify relevant limitations in existing vision-based wheelchair gesture interfaces.
2. Determine whether available datasets support the intended research questions.
3. Establish consistent landmark extraction, normalization, and sequence construction.
4. Compare a transparent baseline with temporal recognition models.
5. Define and evaluate a reject option and command persistence policy.
6. Quantify recognition errors, false command events, and runtime latency.
7. Document ethical, privacy, and deployment limitations.

## Out of scope

- Diagnosing Parkinson's disease or estimating clinical severity.
- Claiming that RGB video replaces clinical assessment.
- Treating IMU/EMG-only data as camera data.
- Operating a real wheelchair without independent safety engineering and supervised validation.
