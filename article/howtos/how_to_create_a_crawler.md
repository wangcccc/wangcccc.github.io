---
title: How to create a crawler?
___

### How to use proxy in python requests?

    import requests

    response = requests.get("http://www.google.com", proxies={
        'http': 'http://127.0.0.1:1080',
        'https': 'http://127.0.0.1:1080'
    })

    print(response.text)

### How to set up proxy in Scrapy?

    

