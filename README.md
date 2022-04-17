# Portfolio_Analysis
*Portfolio Analysis* is a quantitative analysis risk management processes visualized through a serie of different metrics based on performance, volatility, risk, risk-return profile for portfolio diversification. The analyser processes given dataframe of assets from a data file (.csv) comparing them to the market.
Currently being developed as part of a UCBerkeley Bootcamp.

---

## Requirements

This application was writen in Jupyter Lab 3.3.2 using Python 3.9.7

**Operating System:**
* Window 10 (or higher) using Gitbash.
* MacOS 10.14 (or higher) using a terminal.
* Linux Ubuntu 20.04 (or higher) using a terminal.

**Will need to be installed:**

*jupyter lab* 3.3.2
```
$ pip install jupyterlab
```

*numpy* 1.22.3
```
$ pip install numpy
```

*pandas* 1.4.2

```
$ pip install pandas
```

*pathlib* 1.0.1

```
$ pip install pathlib
```

*matplotlib* 0.1.3

```
$ pip install matplotlib
```
---

## Installation

To install the application you will need to clone the GitHub repository.

```
$ git clone https://github.com/yanickw/Portfolio_Analysis
```

---

## Get Started

Using the *Portfolio Analysis*:

Open a gitbash, navigate to your github cloned repositery. Start *Jupyter Lab*
```
$ jupyter lab
```

### 1. Import the Data
Once the Jupyter Lab application running, you will need to link your dataframe (.csv) accessed from a relative path location in the /Resources folder.

```
# Import the data by reading in the CSV file and setting the DatetimeIndex.
<name of dataframe> = pd.read_csv(Path("./Resources/<new file>.csv"),
                           index_col = "<date column name>",
                           parse_dates = True,
                           infer_datetime_format = True)
```

### 2. Analyze the Volatility
Graph vizualisation method uses matplotlib library using a plot. 

```
# Plot of the daily return data of the 4 funds and the S&P 500.
ax = daily_returns_df["<name of asset_01 column>"].plot(figsize = (25,10), title = "<title of your graph>")

daily_returns_df["<name of asset_02 column>"].plot(ax=ax)
daily_returns_df["<name of market column>"].plot(ax=ax)

ax.legend(["<name of asset_01 column>","<name of asset_02 column>","<name of market column>"])

```

### 3. Analyze the Risk
Uses the Pandas `std` to calculate the annualized standard deviation and 21-day rolling window for each of the assets and for the market to evaluate risk.

### 4. Analyze the Risk-Return Profile
Use the daily return DataFrame to calculate the annualized average return data for each of the assets and for the market based on a 252 trading days for the year.
Calculate the Sharpe ratios to find which of the assets offers the best risk-return profile?

### 5. Diversify the Portfolio
Calculates the variance of the market by using a 60-day rolling window.
Calculates the covarianceand and the Beta.
Calculate the average value of the 60-day rolling beta of the assts using the `.mean` function to find which asset is more sensitive to the movement of the market.

---

## Contributors

This application originated from a Berkeley Bootcamp.

For any inquieries, feedbacks or comments about this project please email me at yanickw@gmail.com

I can also be reached on [LinkedIn](https://www.linkedin.com/in/yanickwilisky/)
or  [Twitter](https://twitter.com/yanickwilisky).

---

## License

MIT License

Copyright (c) 2022 Yanick Wilisky

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
