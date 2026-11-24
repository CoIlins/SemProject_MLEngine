# UpShift ML engine

Our engine compares a student's profile with job descriptions, ranks suggestions and shows skills to check. A separate classifier recognises the tone of feedback.

## Final submission

Open **[MiniLM_Final.ipynb](MiniLM_Final.ipynb)** for the complete, executed workflow.

[Open in Google Colab](https://colab.research.google.com/github/CoIlins/SemProject_MLEngine/blob/main/MiniLM_Final.ipynb)

The numbered steps cover data loading, cleaning, exploration, model comparison, evaluation, valid and invalid examples, and saving/reloading the app-compatible model. Longer shared functions are included in expandable setup cells. No other project code file is needed to run the notebook.

## Run it

**Recommended: Colab, on any computer with a browser.**

1. Give the runner's Google account **Viewer** access to the [shared project folder](https://drive.google.com/drive/folders/11kEwky5_pJ6IpLfNWepHzNfzI0vKkW-2). The current data is restricted to named accounts; a public notebook does not make private Drive files public.
2. Open the Colab link above, select **Runtime → Run all**, and complete the Google sign-in prompt in Step 1. The notebook reads the three CSVs directly by their Drive IDs; no personal folder paths or shortcuts are needed.
3. Allow the run to finish. The first full CPU run took about 28 minutes in our check. Restart once if requested after dependency installation, then run all again. Keep the saved results visible during the demo.
4. Download `UpShift_Final_Model.zip` from the Colab Files panel before ending the runtime if you want to retain the generated model. Original Drive data is never changed.

**Local Jupyter/VS Code:** use a dedicated Python 3.12 environment, install `requirements.txt`, and download/extract `Resume.csv`, `postings.csv` and `skills_en.csv` from [AI Datasets](https://drive.google.com/drive/folders/1OS_u2gUFYCGqZtl-Q2izLvgZZSFi9ZS9). Run the notebook and paste your own dataset-folder path when Step 1 asks. It supports nested folders and checks the original file fingerprints. Results are saved in `UpShift_Final_Output` beside the notebook's working folder. No Windows username or fixed Downloads path is required.

**Lecturer check:** share the project folder with the lecturer's Google email as a Viewer, send the Colab link, and ask them to run all while signed in with that account. If access is denied, check which account they used; do not make private data public just to bypass permissions.

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
