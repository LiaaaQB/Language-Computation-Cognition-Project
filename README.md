# Subjective Cognitive Comprehension or Eye Fixations? A Study

This repository investigates whether reading-comprehension accuracy can be
predicted from eye-tracking measurements alone, subjective questionnaire responses,
or a combination of both.

The main hypothesis:
- Metacomprehension features such as reported confidence or text difficulty positively impact predictive eye tracking models that predict reading comprehension success.

The main workflow documented here is:

- `Main.ipynb`

## Notebook overview

The notebook performs the following experiments:

1. Find correlation between eye tracking features and metacomprehension features
2. Feature importance analysis on all available features
3. Incremental contribution of each feature
4. Ablation study between both feature groups
5. Testing the model on different evaluation regimes

## Data

The notebook expects these files:

```text
Data/
├── 18sat_labels.csv
└── 18sat_fixfinal.csv
```

The data was extracted from the EyeBench project.
The paths are configured near the beginning of the notebook, change if needed:

```python
LABELS_PATH = Path("Data/18sat_labels.csv")
FIX_PATH = Path("Data/18sat_fixfinal.csv")
```


## How to use:

Creating the enviroment:

```bash
conda env create -f environment.yml
conda activate language-project
```

Open `Project_notebook_error_analysis.ipynb`, select the
`Python (language-project)` kernel, and run the cells from top to bottom.


## Outputs

The notebook produces:

- correlation tables and a strongest-correlation plot
- logistic-regression performance scores
- ranked feature coefficients
- incremental feature-contribution curves
- feature-group ablation results
- evaluation-regime summaries and ROC curves
- an out-of-fold confusion matrix
- passage-level prediction error rates


All plots may be found in the /plots folder. 
