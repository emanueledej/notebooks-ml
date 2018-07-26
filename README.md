# Notebooks

## Contributing

When adding commits to a project, add the name of the project in the beginning of the commit message.
E.g.: `[project] Add raw data`.

## Structure

```
├── <project_name>/
|   ├── data/
|   |   ├── __init__.py
|   |   ├── dataset.py              # Code to download or generate data
│   |   ├── external/               # Data from third party sources
│   |   ├── interim /               # Intermediate data that has been transformed
│   |   ├── processed/              # The final, canonical data sets for modeling
│   |   └── raw/                    # The original, immutable data dump
|   |
|   ├── docs                        # Documentation
│   |
|   ├── models                      # Trained and serialized models, model predictions, or model summaries
|   |   └── __init__.py             # Scripts to train models and then use trained models to make predictions
|   |
|   └── notebooks                   # Jupyter notebooks. Naming convention is a number (for ordering),
│                                   # the creator's initials, and a short - delimited description, e.g.
│                                   # 1.0-jqp-initial-data-exploration.
└── <project_name>/
```

## Installation

```sh
brew install node
pip install pipenv
pipenv install
```

Config [notebooks diff](https://nbdime.readthedocs.io/en/stable/) for git:

```sh
pipenv run nbdime config-git --enable --global
```

Or use the web ui:

```sh
nbdiff-web [<commit> [<commit>]] [<path>]
```

Config spaCy models:

```sh
pipenv run python -m spacy download en_core_web_md
pipenv run python -m spacy link en_core_web_md en

pipenv run python -m spacy download pt_core_news_sm
pipenv run python -m spacy link pt_core_news_sm pt
```

## Running it

```sh
pipenv run jupyter lab
```
