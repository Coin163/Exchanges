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


It will be returns last 24h trade data. Sample output:
```
{"success":true,"result":[{"market":"ETH_USDT","currency":"ETH","base":"USDT","volume":"3719.480000000000","high":"172.330000000000","low":"155.740000000000","average":"161.7165217391304348","timestamp":1594139374}]}
```

Call: https://api.coin163.org/v1/ticker/eth_usdt,get current tick data
```
{"success":true,"result":{"volume":754,"high":"172.330000000000","low":"155.740000000000","average":4.932997347480105,"open":"155.740000000000","price":161.71652173913043,"timestamp":1594140778}}
```		
Required parameters: market

Call: https://api.coin163.org/v1/orders/eth_usdt/5,get order book data
```
{"success":true,"result":{"buy":[{"price":"143.000000000000","amount":"5.000000000000","timestamp":"1585903106"},{"price":"143.250000000000","amount":"1.000000000000","timestamp":"1585903363"},{"price":"143.000000000000","amount":"5.000000000000","timestamp":"1586008718"},{"price":"143.000000000000","amount":"0.100000000000","timestamp":"1586009019"}],"sell":[{"price":"143.250000000000","amount":"1.000000000000","timestamp":"1586002565"}]}}
```			
Required parameters: market, count (max: 100)

Call: https://api.coin163.org/v1/history/eth_usdt/5,get history transactions data
```{"success":true,"result":[{"price":"143.000000000000","amount":"5.000000000000","total":715,"type":"buy","timestamp":"1585903106"},{"price":"143.250000000000","amount":"1.000000000000","total":143.25,"type":"buy","timestamp":"1585903363"},{"price":"143.250000000000","amount":"1.000000000000","total":143.25,"type":"sell","timestamp":"1586002565"},{"price":"143.000000000000","amount":"5.000000000000","total":715,"type":"buy","timestamp":"1586008718"},{"price":"143.000000000000","amount":"0.100000000000","total":14.3,"type":"buy","timestamp":"1586009019"}]}
```			
Required parameters: market, count (max: 200)

Call: https://api.coin163.org/v1/chart/eth_usdt/5,get candles historical trades data
```{"success":true,"result":[{"price":"155.740000000000","amount":"38.000000000000","total":5918.120000000001,"type":"sell","timestamp":"1593615529"},{"price":"158.110000000000","amount":"59.000000000000","total":9328.490000000002,"type":"buy","timestamp":"1593615529"},{"price":"160.480000000000","amount":"47.000000000000","total":7542.5599999999995,"type":"sell","timestamp":"1593615529"}]}
```		

			
