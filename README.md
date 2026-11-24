# Group 09 · C3

**Respiratory demand: evidence before action**  
**Ariel Cusacovich and Ana Peris Diaz-Varela**  
Business Intelligence · IIB423T-1 · Universidad del Desarrollo  
**Assessed release: C3-2026-11-24-r4**

## Question and main conclusion

How did recorded respiratory emergency demand among children under 15 change across 2023–2024, and do simple daily prediction methods support using these records for advance planning?

In the same 22 hospitals, the first-half decline repeats across both quarters, but the second-half increase hides a fourth-quarter decline. Statistical MA(1), fitted on 2023 only, has higher validation error than the lag7 reference and slightly lower historical test error. Residual dependence and worse high-demand performance prevent recommending it for an operational pilot. OLS does not beat the reference in either period. We recommend quarterly review, publication-history checks and a revised specification evaluated on a genuinely new period. The MA(1) extension remains exploratory because 2024 was already inspected.

## Start here

Open **[01_C3_Study.ipynb](01_C3_Study.ipynb)**. It contains the complete executed pipeline, explanations, compact summary tables, four saved figures, feedback record and contributions. Read sections 1–4 for the question, data and EDA; 5–6 for modeling and evaluation; 7 for the visual system; and 8 for development, feedback and contributions.

**No installation, execution or data download is required for assessment.** Notebook outputs are saved. There are no datasets, data extracts, environment folders or legacy archives in this release.

## Pipeline and provenance

Identified DEIS/MINSAL annual snapshots → W2 scope extraction → fingerprint checks → ID/date/count validation → under-15 age sums → paired hospital-days → coverage and EDA → same-panel quarterly comparisons → calendar lags and training-only imputation → hospital MA(1) fits and diagnostics → past-only historical model comparison → common visual settings → saved tables and figures.

The notebook rebuilds 18,988 hospital-days from 37,976 selected hospital–date–cause records. It reports 26 observed hospitals, the descriptive fixed panel of 22, 18 absent reports, valid zeros, the corrected KPI and the Peñaflor check. The modeling target is a count per observed hospital-day, not a population rate.

The exact historical W2 source version is [ba82d9258886fab0857552ea2df7b2cd70bf6e87](https://github.com/arielcusacovich/GROUP_09_BI/tree/ba82d9258886fab0857552ea2df7b2cd70bf6e87). This is a provenance reference, **not the C3 repository to assess**. Original DEIS links, input hashes and the C2/W3 version fingerprints appear in notebook sections 2 and 8. Earlier data-containing archives are not part of the C3 release.

## Software and optional execution

Analysis was executed with Python 3.12.14, pandas 3.0.1, NumPy 2.5.4, statsmodels 0.15.0 and SciPy 1.18.1; matplotlib generates the plots and IPython captures visible outputs. The editable notebook contains the analysis and shared visual settings. MA(1) is a statistical model of innovations, compared with the lag7 reference and retained C2 OLS. Section 5 documents parameter fitting, constant-series rules, diagnostics and daily evaluation.

Optional rerunning requires Python with pandas, NumPy, matplotlib, IPython, statsmodels and SciPy in a notebook environment. Use the versions listed above, including statsmodels 0.15.0. Run the notebook from top to bottom. By default it reads the two uncleaned selected extracts from the exact W2 commit in memory and verifies their SHA-256 hashes. Alternatively, set `C3_W2_DIR` to an existing W2 folder. Both input routes have been checked against the same source fingerprints. The saved execution uses the verified local inputs; the default GitHub route was also successfully checked during preparation. No computer-specific path is embedded. Neither route exports data files. Rerunning is separate from assessment and is not required of the reviewer.

## Contributions and AI use

The contribution record is stated in notebook section 8. **AI use:** OpenAI Codex assisted extensively with code, calculations, charts and English drafting. Source, method and consistency checks are recorded in the notebook. We remain responsible for reviewing and explaining the work.
