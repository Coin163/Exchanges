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
{"success":true,"result":[{"market":"LINK_ETH","currency":"LINK","base":"ETH","volume":"8092.696000000000","high":"0.021654800000","low":"0.020729210000","price":"0.021567180000","average":"0.021567180000","percent":0.04274294844561007,"timestamp":1608347747},{"market":"LINK_USDT","currency":"LINK","base":"USDT","volume":"79436.762000000000","high":"14.117698210000","low":"13.446719510000","price":"14.018644130000","average":"14.018644130000","percent":0.047527485714684424,"timestamp":1608347747},{"market":"OMG_BTC","currency":"OMG","base":"BTC","volume":"0.000000000000","high":"0.000000000000","low":"0.000000000000","price":"0.000000000000","average":"0.000000000000","percent":"0.000000000000","timestamp":1608347747},{"market":"OMG_ETH","currency":"OMG","base":"ETH","volume":"33112.580000000000","high":"0.005173080000","low":"0.004981870000","price":"0.005110770000","average":"0.005110770000","percent":0.03696250589590724,"timestamp":1608347747},{"market":"OMG_USDT","currency":"OMG","base":"USDT","volume":"121558.100000000000","high":"3.354119540000","low":"3.232351580000","price":"3.324528370000","average":"3.324528370000","percent":0.036304001258106657,"timestamp":1608347747}]}
```

Call: https://api.coin163.org/v1/ticker/eth_usdt ,get current tick data
```
{"success":true,"result":{"volume":754,"high":"172.330000000000","low":"155.740000000000","average":4.932997347480105,"open":"155.740000000000","price":161.71652173913043,"timestamp":1594140778}}
```		
Required parameters: market

Call: https://api.coin163.org/v1/orders/eth_usdt/500  ,get order book data
```
{"success":true,"result":{"buy":[{"price":"669.980200000000","amount":"13.000000000000","timestamp":"1608346929"},{"price":"669.107800000000","amount":"13.000000000000","timestamp":"1608346474"},{"price":"671.731800000000","amount":"10.000000000000","timestamp":"1608345492"},{"price":"668.225500000000","amount":"13.000000000000","timestamp":"1608346964"},{"price":"669.107800000000","amount":"15.000000000000","timestamp":"1608347312"},{"price":"667.369900000000","amount":"13.000000000000","timestamp":"1608346671"},{"price":"667.153300000000","amount":"9.000000000000","timestamp":"1608347303"},{"price":"668.949500000000","amount":"9.000000000000","timestamp":"1608345504"},{"price":"667.598100000000","amount":"16.000000000000","timestamp":"1608345438"}
]}```
Required parameters: market, count (max: 100)

Call: https://api.coin163.org/v1/history/eth_usdt/5  ,get history transactions data
```{"success":true,"result":[{"price":"143.000000000000","amount":"5.000000000000","total":715,"type":"buy","timestamp":"1585903106"},{"price":"143.250000000000","amount":"1.000000000000","total":143.25,"type":"buy","timestamp":"1585903363"},{"price":"143.250000000000","amount":"1.000000000000","total":143.25,"type":"sell","timestamp":"1586002565"},{"price":"143.000000000000","amount":"5.000000000000","total":715,"type":"buy","timestamp":"1586008718"},{"price":"143.000000000000","amount":"0.100000000000","total":14.3,"type":"buy","timestamp":"1586009019"}]}
```			
Required parameters: market, count (max: 200)

Call: https://api.coin163.org/v1/chart/eth_usdt/5 ,get candles historical trades data
```{"success":true,"result":[{"price":"155.740000000000","amount":"38.000000000000","total":5918.120000000001,"type":"sell","timestamp":"1593615529"},{"price":"158.110000000000","amount":"59.000000000000","total":9328.490000000002,"type":"buy","timestamp":"1593615529"},{"price":"160.480000000000","amount":"47.000000000000","total":7542.5599999999995,"type":"sell","timestamp":"1593615529"}]}
```		

			
