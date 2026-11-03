# Experiments

Organize experiments so that every result can be traced to a configuration, dataset version, split definition, and code revision.

Suggested structure:

```text
experiments/
├── baseline/
│   └── README.md
├── temporal-models/
│   └── README.md
└── command-gating/
    └── README.md
```

For each experiment, record its research question, hypothesis, data provenance, participant-wise split, preprocessing, model, hyperparameters, seeds, metrics, compute environment, and limitations. Do not commit private raw data or large model artifacts without an approved storage policy.
