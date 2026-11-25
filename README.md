# UpShift AI

We built a job-matching workflow that compares a student’s profile with job descriptions and shows skills to check.

## Our notebooks

- [Final notebook](SemanticMatching_Final.ipynb) — our complete workflow, results, charts and app-model code.
- [Base notebook](LogisticRegression_Base.ipynb) — our original logistic-regression work, preserved unchanged.
- [Open the final notebook in Colab](https://colab.research.google.com/github/CoIlins/SemProject_MLEngine/blob/main/SemanticMatching_Final.ipynb).

We compare word matching with semantic matching using a pretrained text model. We also train CV classifiers and a separate feedback-tone classifier. We explain our rule-based chatbot and course guidance at the end.

## Run our notebook

We include saved outputs, so the results can be reviewed without rerunning. To rerun:

1. Use Python 3.12 and install `requirements.txt`.
2. Download `Resume.csv`, `postings.csv` and `skills_en.csv` from our [dataset folder](https://drive.google.com/drive/folders/1OS_u2gUFYCGqZtl-Q2izLvgZZSFi9ZS9).
3. Put them in one folder, enter its path in the setup cell and run the cells in order.

Drive access is required for the data. The first full run also downloads the pretrained text model and labelled English tweets used for feedback training.

## Our app connection

We export the backend files to `UpShift_Final_Output/live_app/artifacts/`. We checked the rebuilt model against our backend across 20 cases. Our [mobile repository](https://github.com/wangui-technerd/Upshift/tree/android-frontend) contains the app and setup instructions.

Our scores do not predict hiring success. The matching evaluation uses rough career-field labels; independent human relevance review remains pending.
