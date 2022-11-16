# About The Project
### Why?
###### This was a project where me and my friends trying to develop a strategy which creates automatic entries to generate a passive income. The initial form of the project was too complex and long. Raw binance API is used for requests and can cause problems.
###### In this version **binanceapi**, a python module about binance transactions, is used.

### Additional Information
###### All orders are in future orders with 20x leverage.
###### This project requires a webhook connection with *TradingView*. It is not really complicated, create an alarm in TradingView, then connect it with the API inside the project. 
###### We used discord notifications to track all entries. It is not necessary, but It may help. 

# Structure
###### The project consists of 3 main parts.

### Webhook
###### This part has an API to catch POST requests for TradingView alarms. The data is collected and transformed to a proper format. `app.py` contains all necessary structures.
###### This webhook URL is required in Tradingview Alarm.

### Binance 
###### The main logic of this section is to take the data from webhook, process it according to coins, balance, entry type, prices etc. and to open the entry, long or short. This operation is same for all users registered.
###### In `users.py`, a user object is defined. Every user has their unique `token` and `id` attributes. Every instance has a `method` to create orders. And there is a `@classmethod` named `new_order_for_all()` to open the entry for all users.

