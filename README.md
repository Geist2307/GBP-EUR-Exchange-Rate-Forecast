# Forecasting exchange rates with RNN's and ARIMA - comparison

## Motivation

Analysis and experiments for finding good RNN's for predicting the EUR-GBP exchange rate based on historic data. I use the Jupyter Notebook to keep track of changes, explore the data, and experiment with building and fine-tuning an RNN model. I use  ARIMA for baseline comparison. 
<p>

I am looking at about 6000 instances of historic data from the [European Central Bank](https://www.ecb.europa.eu/stats/policy_and_exchange_rates/euro_reference_exchange_rates/html/eurofxref-graph-gbp.en.html) on the exchange rate between the Euro (EUR) and the Great Britain Pound (GBP), and also at Gross Domestic Product data from the [Office for National Statistics](https://www.ons.gov.uk/economy/grossdomesticproductgdp/datasets/contributionstomonthlygdp).

</p>

## Goal

<p>

The main goal is to analyze, and model the fluctuations in the exchange rate with SARIMA and RNN's, to see if we can get good results in predicting the exchange rate based only on patterns in historic data and record any observations along the way. 

</p>

<p>

RNN is a model of low _interpretability_, as many calculations are done in each layer, and layers are usually connected by activation functions. So it is difficult to intepret the parameters of the model. ARIMA, on the other hand, has a clear meaning for its model parameters. Comparing the two can reveal good trade-offs in performance/interpretability. 
</p>

## Workflow

<p>
 
 The workflow consists of several stages :


<ul>

1. Exploratory data analysis: this looks at trends in the data, and also looks at correlations on annual data between GDP and exchange rates
2. Forecasting with ARIMA: builts an Auto-Regressive model for the time series representing the EUR/GBP exchange rate
3. Forecasting with RNN : builts and evaluates a Recursive Neural Net for predicting the values of the exchange rates
4. Compare models and internally validate the model : Which model is better? Is a simpler model (ARIMA) more succesfull than a more complex one (RNN)

</ul>

## Technology

The analysis together with building, fine-tuning and testing the models is done with Python libraries in a Jupyter Notebook.

</p>

- The code is written in **Python 3.11.6**, 
- I use **Tensorflow v 2.16** for building RNN's
- For EDA, I use **Pandas**
- For Visualisation, **Matplotlib** and **Seaborn**
- For statistical analysis, and ARMA model, I use **Statsmodels**

