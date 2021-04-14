# Coinbase-API-project
## Dave Wisinski
## April 2021

### Task 1.1:
<em>Download a full day of production trade history for BTC/USD from exchange: Coinbase Pro - "https://docs.pro.coinbase.com". Endpoint: GET "/products/\<product-id>/candles" (make sure this is the raw trade data). Store the data in a DataFrame.

Produce a report for the dataset showing hourly bars of:
open, high, low, close, change, and trade volume.</em><br><br>

BTC/USD trade data for 4-13-2021 was obtainted from aforementioned endpoint and plotted in candlestick chart format using plotly library.

### Task 1.2:
<em>Download a full day of production trade history of ETH/BTC exchange: Coinbase Pro - "https://docs.pro.coinbase.com". Endpoint: GET "/products/\<product-id>/trades" (make sure this is the raw trade data). Store the data in a DataFrame.

Produce a report for ETH/BTC showing notional volume in USD.</em><br><br>

ETH/BTC tick (i.e. individual trade) data for 4-13-2021 was obtained from the aformentioned endpoint via iterative timed requests. Data was stored in DataFrames for manipulation and performing relevant calculations.

Note: All output data (.svg chart output and multiple .csv data outputs) is located in the output_data folder.

### Task 2:
<em>Describe how you would approach assessing the number of confirmations that a Digital Asset Exchange should wait before it considers a transaction (deposit to the exchange) in the BTC blockchain as valid in order to minimize the risk of being affected by a potential reorganization in the blockchain, but also not having a negative impact on the user experience (making the user wait for too long).

What measures, data and calculations would you look at to determine how many blockchain confirmations an exchange should wait when a client makes a BTC deposit before making the funds available for client to trade with?</em><br><br>

Response:<br>
In terms of assessing the number of required blockchain confirmations before determining validity of a customer BTC deposit, several factors should be considered, including:
- Notional value of the individual deposit (i.e. specific risk to the DAE) and aggregate notional value of pending deposits in a predefined timeframe (i.e. overall/systemic risk to the DAE). In general, if the DAE's risk is lower in relative terms, fewer confirmations may be considered acceptable.
- A probability of success (of a doublespend or reogranization attack) function which calculates the likelihood (probability) of a successful attack of either type based on metrics including concentrated proportion of total network hashrate and potential opportunity cost as measured by potential block reward vs. transaction value.
- A DAE should also consider industry standards/norms in order to provide a competitive service offering to the customer. For example, the current standard for required confirmations of BTC deposits at DAEs such as Coinbase and Gemini is three, therefore a DAE looking to remain competitive in the marketplace should consider requiring approximately the same number of confirmations.
- Other important considerations in determining a specified number of required confirmations for BTC deposits may include Bitcoin network traffic (i.e. time periods of greater volatiltiy may lead to greater activity and therefore slower transaction processing times) as well as the network's block difficulty and overall hashrate (which are positively correlated), though the latter would already be incorporated into the probability function discussed above.


