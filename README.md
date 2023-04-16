# Forex_Real-time-ETL
This system collects price data from Polygon every six minutes and uses it to inform investment decisions through a portfolio class. The system includes several classes for data analysis and investment management.

## Tools Used

- Python
- Polygon API
- SQLite

## Raw Price Data Collection

The raw price data is collected from Polygon and stored in an SQLite database. Every six minutes, a query is run to calculate the mean value and standard deviation of the data, and these values are stored in a separate table. The raw data is then flushed.

## Return Class

The return class takes the average price as an input and calculates the return based on the previous return value stored in the class. The class also keeps three different running sums: one for calculating the moving average of the return, one for the standard deviation of the return, and one for the average standard deviation of the return. The class includes built-in functions for calculating the moving average, standard deviation, and average standard deviation of the returns.

## Portfolio Class

The portfolio class is instantiated once per currency pair and keeps track of current investments and available money. The class includes built-in functions for buying and selling, as well as logic to check if transactions can be made. The portfolio class uses data from the return class to inform investment decisions.

## Main Loop

The main loop of the system runs approximately every six minutes and includes an aggregate_raw_data_tables function. This function calculates the necessary data and makes investment decisions based on the data collected by the return and portfolio classes.
