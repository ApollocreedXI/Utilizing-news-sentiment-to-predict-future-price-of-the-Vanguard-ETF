# Utilizing news sentiment to predict future price of the Vanguard Information Technology ETF

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

## Introduction
The advent of neural networks has transformed the landscape for predictive modeling in the financial markets. Unlike traditional autoregressive techniques like ARIMA, neural network architectures can learn long- and short-term dependencies in sequential data. This is an important improvement as financial securities are generally driven by longer-term trends, whereas short-term price action is often volatile and trends are short-lived. Furthermore, novel developments in transformer-based neural network architectures have enabled sentiment analysis of a large corpus of textual financial news headlines. News headline embeddings have been found to improve a model’s ability to predict the next day’s stock price (Qayyum, 2025), but can suffer from issues such as unwanted data leakage during model development and vector sparsity due to short headline titles. For this reason, this project intends to investigate how textual analysis alongside univariate price can be used in the financial markets for resource allocation and risk management. As such, this project intends to evaluate two objectives:

- Does incorporating aggregated daily sentiment alongside univariate price improve predictive performance in network modeling?

- Does incorporating news sentiment alongside price in network modeling improve predictive performance over traditional ARIMA modeling?

The results from this project will provide insight into the extent to which sentiment analysis improves model performance. Additionally, it will provide insight into whether the performance increase is meaningful enough to justify training of a more complex and resource intensive model. 

## Main Methods Used

For this project, a univariate hyperparameter-tuned ARIMA model will establish the baseline model for predicting the future daily price of the Vanguard Information Technology ETF. To accomplish the task of sentiment analysis, a pre-trained Bidirectional Encoder Representations from Transformers (BERT) model will be employed. Specifically, this project will employ the pre-trained Fin-BERT model available from Hugging Face. The model has been pre-trained on a financial text corpus and will be fine-tuned and adapted for new headline sentiment analysis. Finally, a LSTM model will be trained solely on soley univariate price to establish baseline network performance statistics. Later, daily aggregated news sentiment will be incorporated alongside univariate price in three network models to evaluate performance improvements over all univariate modeling strategies. Specifically, these models include a Gated Recurrent Unit (GRU), a Long-Short Term Memory Network, and the Transformer for network modeling.

## Conclusion
The project investigates two main research questions:
- Does incorporating aggregated daily sentiment alongside univariate price improve predictive performance in network modeling?

- Does incorporating news sentiment alongside price in network modeling improve predictive performance over traditional ARIMA modeling?

The result of the network modeling does demonstrate that using aggregated daily sentiment alongside univariate price does improve predictive performance. This is supported by both the LSTM and GRU networks, whose performance outperformed that of the univariate LSTM network. This finding is in alignment with current literature that sentiment influences a security's price. (Dahal , et al., 2023)

The results of the project do not support that incorporating news sentiment alongside price in network modeling outperforms traditional ARIMA modeling. This is likely due to insufficient training data and should not be taken as conclusive evidence that ARIMA modeling is superior. In fact, other studies have shown that utilizing sentiment analysis to predict a stock's price does outperform traditional statistical modeling. Future exploration for this project would be to train a model on multiple related securities, such as those securities that compose the Vanguard Information Technology ETF. One would then utilize this pretrained model and fine-tune it on the multivariate dataset trained in this project. This will give the models employed in this project sufficient data from which to train these models with large trainable parameters.


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

