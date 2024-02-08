Forecasting exchange rates is an interesting problem for businesses and banks. There are various ways in which one could model the problem, which include analysing all factors that might impact the exchange rate (unemployment, gross domestic product), or looking at historical data to find hidden patterns within the data - for some more discussion, this [post](https://fxopen.com/blog/en/7-common-ways-to-forecast-currency-exchange-rates/#:~:text=Comparing%20economic%20conditions%20in%20two,direction%20of%20a%20pair's%20rate.) offers some interesting ideas.

<p>
In this project, I aim to explore the predictive power of deep learning and machine learning. So, I chose to look at historical data from the [ECB](https://www.ecb.europa.eu/stats/policy_and_exchange_rates/euro_reference_exchange_rates/html/eurofxref-graph-gbp.en.html) on the exchange rate between the Euro (EUR) and the Great Britain Pound (GBP), and also at Gross Domestic Product data from the [Office for National Statistics](https://www.ons.gov.uk/economy/grossdomesticproductgdp/datasets/contributionstomonthlygdp). One very important assumption when predicting time series based on past behaviour, is that _relationships established in the past do not change_. This is the reason why such models hold only in the absence of external events that can affect the underlying assumptions (economic crises, changes in trade relationships invalidate the model). Hence, despite much historical data, predictions can be made only by considering relatively _stable_ periods, not marked by major changes. 

</p>

<p>

One very important aspect is to identify the purpose of the model. In this project, I do not aim to uncover the mechanism that leads to the values of the exchange rate, but simply use a predictive model that allows for reliable forecasts (low generalization error) if there is no change in the circumstances that underping the value of the exchange rate. Hence, this model works well with relatively small fluctuations in the exchange rate for set periods of time where _nothing happens_ to disturb said assumptions. 

</p>

<p>

Equally important, is that the RNN is a model of low _interpretability_, as many calculations are done in each layer, and layers are usually connected by activation functions. So it is difficult to intepret the parameters of the model, which makes the RNN more like a black box. ARIMA, on the other hand, has a clear meaning for its model parameters.
</p>

<p>
The associated Jupyter Notebook shows my code and my reasoning step by step, and it mainly looks to understand patterns in the data itself, to make predictions. I took four steps in this analysis:

<ul>

1. Exploratory data analysis: this looks at trends in the data, and also looks at correlations on annual data between GDP and exchange rates
2. Forecasting with ARIMA: builts an Auto-Regressive model for the time series representing the EUR/GBP exchange rate
3. Forecasting with RNN : builts and evaluates a Recursive Neural Net for predicting the values of the exchange rates
4. Compare models and internally validate the model : Which model is better? Is a simpler model (ARIMA) more succesfull than a more complex one (RNN)

</ul>

</p>

All in all, this was a fun project that allowed me to build a RNN model and compare it with a more traditional ARIMA forecasting tool. Based on the interval validation, it turns out ARIMA outperforms the RNN, however, thanks to the influx of new data (ECB updates their pages with new values for the exchange rate), the model can be externally validated and its performance tracked on new data.

<p>

In this repo, the files are :

- a Jupyter Notebook, fully annonated, that shows all steps for this end-to-end project 
- data from the ECB and OFN (as explained above)

</p>