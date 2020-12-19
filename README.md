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
{"success":true,"result":[{"market":"ETH_USDT","currency":"ETH","base":"USDT","volume":"3719.480000000000","high":"172.330000000000","low":"155.740000000000","average":"161.7165217391304348","timestamp":1594139374}]}
			

			
