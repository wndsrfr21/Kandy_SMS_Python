
import requests
import json

domain_key = "DAKe7ad9232e18s1410ca92d8gf11gc62da2"
domain_api_secret = "DAE3269ef1b585e41c1bdb5a0fc65e3e1f4"
user_id = "user1"

r = requests.get("https://api.kandy.io/v1.2/domains/users/accesstokens?key="+domain_key+"&domain_api_secret="+domain_api_secret+"&user_id="+user_id)
data = r.json()
UserToken = data['result']['user_access_token']
#print(UserToken)
#print("part2.......")
Url = "https://api.kandy.io/v1.2/users/devices?key=" + UserToken
r = requests.get(Url)
data = r.json()
DeviceId = data['result']['devices'][0]['id']
#print(data)
#print("--------")
#print(DeviceId)
#print("part3.......")
Url = "https://api.kandy.io/v1.2/devices/smss?device_id=" + DeviceId + "&key=" + UserToken
#!!!!!!!!!!!!!! 
# For the next line - change the destination phone number
# !!!!!!!!!!!!!
DataString = {
    "message": {
        "source": "+14443338888",
        "destination": "+14443338888",
        "message": {
            "text": "KandySMS - Hello Alex!!"
        }
    }
}

Headers = {
    "Content-Type":"application/json"
}

r = requests.post(Url, headers=Headers, data=json.dumps(DataString))
#status = r[u'body'])[u'user_access_token']
data = r.json()
#DeviceId = data['result']['devices'][0]['id']
#print(data)
#print("--------")
#print(data)
#print("--------")
#print(Url)
