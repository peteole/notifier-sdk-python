# openapi-client
No description provided (generated by Openapi Generator https://github.com/openapitools/openapi-generator)

This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 0.2.2
- Package version: 0.2.2
- Build package: org.openapitools.codegen.languages.PythonClientCodegen

## Requirements.

Python >=3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/peteole/notifier-sdk-python.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/peteole/notifier-sdk-python.git`)

Then import the package:
```python
import openapi_client
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import openapi_client
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
import openapi_client
from pprint import pprint
from openapi_client.api import crate_api
from openapi_client.model.add_channel_body import AddChannelBody
from openapi_client.model.get_telegram_chat_id_body import GetTelegramChatIdBody
from openapi_client.model.remove_channel_body import RemoveChannelBody
from openapi_client.model.send_notification_body import SendNotificationBody
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = openapi_client.Configuration(
    host = "http://localhost"
)



# Enter a context with an instance of the API client
with openapi_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = crate_api.CrateApi(api_client)
    add_channel_body = AddChannelBody(
        user_id="user_id_example",
        service_username="service_username_example",
        service_id="service_id_example",
    ) # AddChannelBody | 

    try:
        # Add channel
        api_instance.handle_add_channel(add_channel_body)
    except openapi_client.ApiException as e:
        print("Exception when calling CrateApi->handle_add_channel: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *http://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*CrateApi* | [**handle_add_channel**](docs/CrateApi.md#handle_add_channel) | **POST** /add_channel | Add channel
*CrateApi* | [**handle_get_telegram_chat_id**](docs/CrateApi.md#handle_get_telegram_chat_id) | **POST** /get_telegram_chat_id | Get the chat ID of a telegram username
*CrateApi* | [**handle_notify**](docs/CrateApi.md#handle_notify) | **POST** /notify | Send notification
*CrateApi* | [**handle_remove_channel**](docs/CrateApi.md#handle_remove_channel) | **POST** /remove_channel | Remove channel


## Documentation For Models

 - [AddChannelBody](docs/AddChannelBody.md)
 - [GetTelegramChatIdBody](docs/GetTelegramChatIdBody.md)
 - [RemoveChannelBody](docs/RemoveChannelBody.md)
 - [SendNotificationBody](docs/SendNotificationBody.md)


## Documentation For Authorization

 All endpoints do not require authorization.

## Author




## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in openapi_client.apis and openapi_client.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from openapi_client.api.default_api import DefaultApi`
- `from openapi_client.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
import openapi_client
from openapi_client.apis import *
from openapi_client.models import *
```

