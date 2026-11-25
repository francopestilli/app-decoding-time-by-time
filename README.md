#  app-decoding-time-by-time 

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Decodes condition labels over time from MEG gradiometer epochs with MNE-Python SlidingEstimator (standardised logistic regression, 5-fold ROC AUC) and plots the decoding score time course.**

Selects the 'auditory' epochs, keeps the gradiometer channels and fits a scikit-learn pipeline (StandardScaler and LogisticRegression) independently at each time point with mne.decoding.SlidingEstimator, scoring with 5-fold cross-validated ROC AUC against event codes. Outputs a PNG of the mean score over time with the chance level. The condition name and channel type are hard-coded (MNE sample-dataset style 'auditory' left vs right), so it only runs on epochs that contain an 'auditory' condition with two event codes and gradiometers.

| | |
|---|---|
| 📥 **Inputs** | `neuro/meeg/mne/epochs` |
| 📤 **Outputs** | `generic/image/png` |
| 🐳 **Container** | `brainlife/mne:1.0.2` |
| ⚙️ **Resources** | 1 CPUs |
| 🔗 **Run it** | [doi.org/10.25663/brainlife.app.655](https://doi.org/10.25663/brainlife.app.655) |

#### 📥 Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `epo` | `neuro/meeg/mne/epochs` | yes | MEG epochs (MNE -epo.fif) with an 'auditory' condition. Must contain gradiometer channels and events tagged auditory with two classes. |

#### 📤 Outputs

| Output | Datatype | Description |
|---|---|---|
| `out_figs` | `generic/image/png` | Sensor-Space-Decoding.png: mean cross-validated ROC AUC over time with the chance level. |

<!-- brainlife-app:end -->

