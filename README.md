Fork of https://github.com/vsjha18/nsetools
=======================
Changes
  * ETF live data fetching

Installation
  * mkdir stock_watch
  * cd stock_watch
  * git clone https://github.com/ask1234560/nsetools.git
  * python3 -m venv environment
  * pip install -r nsetools/requirements.txt
 
Example Script
```
import json
from nsetools import Nse

nse = Nse()

indexesQ = ['NIFTY 50', 'NIFTY NEXT 50', 'INDIA VIX']
etfQ = ["NIFTYBEES", "JUNIORBEES"]

outputETFs = []
outputIndexes = []

for q in etfQ:
    jd = json.loads(nse.get_etf_quote(q, as_json=True))
    items = [q, jd.get("pChange"), jd.get("change"), jd.get("lastPrice")]
    outputETFs.append(items)

for q in indexesQ:
    jd = json.loads(nse.get_index_quote(q, as_json=True))
    items = [q, jd.get("pChange"), jd.get("change"), jd.get("lastPrice")]
    outputIndexes.append(items)

print(*outputIndexes, "*"*100, *outputETFs, sep="\n")
```
 



Project Page
=============
http://nsetools.readthedocs.io

Updates
=========

To stay updated please subscribe to google group https://groups.google.com/forum/#!forum/nsetools

nsetools
========

Python library for extracting realtime data from National Stock Exchange (India)

Introduction.
============

nsetools is a library for collecting real time data from National Stock Exchange (India). It can be used in various types of projects which requires getting live quotes for a given stock or index or build large data sets for further data analytics. You can also build cli applications which can provide you live market details at a blazing fast speeds, much faster that the browsers. The accuracy of data is only as correct as provided on www.nseindia.com.

Main Features:
=============

* Getting live quotes for stocks using stock codes.
* Return data in both json and python dict and list formats.
* Getting quotes for all the indices traded in NSE, e.g CNX NIFTY, BANKNIFTY etc.
* Getting list of top losers.
* Getting list of top gainers.
* Helper APIs to check whether a given stock code or index code is correct.
* Getting list of all indices and stocks.
* Cent percent unittest coverage.

Dependencies
=============
To keep it simple and supported on most of the platforms, it uses only core python libraries, hence there are no external dependencies. It can be used out of box and absolutely not set up is required except an internet connection.

Detailed Documenation 
=====================

For complete documenation, please refer http://nsetools.readthedocs.io
