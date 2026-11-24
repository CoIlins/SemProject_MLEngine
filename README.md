# UpShift ML engine

Our engine compares a student's profile with job descriptions, ranks suggestions and shows skills to check. A separate classifier recognises the tone of feedback.

## Final submission

Open **[SemanticMatching_Final.ipynb](SemanticMatching_Final.ipynb)** for the complete, executed workflow.

[Open in Google Colab](https://colab.research.google.com/github/CoIlins/SemProject_MLEngine/blob/main/SemanticMatching_Final.ipynb)

The notebook builds on the original work in four collapsible sections: **cleaning**, **exploration**, **modelling**, and **semantic matching**. The original logistic regression, SVM, Naive Bayes, baseline, word-count, TF-IDF and LSA experiments are retained. Short explanations and charts describe what each check measures. The semantic sentence encoder is pretrained; the CV classifiers are trained in the notebook.

## Read or rerun

**For assessment:** open the final notebook and read the saved results and charts. No setup or retraining is needed to review it.

**Only to rerun:** use Python 3.12/Jupyter with `requirements.txt`, download the three CSVs from the [shared Drive](https://drive.google.com/drive/folders/11kEwky5_pJ6IpLfNWepHzNfzI0vKkW-2) into one folder, and enter that folder's path in Step 1. In Colab, install the requirements and upload the CSVs into a folder in the Files panel first. Full reruns take time; use the saved outputs when reviewing or presenting.

The lecturer needs Viewer access to the Drive folder only if downloading the data to rerun. Saved outputs can be read directly from the public notebook. Generated files go into `UpShift_Final_Output`; the original CSVs are unchanged.

## What we compared

- **CV classification:** trained logistic regression, SVM and Naive Bayes against a majority-category baseline, including title-leakage and near-copy checks.
- **Job matching:** word counts, TF-IDF, LSA and pretrained semantic matching on the same small research sample.
- **Skill mentions:** ESCO phrase matching, overlap diagnostics and an exercise awaiting human review.

The field-agreement check uses rough labels inferred from job titles, not verified job relevance. Human relevance ratings and the displayed skill review remain pending. Similarity is not a hiring probability. Historical international postings cannot establish current Kenyan eligibility.

## App handoff

The notebook saves research models separately from the existing app deployment bundle. Running it does not replace or deploy the working backend model. The backend supplies approved vacancies; the app's semantic ranking and skill-context rules are implemented in the [mobile repository](https://github.com/wangui-technerd/Upshift/tree/android-frontend). Feedback-tone classification remains a separate experiment and does not change job ranking.

[Existing model handoff folder](https://drive.google.com/drive/folders/1tfmOnYKapGidW1i8TDKwe2CIQjgVpxpX)

## Earlier work

- `LogisticRegression_Base.ipynb`: original base notebook, preserved with the correct extension.
- `01_cleaning.ipynb` and `Resume_Exploration.ipynb`: earlier exploration and development.
- `src/`: earlier supporting code. The final notebook includes its own full workflow.

Team: Hafswa, Collins and Shifla.
