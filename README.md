# Utilizing news sentiment to predict future price of the Vanguard ETF

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

## Introduction
The advent of neural networks has transformed the landscape for predictive modeling in the financial markets. Unlike traditional autoregressive techniques like ARIMA, neural network architectures can learn long- and short-term dependencies in sequential data. This is an important improvement as financial securities are generally driven by longer-term trends, whereas short-term price action is often volatile and trends are short-lived. Furthermore, novel developments in transformer-based neural network architectures have enabled sentiment analysis of a large corpus of textual financial news headlines. News headline embeddings have been found to improve a model’s ability to predict the next day’s stock price (Qayyum, 2025), but can suffer from issues such as unwanted data leakage during model development and vector sparsity due to short headline titles. For this reason, this project intends to investigate how textual analysis alongside univariate price can be used in the financial markets for resource allocation and risk management. As such, this project intends to evaluate two objectives:

- Does incorporating aggregated daily sentiment alongside univariate price improve predictive performance?

- Does incorporating news sentiment alongside price in network modeling improve predictive performance over traditional ARIMA modeling?

The results from this project will provide insight into the extent to which sentiment analysis improves model performance. Additionally, it will provide insight into whether the performance increase is meaningful enough to justify training of a more complex and resource intensive model. 

## Main Methods Used

For this project, a univariate hyperparameter-tuned ARIMA model will establish the baseline model. To accomplish the task of sentiment analysis, a pre-trained Bidirectional Encoder Representations from Transformers (BERT) model will be employed. BERT models are specially designed transformer models for NLP tasks such as text classification. Specifically, this project will employ the pre-trained Fin-BERT model available from Hugging Face. The model has been pre-trained on a financial text corpus and will be fine-tuned and adapted for new headline sentiment analysis. Finally, three sequential neural network architectures will be utilized to incorporate univariate price and daily aggregated news sentiment to predict the future daily price of the Vanguard Technology ETF. Specifically, these models include a Gated Recurrent Unit (GRU), a Long-Short Term Memory Network, and the Transformer for network modeling.


## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         utilizing_news_sentiment_to_predict_future_price_of_the_vanguard_etf and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── utilizing_news_sentiment_to_predict_future_price_of_the_vanguard_etf   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes utilizing_news_sentiment_to_predict_future_price_of_the_vanguard_etf a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

--------

