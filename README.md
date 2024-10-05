# spamAPI

to run this app:
```
cd spamAPI
pip install -r requirements.txt
python app.py
```

note: using python -V 3.11.5

---
### Doker

build and run with docker-compose.yml
```
docker-compose build
docker-compose up
```
note: running on port: 5000

pull it from " https://hub.docker.com/r/bossryut/backendspam "

or run following command
```
docker pull bossryut/backendspam
```
---
### API url
deployed with GCP Cloud Run " https://spambackend-644030095619.asia-east1.run.app/predict "

example to test with python :
```python
import requests
url = "https://spambackend-644030095619.asia-east1.run.app/predict"
#for local host : url = "http://127.0.0.1:5000/predict"
try:
    msg = {'message':str(input('message : '))}
    r = requests.post(url, json = msg)
    print(r.json())
except:
    print('error')
```

note: support only post method
