# Assessing Financial Vulnerability in Indian Equities

Welcome to the Bankruptcy Prediction project! This project aims to predict bankruptcy for companies with and without using knowledge graph embeddings of the news of the companies combined with the machine learning techniques.

## Overview

Bankruptcy prediction is a critical task for financial institutions and investors to assess the financial health and stability of companies. This project utilizes knowledge graph embeddings generated from news related to the companies along with the machine learning algorithms to analyze financial data and predict the likelihood of bankruptcy for companies.

## Dataset

The dataset used in this project contains financial indicators and bankruptcy labels for a sample of companies. It includes features such as liquidity ratios, leverage ratios, profitability ratios, and activity ratios. The dataset is stored in the `dataset` directory.

## Installation

To set up the project locally, follow these steps:

1. Clone the repository:
- git clone https://github.com/svats125/Bankruptcy-Prediction.git
- cd Bankruptcy-Prediction


2. Install dependencies:
- pip install -r requirements.txt

## Usage

1. **News Extraction**:
- The news has been extracted from moneycontrol website(https://www.moneycontrol.com/). For that we need the company codes assigned by moneycontrol website to each of the companies. We extracted latest 20 news available for each and every company. For that we have used beautifulsoup and request library.

2. **Knowledge Graph**:
- For knowledge graph generation we have used REBEL model which will generate the triplets of head, tail and relation and these triplets will be used for knowledge graph embeddings generation.

3. **Knowledge Graph Embeddings**:
- For knowledge graph embeddings we have used one distance based model, i.e, TransE and another one Semantic based model, which is DistMult. For this we have used pykeen library to implement the same.

4. **Integration**
- We had 4 embeddings with us, entity and relation embeddings from both the models. Then, we inserted 4 more columns to our financial ratios dataset where in each new column average value of the embeddings are inserted to the single block.
