# UpShift ML engine

Our engine compares a student's profile with job descriptions, ranks suggestions and shows skills to check. A separate classifier recognises the tone of feedback.

## Final submission

Open **[SemanticMatching_Final.ipynb](SemanticMatching_Final.ipynb)** for the complete, executed workflow.

[Open in Google Colab](https://colab.research.google.com/github/CoIlins/SemProject_MLEngine/blob/main/SemanticMatching_Final.ipynb)

The notebook builds on the original work in five visible sections: **cleaning**, **exploration**, **modelling**, **semantic matching**, and **the complete app model**. The original logistic regression, SVM, Naive Bayes, baseline, word-count, TF-IDF and LSA experiments are retained. Short explanations and charts describe what each check measures. The semantic sentence encoder is pretrained; the CV and feedback classifiers are trained in the notebook. All cells are visible, and the original base notebook is preserved unchanged.

## Read or rerun

**For assessment:** open the final notebook and read the saved results and charts. No setup or retraining is needed to review it.

**Only to rerun:** use Python 3.12/Jupyter with `requirements.txt`, download the three CSVs from the [shared Drive](https://drive.google.com/drive/folders/11kEwky5_pJ6IpLfNWepHzNfzI0vKkW-2) into one folder, and enter that folder's path in Step 1. In Colab, install the requirements and upload the CSVs into a folder in the Files panel first. Full reruns take time; use the saved outputs when reviewing or presenting.

The lecturer needs Viewer access to the Drive folder only if downloading the data to rerun. Saved outputs can be read directly from the public notebook. Generated files go into `UpShift_Final_Output`; the original CSVs are unchanged.

## What we compared

- **CV classification:** trained logistic regression, SVM and Naive Bayes against a majority-category baseline, including title-leakage and near-copy checks.
- **Job matching:** word counts, TF-IDF, LSA and pretrained semantic matching on the same small research sample.
- **Skill mentions:** ESCO phrase matching, overlap diagnostics and an exercise awaiting human review.
- **Feedback:** logistic regression trained on labelled TweetEval English text, compared with VADER and a majority-label baseline. It never changes job ranking.

The field-agreement check uses rough labels inferred from job titles, not verified job relevance. Human relevance ratings and the displayed skill review remain pending. Similarity is not a hiring probability. Historical international postings cannot establish current Kenyan eligibility.

## App handoff

The final section includes all shared model code and generates the complete backend-format package under `UpShift_Final_Output/live_app/artifacts/`: `upshift_bundle.joblib`, `deployment_config.json`, `semantic_encoder/` and `upshift_ai/`. It also creates `UpShift_Complete_Model.zip`. No separate project Python file is needed to run the notebook. The first run downloads the fixed encoder and TweetEval dataset versions.

The rebuilt model was compared through the actual `backend.models.Models` adapter against the existing app model: **20 checks passed**, covering live/research ranking, skill explanations, feedback and invalid inputs. Scores and probabilities matched within 0.000001. Source-code equivalence, vocabulary, job IDs, skill rules and all 6,000 semantic vectors were checked too. Section 5.7 includes a portable comparison with recorded backend outputs.

Running this notebook saves a separate package; it does not deploy it or modify the model currently used by the app. Accounts, approved vacancies and eligibility checks remain backend responsibilities. [Mobile repository](https://github.com/wangui-technerd/Upshift/tree/android-frontend).

[Existing model handoff folder](https://drive.google.com/drive/folders/1tfmOnYKapGidW1i8TDKwe2CIQjgVpxpX)

## Earlier work

- `LogisticRegression_Base.ipynb`: original base notebook, preserved with the correct extension.
- `01_cleaning.ipynb` and `Resume_Exploration.ipynb`: earlier exploration and development.
- `src/`: earlier supporting code. The final notebook includes its own full workflow.

Team: Hafswa, Collins and Shifla.
