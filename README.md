# Insuring_Insurance_Payments

#Leith Bakhit 

In order for a Life Insurance company to continuously grow their assets at a set minimum ROR, they need to account for Policy Premiums, company expenses, and Death Benefit Payouts. By creating an optimal portfolio based on sharpe ratios, volatility, and predicted returns; we’re able to make sure the company in question is able to insure their death benefit payouts even if they double in a certain year or if their premium payments were significantly cut. We used sharpe ratios to select 1 ETFs per sector to represent the broader asset classes and then used machine learning to predict future pricing and to optimize the portfolio. We used an LSTM model to predict the future pricing for the selected ETFs getting an idea of future volatility and prices. Using a lookback period of 45 days, we were able to predict 90 days of returns(graphs shown on Presentation slides 9-10). Next we used the Efficient Frontier portfolio to optimize our ETF weights, finding an adequate return for the companies while still keeping the risk at a minimum shown on slide 12.  
  
#Feng Zhang
	
Data preparation: Data pulling from Alpaca with ETFs daily price and auditing the data to see if there are duplicates, missing data points and determining the time frame.  
Model selection: We are focusing on two methodologies: Random forest and LSTM. 
We take nasdaq100(QQQ) as an example to compare the two models. After building up two machine learning models, we got the price perdition curves. As a result, we ended up using the LSTM model. There are two reasons: 1. We take 75% as train, and 25% as test, LSTM performs more close to the actual than Random forest. 2. LSTM has a higher accuracy than Random forest.


#Umme Arusha

The objective of our assignment was to build a model and investing algorithm to meet a targeted rate of return with the least amount of risk. Funding will come from premiums of life insurance policies, business expenses will be accounted for. 

As a member of this project, I contributed to the project in the following ways 
Initial research on different ways of building the model. I shared my findings with my team members which helped us to decide how we want to proceed to build the tool.
After making a decision as a team that we will use Sharpe Ratio to identify the list of potential ETFs, I built a python script to calculate the Sharpe Ratio of a list of selected ETFs from historical data. The output of the script helped us to decide which ETFs we should consider for the next stage to build a model.
I also helped with improving the optimizer script by locating that Real estate was missing from the list and the allocation of funds was better diversified after Real estate was added.


#Jeff Berger

In order to feed the engine for deriving the optimal allocation, we needed to project future prices of our selected ETFs. We did this by training an LSTM model using historical daily close prices over the last 10 years, then having the model predict the next 90 days worth of prices. (we referenced our model off the article referenced in the URL in the Jupyter notebook). Using only one input, we built a single layer LSTM model. The prices were predicted by feeding in the previous 45 days of prices as part of the Look Back period. We also used the timesereiesenerator from Keras which helps us create intervals of prices while taking into account their sequential order. Pairing this with the prediction_generator gave us batched outputs.  We tried feeding in more than 45 days but it started to adjust the accuracy of our model. We also had trouble projecting more than 90 days as the further we tried to look ahead the more unreliable the predictions became. The 45 day look back and the 90 projection ended up being the furthest we could push out in either direction while maintaining the integrity of the model.

#Alex Domenick

The objective of our project was to provide life insurance companies with an optimal asset allocation for seven different asset classes that are common investments in the industry (these being; Corporates, Municipals, Commodities, Treasuries, Equities, MBS and Real Estate).  

The ultimate allocation percentages would be based on recent ETF price data from each asset class.  To start, our group chose around three large ETFs for each asset class, then calculated the sharpe ratios for each.  The ETFs with the highest sharpe ratio by asset class were chosen to represent historical returns for its respective asset class.

Next, Historical ETF returns were used to train a Long short-term memory (LSTM) deep learning model and predict 90 days of forward returns.  Our group experimented with a couple of additional ML models including the random forest model.  LSTM proved to be the best predictor of ETF returns.

The predicted returns were inputted into randomly generated portfolios of varying asset weights to find the portfolio with the highest sharpe ratio, our methodology for optimal portfolio allocation.  By generating this analysis we were able to construct an efficient frontier graph for the set of randomly generated portfolios.  While our group worked together on much of the project and helped each other with coding issues, this optimal portfolio analysis portion was my main contribution to the project.  I started with a set of functions from the website referenced in my jupyter notebook (thanks Faith for sending the link!!!!) and updated them to incorporate our dataset.  For 25,000 different portfolios, random asset class weightings collectively totaling 1 were generated.  The portfolio return and standard deviations were calculated with another function to determine sharpe ratios.  The final function plots the returns and volatility (standard deviations) to show the efficient frontier graph, and shows an allocation output for the highest sharpe ratio portfolio.

