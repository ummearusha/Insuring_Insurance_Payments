# Insuring_Insurance_Payments

(Further details can be found here - https://github.com/ummearusha/Insuring_Insurance_Payments/blob/main/Insuring%20Insurance%20Payments.pptx)

The objective of our project was to provide life insurance companies with an optimal asset allocation for seven different asset classes that are common investments in the industry (these being; Corporates, Municipals, Commodities, Treasuries, Equities, MBS and Real Estate).  

The ultimate allocation percentages would be based on recent ETF price data from each asset class.  To start, our group chose around three large ETFs for each asset class, then calculated the sharpe ratios for each.  The ETFs with the highest sharpe ratio by asset class were chosen to represent historical returns for its respective asset class.

Next, Historical ETF returns were used to train a Long short-term memory (LSTM) deep learning model and predict 90 days of forward returns.  Our group experimented with a couple of additional ML models including the random forest model.  LSTM proved to be the best predictor of ETF returns.

The predicted returns were inputted into randomly generated portfolios of varying asset weights to find the portfolio with the highest sharpe ratio, our methodology for optimal portfolio allocation.  By generating this analysis we were able to construct an efficient frontier graph for the set of randomly generated portfolios.  While our group worked together on much of the project and helped each other with coding issues, this optimal portfolio analysis portion was my main contribution to the project.  I started with a set of functions from the website referenced in my jupyter notebook (thanks Faith for sending the link!!!!) and updated them to incorporate our dataset.  For 25,000 different portfolios, random asset class weightings collectively totaling 1 were generated.  The portfolio return and standard deviations were calculated with another function to determine sharpe ratios.  The final function plots the returns and volatility (standard deviations) to show the efficient frontier graph, and shows an allocation output for the highest sharpe ratio portfolio.


