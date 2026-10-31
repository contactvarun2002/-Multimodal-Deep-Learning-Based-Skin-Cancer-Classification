# Derm7pt — Final Held-Out Test Results

**Evaluation source:** Step 6 full-data five-class HH-dynamics-inspired classifier.
**Model selection:** performed on original validation partition (not on test in this script).

## Actual held-out test metrics

| Metric | Result |
|---|---:|
| Test_Samples | 152 |
| Classes_In_Test | 5 |
| Accuracy | 0.7566 |
| Balanced_Accuracy_Present_Classes | 0.7107 |
| Macro_Precision_All5 | 0.6615 |
| Macro_Recall_All5 | 0.7107 |
| Macro_F1_All5 | 0.6750 |
| Weighted_F1 | 0.7701 |
| Macro_OVR_AUC_All5 | 0.9417 |
| MCC | 0.6207 |
| Cohen_Kappa | 0.6171 |
| Log_Loss | 0.6390 |

## Per-class support and F1

| Class | Support | F1 | ROC-AUC |
|---|---:|---:|---:|
| Nevus | 87 | 0.8364 | 0.9178 |
| Melanoma | 33 | 0.7385 | 0.9516 |
| MISC | 20 | 0.6512 | 0.9534 |
| SK | 6 | 0.3158 | 0.9155 |
| BCC | 6 | 0.8333 | 0.9703 |

## Uncertainty

Bootstrap method: Lesion-level bootstrap; clustering by patient unavailable.
Intervals describe the fixed test sample; they are not validation of clinical generalization.

## Research limitations

- Patient IDs are incomplete; patient-level independence not demonstrated.
- Step 12 CV was lesion-only exploratory; DO NOT label it patient-grouped.
- Step 12 selected epochs on evaluated fold validation data; fold metrics may be optimistic.
- Step 5 supervised projections were learned on original Train and selected using Validation; Step 6 test scores are tied to that fixed procedure.
- Step 4 feature backbones were independent frozen pretrained architectures, not exact paper-defined trained hybrids.
- HH membrane is a differentiable HH-inspired approximation, not a validated exact biological spike simulator.
- Step 4 FT-Transformer metadata embedding training provenance must be independently checked for train/test and CV leakage.
- Do not compare Step 10 repeated seeds or Step 12 fold means as independent cohorts or merge them with held-out-test accuracy.
- The 5-class MISC diagnosis mapping needs clinical/research protocol verification before manuscript submission.

## Evidence inventory

Consult Evidence_Inventory.csv for Step 7, 9, 10 and 12 status.
No external-dataset validation is claimed.