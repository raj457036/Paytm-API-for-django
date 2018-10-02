# Paytm-api-for-django
High performance with just plug and play feature. just put the app, tweak some settings and you are ready to go. good luck.

## Features

### Requirements
Python 3+
Django 2+

### Installation
step 1: clone this repo and paste it in your project directory
step 2: open **settings.py** file of your project and add **paytm** to **INSTALLED_APPS** paste the below settings

```python
# settings.py

INSTALLED_APPS = [
    .
    .
    .
    'paytm',
]

# other settings...

PAYTM_STAGING_URL = 'https://securegw-stage.paytm.in'
PAYTM_PRODUCTION_URL = 'https://securegw.paytm.in'

HOSTNAME = '127.0.0.1:8000'

if DEBUG:
    PAYTM_URL = PAYTM_STAGING_URL
else:
    PAYTM_URL = PAYTM_PRODUCTION_URL

PAYTM_MERCHANT_KEY = 'XXXXXXXXXXXX' # replace with original merchangt key
PAYTM_GATEWAY_SETTINGS = {
    'MID':'XXXXXXXXXXXXXXXXXXXX', # replace with original merchangt id or MID
    'INDUSTRY_TYPE_ID':'Retail',
    'WEBSITE':'APPSTAGING', # WEBSTAGING for websites -->> change this with production variables
    'CHANNEL_ID':'WAP', #WEB for websites
    'CALLBACK_URL':f'http://{HOSTNAME}/paytm/payment_response/',
```
step 3: Replace "XXXXX..." above with respective **merchant key** and **MID**

step 4: open urls.py and add
```python
#urls.py

urlpatterns = [
  #other urls ...
  path('paytm/', include('paytm.urls'))
]
```

step 4: Setup complete and you are good to go

### Test your api

 - run the server and go to **http://127.0.0.1:8000/paytm/test/**
 ![alt text](https://drive.google.com/file/d/10fX_hlb5PDQTXrC0aPeNRWi32IGy_Kz9/view?usp=sharing)
 - fill the details and test your api
 
#Any problem? raise an issue

###LICENCE
 - MIT
