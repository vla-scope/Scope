# VLA-Scope

## Shift-Aware Failure Prediction for Vision-Language-Action Models

**Kaiwen Zhu, Dongfang Liu, and Liangkai Liu**

[Project Website](https://vla-scope.github.io/) | [Paper](https://arxiv.org/abs/2609.21246) | [PDF](https://arxiv.org/pdf/2609.21246)

VLA-Scope combines initial input-shift characterization with execution evidence to predict failure during out-of-distribution rollouts, without changing the underlying VLA policy.

- **OOD Characterizer:** uses pooled image and language representations to detect OOD inputs and classify their shift categories.
- **Failure Risk Predictor:** combines predicted OOD type, action-prefix features, and cumulative execution-step representations in a shared logistic regression model.

## Status

This is the research-code repository for VLA-Scope. Research code has not yet been released. The project website and demonstration videos are available at [vla-scope.github.io](https://vla-scope.github.io/).

The website source, paper PDF, and demonstration videos are maintained separately in [vla-scope/vla-scope.github.io](https://github.com/vla-scope/vla-scope.github.io).

## Evaluation

Evaluated with OpenVLA on ten LIBERO-Spatial tasks using Leave-One-Group-Out cross-validation:

| Metric | Result |
| --- | --- |
| OOD detection ROC-AUC | 0.9454 |
| OOD type classification accuracy | 91.0% |
| Failure prediction ROC-AUC at 60 executed actions | 0.8497 |

Failure prediction is evaluated on all 1,400 OOD rollouts, independently of the initial OOD gate. See the paper for the complete protocol, comparisons, and limitations.
