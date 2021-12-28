# PYCMC

Coinmarketcap unofficial API wrapper, it can be used to easly create python applications that needs to contact with the API.

## How to use pycmc

Create a new wrapper with:

```
  wrapper = start(api_key = YOUR_CMC_API_KEY)
```
or if you want to use the sandbox enviroment:

```
  wrapper = start()
```

now you must take into account which API category you want to reach:

[API endpoints documentation](https://coinmarketcap.com/api/documentation/v1/#section/Endpoint-Overview)

![CMC API categories](/docs/cmcEndpoints.PNG)

for example, if you want to reach /cryptocurrency you need to call:

```
  wrapper.cryptocurrency()
```
this pattern repeats for all the categories:

```
  wrapper.exchange()
  wrapper.key()
  ...
```
>#### pymc v6 actually supports cryptocurrency, exchange and key

after that you need to access an endpoint of that category. To know all available endpoints go to the category documentation and choose the desired endpoint:

[API endpoints documentation](https://coinmarketcap.com/api/documentation/v1/#section/Endpoint-Overview)

![CMC API endpoints](/docs/cryptocurrenciesEndpoints.PNG)

For example if you want to acess /cryptocurrency/listings/latest you would need to do:

```
  wrapper.cryptocurrency().listings_latest()
```

It will return an object that contains all the information requested, the request does not have to be parsed by yourself.

the object will follow the schema provided by coinmarketcap API documentation about the response information organization.
