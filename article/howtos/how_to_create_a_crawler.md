---
title: How to create a crawler?
---

### How to use proxy in python requests?
```python
import requests

response = requests.get("http://www.google.com", proxies={
    'http': 'http://127.0.0.1:1080',
    'https': 'http://127.0.0.1:1080'
})

print(response.text)
```

### How to set up proxy in Scrapy?
In settings.py add middleware config.
```python
DOWNLOADER_MIDDLEWARES = {
    'scrapy.downloadermiddlewares.httpproxy.HttpProxyMiddleware': 1
}
```
 Set the environment variable http_proxy, https_proxy.

    C:\>set http_proxy=http://proxy:port
    csh% setenv http_proxy http://proxy:port
    sh$ export http_proxy=http://proxy:port

    C:\>set https_proxy=https://proxy:port
    csh% setenv https_proxy https://proxy:port
    sh$ export https_proxy=https://proxy:port
    
# mongodb

    db.pornpics.updateMany({}, {$set:{favorite:false}})

# pymongo
```python
from pymongo import MongoClient

client = MongoClient('localhost', 27017)
db = client.db_name
collection = db.collection_name

# insert
collection.insert_one(data)
# get total documents
count = collection.count_documents({})
# search by pattern
query = {
    "field_name": {
    "$regex": '^pattern.*',
    "$options" :'i' # case-insensitive
    }
}
docs = collection.find(query)
```
