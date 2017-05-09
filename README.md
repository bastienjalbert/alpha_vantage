# alpha-vantage

[![Build Status](https://travis-ci.org/RomelTorres/alpha-vantage.png?branch=master)](https://travis-ci.org/RomelTorres/alpha-vantage)

*Python module to get stock data from the Alpha Vantage API*

Alpha Vantage delivers a free API for real time financial data and most used finance indicators in a simple json format. This module implements a python interface to the free API provided by Alpha
Vantage (http://www.alphavantage.co/). It requires a free API, that can be requested in their website.

## Install
```shell
git clone https://github.com/RomelTorres/alpha-vantage.git
cd alpha-vantage
python setup install
```

## Usage
To get data in a python, simply import the library and call the object with your api key and get ready for some awesome free realtime finance data.
```python
from alpha_vantage.alphavantage import AlphaVantage
av = AlphaVantage(key='YOUR_API_KEY')
# Get json object with the intraday data and another with  the call's metadata
data, meta_data = av.get_intraday('GOOGL')
```
Internally there is a retries counter, that can be used to minimize connection errors (in case that the api is not able to respond in time), the default is set to
3 but can be increased or decreased whenever needed.
```python
av = AlphaVantage(key='YOUR_API_KEY',retries='YOUR_RETRIES')
```
## Tests

In order to run the tests  (it takes sometime to run):
```shell
cd alpha-vantage
nosetests
```

## Coming soon:
1. ~~Add basic functionality: 0.0.1~~
2. ~~Add retry in order to allow the calls to be retried in case of failure: 0.0.2~~
3. Implement all functions described in the alpha vantage documentation 0.0.3
4. Re-factor functions to have an unified method for accessing the api 0.1.0
5. Add unit tests for all the function parameters in the module 0.1.1
6. Add pandas support through decorators 0.2.0