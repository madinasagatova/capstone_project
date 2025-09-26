# Machine Learning Techniques and Large Language Models for Property Rental Price Prediction in Ireland  

## 📖 Overview  
This repository contains the implementation and supporting materials for my MSc Data Analytics Capstone Project at **CCT College Dublin**.   
The project investigates the potential of **LLM-based models** to improve the forecasting accuracy compared to **the traditional SARIMA model** and **the modern Prophet model** developed by Facebook for predicting rental prices in Ireland, with a focus on **Dublin quarterly rent data (2007–2024)**.
## 🎯 Research Objectives  
- To evaluate the effectiveness of **ML-based forecasting models** in predicting rental prices based on property features.  
- To assess the effectiveness of **LLMs** to improve prediction accuracy for rental price forecasting in Ireland.
- To provide **an analysis comparing forecasting ML models and LLM-based techniques** that explores how each method approaches the prediction task, the quality of insights they provide, and their suitability for various aspects of the Irish rental market.  

## 🗂 Dataset  
- **Source**: [Central Statistics Office (CSO) Ireland](https://data.cso.ie/table/RIQ02)  
- **Data**: Quarterly average rent prices from 2007 to 2024  
- **Features**: Average rent (€), quarter, number of bedrooms, property type, location  

## ⚙️ Methodology  
### Data Preprocessing  
- Handling missing values  
- Location filtering (focus on Dublin)  
- Time formatting (quarterly → datetime)  
- Outlier detection  
- Stationarity testing (ADF test)  
- Seasonal decomposition & autocorrelation analysis  

### Models Implemented  
- **SARIMA** (auto-tuned via `pmdarima`)  
- **Prophet** (with Fourier seasonality tuning) 
- **ChatGPT-3.5 & 4-turbo** (zero-shot & few-shot forecasting via OpenAI API)  
- **Time-LLM (GPT-2)** reprogramming framework  
- **Chronos (T5-small, T5-base, T5-large)** pre-trained time series models  

### Evaluation Metrics  
- Mean Squared Error (MSE)  
- Mean Absolute Error (MAE)  
- R² Score  
- Mean Absolute Percentage Error (MAPE)  

## 📊 Key Findings  
- **SARIMA** best captured seasonality and long-term structure.  
- **Prophet** performed robustly with tuned seasonal parameters.  
- **ChatGPT (few-shot)** achieved lowest point-wise error but failed to reproduce seasonality.  
- **Chronos** provided good short-term forecasts but degraded over longer horizons.  
- **Time-LLM (GPT-2)** was the weakest model, struggling with trend reproduction.  

## 🚀 How to Open & Run the Project  

### 1. Clone the Repository  
```bash
git clone https://github.com/madinasagatova/capstone_project.git
cd capstone_project 

### 2. Create & Activate a Virtual Environment (recommended)  
```bash
python3 -m venv venv
source venv/bin/activate   # On macOS/Linux
venv\Scripts\activate      # On Windows

### 3. Install Dependencies
```bash
pip install -r requirements.txt

### 4. Launch Jupyter Notebook
jupyter notebook

### 5. Then open Capstone_Madina_Sagatova_2021255_clean.ipynb file inside the folder.

### 6. (Optional) Run with OpenAI API
If you want to reproduce ChatGPT zero-/few-shot forecasts:
Create an OpenAI account and get an API key.
Add it as an environment variable:
export OPENAI_API_KEY="your_api_key_here"   # macOS/Linux
setx OPENAI_API_KEY "your_api_key_here"     # Windows
Run the LLMs.

## 📑 License
This project uses datasets from the CSO (Central Statistics Office) under the CC BY 4.0 license. The dataset for this research was downloaded from the CSO website using API, available at: https://data.cso.ie/table/RIQ02.

Code is provided under the MIT License.

GPT-2 (Radford et al., 2019) is open source, released under a modified MIT License, which permits unlimited usage for commercial and research purposes as long as proper acknowledgement is provided.   The license can be found at: 
https://github.com/openai/gpt-2/blob/master/LICENSE

GPT-3.5 and GPT-4-turbo (OpenAI, 2024): Proprietary LLMs, accessible through OpenAI's API and requires compliance with OpenAI’s licensing terms and citation in academic work.

Both the Amazon Chronos forecasting models and the NeuralForecast library to utilise the Time-LLM, used in this work are open source and licensed under the Apache License 2.0 (Apache, 2004). As long as the original license and copyright notices remain intact, this permissive license permits both personal and commercial use, modification, and redistribution of the software. These licensing conditions guarantee that the tools can be used in practical and academic projects while adhering to open-source standards. 

## 👩‍💻 Author
Madina Sagatova
MSc in Data Analytics, CCT College Dublin (2025)
