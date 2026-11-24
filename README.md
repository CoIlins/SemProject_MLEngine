# UpShift ML engine

Our engine compares a student's profile with job descriptions, ranks suggestions and shows skills to check. A separate classifier recognises the tone of feedback.

## Final submission

Open **[MiniLM_Final.ipynb](MiniLM_Final.ipynb)** for the complete, executed workflow.

[Open in Google Colab](https://colab.research.google.com/github/CoIlins/SemProject_MLEngine/blob/main/MiniLM_Final.ipynb)

The numbered steps cover data loading, cleaning, exploration, model comparison, evaluation, valid and invalid examples, and saving/reloading the app-compatible model. Longer shared functions are included in expandable setup cells. No other project code file is needed to run the notebook.

## Read or rerun

**For assessment:** open the final notebook and read the saved results and five figures. No setup or retraining is needed to review it.

**Only to rerun:** use Python 3.12/Jupyter with `requirements.txt`, download the three CSVs from the [shared Drive](https://drive.google.com/drive/folders/11kEwky5_pJ6IpLfNWepHzNfzI0vKkW-2) into one folder, and enter that folder's path in Step 1. In Colab, install the requirements and upload the CSVs into a folder in the Files panel first. The first full CPU run took about 28 minutes on our PC.

The lecturer needs Viewer access to the Drive folder only if downloading the data to rerun. Saved outputs can be read directly from the public notebook. Generated files go into `UpShift_Final_Output`; the original CSVs are unchanged.

## What we compared

- **Job matching:** TF-IDF word matching against pretrained MiniLM meaning-based matching. MiniLM was not trained or fine-tuned by our team.
- **Skill explanations:** ESCO names and rules compare required skills with the profile. This is separate from the meaning score.
- **Feedback tone:** VADER rules against logistic regression trained on labelled TweetEval English text. Tone does not change job ranking. Sending feedback is a separate app operation.
- **Earlier supporting exercise:** career-category classifiers; these do not determine the final job ranking.

The small job-relevance comparison uses 12 fictional profiles and one AI-assisted set of ratings. Independent human validation remains pending. NDCG measures ranking order, not matching accuracy or the chance of getting a job. Historical international postings are research data; the app backend supplies approved active vacancies and checks eligibility rules separately.

## App handoff

The notebook saves the same schema-2 format loaded by the Android backend: `upshift_bundle.joblib`, `deployment_config.json`, `semantic_encoder/` and the included `upshift_ai/` functions. Trained binaries are generated locally rather than committed to GitHub. Only load joblib files from trusted project sources.

[App repository](https://github.com/wangui-technerd/Upshift/tree/android-frontend) · [Existing model handoff folder](https://drive.google.com/drive/folders/1tfmOnYKapGidW1i8TDKwe2CIQjgVpxpX)

## Earlier work

- `LogisticRegression_Base.ipynb`: original base notebook, preserved with the correct extension.
- `01_cleaning.ipynb` and `Resume_Exploration.ipynb`: earlier exploration and development.
- `src/`: earlier supporting code. The final notebook includes its own full workflow.

Team: Hafswa, Collins and Shifla.
