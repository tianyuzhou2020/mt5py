# Mt5py
Trading bot by Python based on MT5 platform.
``` 
initial.py (open MT5)
mt5py.py define functions
autotrade.py trade bot
```
# Requirement Libraries
```
import MetaTrader5 as mt5
import mt5py as mp 
import pandas as pd
import talib
from time import sleep
from talib import MA_Type
```
# Functions
## Initial Account & Open MT5
```
setup(ID,password,server)   ID int password string server string
```
## Close Account
```
shutdown()
```
    
## Check Historical Data
```
historical_M5(name,number) #5 mins interval data
```
parameter：
  name forex-pair string
  number timesteps int
return：
  datetime ['open','high','low','close','tick_volume','spread','real_volume'],index = 'time'
else：
  historical_M1(name,number) #1min
  historical_M30(name,number) #30mins
  historical_H1(name,number) #1hour
  historical_D1(name,number) #1day
## Check Price on time
```
price_check(name) 
```
parameter：
  name forex-pair string
return：
  [bid price,ask price,time]
## Check Position
```
check_position()
```
Check if there is a position:
```
if len(mp.check_position()) == 0:
```
Check the type of position:
```
mp.check_position()['type'].values  #0 is long 1; 1 is short
```
## Check Order
```
check_order()
```
## Long at Market Price
```
buy_now(symbol,lot,sl=None,tp=None)
```
parameter:
    symbol: forex pair name
    lot: trading volume
    sl: stop loss
    tp: take profit
## Short at Market Price
```
sell_now(symbol,lot,sl=None,tp=None)
```
parameter:
    symbol: forex pair name
    lot: trading volume
    sl: stop loss
    tp: take profit
## Close the Long Position
```
close_long(name)
```
## Close the Short Position
```
close_short(name)
```
