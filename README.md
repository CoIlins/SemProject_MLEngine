# UpShift ML engine

Our engine compares a student's profile with job descriptions, ranks suggestions and shows skills to check. A separate classifier recognises the tone of feedback.

## Final submission

Open **[MiniLM_Final.ipynb](MiniLM_Final.ipynb)** for the complete, executed workflow.

[Open in Google Colab](https://colab.research.google.com/github/CoIlins/SemProject_MLEngine/blob/main/MiniLM_Final.ipynb)

The numbered steps cover data loading, cleaning, exploration, model comparison, evaluation, valid and invalid examples, and saving/reloading the app-compatible model. Longer shared functions are included in expandable setup cells. No other project code file is needed to run the notebook.

## Run it

1. Open a fresh Colab runtime and make the three original files available: `Resume.csv`, `postings.csv` and `skills_en.csv`.
2. Set `DATA_FOLDER` in Step 1 to their location, then run the cells in order. Internet is needed on the first run for dependencies, MiniLM and TweetEval. Restart the runtime if Colab requests it after installation.
3. Find generated results, model files and `UpShift_Final_Model.zip` in `UpShift_Final_Output`. Raw datasets are not changed or uploaded to this repository.

[Team dataset folder](https://drive.google.com/drive/folders/1OS_u2gUFYCGqZtl-Q2izLvgZZSFi9ZS9)

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
