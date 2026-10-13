# cryptotracker.py
script for tracking live feed of market prices of stocks and stablecoins in crypto
import json
from urllib.request import urlopen
print("my crypto tracker")
crypto_portfolio = 3562.57
holdings = ["solana", "etherium", "xrp", "bnb"] 
solana_quantity = 2 
etherium_quantity = 7 
xrp_quantity = 2
bnb_quantity = 1 
etherium_value = 2699.42 * etherium_quantity
xrp_value = 1.42 * xrp_quantity
bnb_value = 751.27 * bnb_quantity
url = "https://api.coingecko.com/api/v3/simple/price?ids=solana&vs_currencies=usd"
with urlopen(url, timeout=10) as response:
    prices = json.load(response)
solana_price = prices["solana"]["usd"]
solana_value = solana_quantity * solana_price
total_value = solana_value + etherium_value + xrp_value + bnb_value
print()
print("Portfolio summary")
print("------------------")
print("solana value:", solana_value)
print("etherium value:", etherium_value)
print("xrp value:", xrp_value)
print("bnb value:", bnb_value)
print("total portfolio value:", total_value)

