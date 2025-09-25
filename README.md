# cookiecutter

This is a project for cookiecutter


MLOps Project – Corrupt MNIST

This project demonstrates a simple MLOps workflow on the Corrupt MNIST dataset.
It includes data preprocessing, model training, evaluation, and visualization.

📦 Setup

Create and activate a virtual environment (recommended):

python -m venv env
source env/bin/activate   # Linux/Mac
env\Scripts\activate      # Windows


Install dependencies:

pip install -r requirements.txt


Install project in editable mode:

pip install -e .

⚡ Usage

We use the invoke
 task runner to simplify commands.
First install it if you haven’t already:

pip install invoke

Available tasks:

Preprocess raw data

invoke preprocess-data


This loads the corrupted MNIST .pt files, normalizes them, and stores them in data/processed/.

Train the model

invoke train


This trains the CNN, saves the model checkpoint in models/, and saves training curves in reports/figures/.

Evaluate the model

invoke evaluate --model-checkpoint=models/model.pt


This loads the saved model and prints accuracy on the test set.

Visualize embeddings

invoke visualize --model-checkpoint=models/model.pt


This extracts embeddings from the trained model, applies t-SNE, and saves a scatterplot in reports/figures/.

List all tasks

invoke --list



## Project structure

The directory structure of the project looks like this:
```txt
├── .github/                  # Github actions and dependabot
│   ├── dependabot.yaml
│   └── workflows/
│       └── tests.yaml
├── configs/                  # Configuration files
├── data/                     # Data directory
│   ├── processed
│   └── raw
├── dockerfiles/              # Dockerfiles
│   ├── api.Dockerfile
│   └── train.Dockerfile
├── docs/                     # Documentation
│   ├── mkdocs.yml
│   └── source/
│       └── index.md
├── models/                   # Trained models
├── notebooks/                # Jupyter notebooks
├── reports/                  # Reports
│   └── figures/
├── src/                      # Source code
│   ├── project_name/
│   │   ├── __init__.py
│   │   ├── api.py
│   │   ├── data.py
│   │   ├── evaluate.py
│   │   ├── models.py
│   │   ├── train.py
│   │   └── visualize.py
└── tests/                    # Tests
│   ├── __init__.py
│   ├── test_api.py
│   ├── test_data.py
│   └── test_model.py
├── .gitignore
├── .pre-commit-config.yaml
├── LICENSE
├── pyproject.toml            # Python project file
├── README.md                 # Project README
├── requirements.txt          # Project requirements
├── requirements_dev.txt      # Development requirements
└── tasks.py                  # Project tasks
```


Created using [mlops_template](https://github.com/SkafteNicki/mlops_template),
a [cookiecutter template](https://github.com/cookiecutter/cookiecutter) for getting
started with Machine Learning Operations (MLOps).


