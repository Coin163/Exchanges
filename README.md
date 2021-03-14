# Coin163 Exchanges
The open api of coin163
API Documentation

you can use curl function to get API data. i.e


$url = 'https://api.coin163.org/v1/market/lists';

$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, $url);

curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, FALSE);

curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, FALSE);

curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);

$output = curl_exec($ch);

curl_close($ch);

$output = json_decode($output,true);

return $output;

Return all the Information about Coin163
GET,https://api.coin163.org/v1/market/info
```
{"success":true,"result":{"name":"Coin163","description":"Coin163 is a cryptocurrency exchange located in Vietnam. The most active trading pair on Coin163 exchange is ETH\/BTC. Coin163 is delivering the most reliable, fast and powerful platform solution on the market.It is established in year 2019.","location":"Vietnam","logo":"https:\/\/www.coin163.org\/Public\/Home\/images\/logo-200.png","website":"https:\/\/www.coin163.org","twitter":"https:\/\/twitter.com\/Coin163Org","telegram":"https:\/\/t.me\/Coin163_Community","email":"support@coin163.org"}}
```

Call: https://api.coin163.org/v1/market/lists ,get current market data
It will be returns last 24h trade data. Sample output:
```
{"success":true,"result":[{"market":"LINK_ETH","currency":"LINK","base":"ETH","volume":"8092.696000000000","high":"0.021654800000","low":"0.020729210000","price":"0.021567180000","average":"0.021567180000","percent":0.04274294844561007,"timestamp":1608347747,"url": "https://www.coin163.org/auction/exchange/LINK-ETH.html"},{"market":"LINK_USDT","currency":"LINK","base":"USDT","volume":"79436.762000000000","high":"14.117698210000","low":"13.446719510000","price":"14.018644130000","average":"14.018644130000","percent":0.047527485714684424,"timestamp":1608347747,"url": "https://www.coin163.org/auction/exchange/LINK-USDT.html"}]}
```

Get All Trade Pairs
Return all the trading pairs supported by Coin163 Market
Call:http://api.coin163.org/v1/market/pairs
```
{"success":true,"result":{"status":1,"message":"Success","combinations":[{"target":"LINK","base":"ETH","ticker_id":"LINK-ETH"},{"target":"LINK","base":"USDT","ticker_id":"LINK-USDT"},{"target":"OMG","base":"BTC","ticker_id":"OMG-BTC"}]}}
```

Get 24 Hours Trade Details
Return all the trade analytics in Coin163 Market
Call:http://api.coin163.org/v1/market/tickers
```
{"success":true,"result":[{"ticker_id":"LINK_ETH","url":"https:\/\/www.coin163.org\/auction\/exchange\/LINK-ETH.html","target_currency":"LINK","base_currency":"ETH","base_volume":"6623.647000000000","high":"0.016371840000","low":"0.015549560000","bid":"0.015693090000","ask":"0.015721350000","last_price":"0.016177850000"}]}
```


Call: https://api.coin163.org/v1/ticker/eth_usdt ,get current tick data
```
{"success":true,"result":{"volume":754,"high":"172.330000000000","low":"155.740000000000","average":4.932997347480105,"open":"155.740000000000","price":161.71652173913043,"timestamp":1594140778}}
```

Required parameters: market

Call: https://api.coin163.org/v1/orders/eth_usdt/500  ,get order book data
```
{"success":true,"result":{"buy":[{"price":"669.980200000000","amount":"13.000000000000","timestamp":"1608346929"},{"price":"669.107800000000","amount":"13.000000000000","timestamp":"1608346474"},{"price":"671.731800000000","amount":"10.000000000000","timestamp":"1608345492"},{"price":"668.225500000000","amount":"13.000000000000","timestamp":"1608346964"},{"price":"669.107800000000","amount":"15.000000000000","timestamp":"1608347312"},{"price":"667.369900000000","amount":"13.000000000000","timestamp":"1608346671"},{"price":"667.153300000000","amount":"9.000000000000","timestamp":"1608347303"},{"price":"668.949500000000","amount":"9.000000000000","timestamp":"1608345504"},{"price":"667.598100000000","amount":"16.000000000000","timestamp":"1608345438"},{"price":"667.598100000000","amount":"6.000000000000","timestamp":"1608346355"},{"price":"665.605800000000","amount":"1.000000000000","timestamp":"1608345474"},{"price":"670.578400000000","amount":"8.000000000000","timestamp":"1608345798"},{"price":"665.748700000000","amount":"12.000000000000","timestamp":"1608346413"},{"price":"665.402000000000","amount":"15.000000000000","timestamp":"1608346791"},{"price":"670.372000000000","amount":"5.000000000000","timestamp":"1608346332"}]}}
```

Required parameters: market, count (max: 500)

Call: https://api.coin163.org/v1/history/eth_usdt/500 ,get history transactions data
```
{"success":true,"result":[{"price":"669.980200000000","amount":"13.000000000000","total":8709.7426,"type":"buy","timestamp":"1608346929"},{"price":"666.564600000000","amount":"10.119000000000","total":6744.9671874000005,"type":"sell","timestamp":"1608346700"},{"price":"669.107800000000","amount":"13.000000000000","total":8698.4014,"type":"buy","timestamp":"1608346474"},{"price":"665.536500000000","amount":"12.115000000000","total":8062.974697500001,"type":"sell","timestamp":"1608345505"},{"price":"671.731800000000","amount":"10.000000000000","total":6717.318,"type":"buy","timestamp":"1608345492"}]}}
```



Required parameters: market, count (max: 10080) Parameter value range (5, 15, 30, 60, 360, 720, 1440, 10080)

Call: https://api.coin163.org/v1/chart/eth_usdt/500 ,get candles historical trades data

```
{"success":true,"result":[{"price":"669.980200000000","amount":"13.000000000000","total":8709.7426,"type":"buy","timestamp":"1608346929"},{"price":"666.564600000000","amount":"10.119000000000","total":6744.9671874000005,"type":"sell","timestamp":"1608346700"},{"price":"669.107800000000","amount":"13.000000000000","total":8698.4014,"type":"buy","timestamp":"1608346474"},{"price":"665.536500000000","amount":"12.115000000000","total":8062.974697500001,"type":"sell","timestamp":"1608345505"},{"price":"671.731800000000","amount":"10.000000000000","total":6717.318,"type":"buy","timestamp":"1608345492"},{"price":"665.468600000000","amount":"16.144000000000","total":10743.3250784,"type":"sell","timestamp":"1608347187"},{"price":"668.225500000000","amount":"13.000000000000","total":8686.9315,"type":"buy","timestamp":"1608346964"}]}}
```





			
