# Introduction

## Fear and Greed Index
The [Fear and Greed Index](http://money.cnn.com/data/fear-and-greed/) is an investment tool by [CNN Money](money.cnn.com) used to measure the emotions driving the market.  It uses various market indicators to report a value representing investor sentiment.  Lower values indicate fear (Bear Market) while higher values indicate greed (Bull Market).  This can help predict when the market may swing in a given direction.

<sub>* The Fear and Greed Index are trademarks™ or registered® trademarks of CNN Money. Use of them does not imply any affiliation with or endorsement by them.<sub>

## The FGI API
This API can be used to retrieve the values of the Fear and Greed Index for a given date.  The value is an integer from 0 to 100 (inclusive) and is updated several times a day until the market closes.

For the most up-to-date data for the current day, please use refer to CNN's tool directly.  This API does not serve as a replacement for CNN's Fear and Greed Index website.

If anything is missing or seems incorrect, please check the [Github issues](https://github.com/leejustin/FGI-Tracker/issues) for existing known issues or [create a new issue](https://github.com/leejustin/FGI-Tracker/issues/new).

<aside class="warning">
This API is still in beta and may change without user notice.  The [Github Repository](https://github.com/leejustin/FGI-Tracker) will have the most recent updates!
</aside>

# Authentication

The API will be secured with an API key.  As it is still under development, the API can currently be accessed without an API key.

<aside class="warning">
Requests will stop working when the API key authentication is implemented.
</aside>

# Records

A record represents the value of the Fear Greed Index for a given date.

Dates are represented with the format:
`yyyy-mm-dd`

<aside class="notice">
Data is available starting from when the FGI-Tracker began collecting data. If no record exists for a given date, <code>null</code> will be returned for the value.
</aside>

## Get a List of Records

```shell
curl "https://fear-and-greed.leejustin.com/api/fgi/records?start=2017-09-20&end=2017-09-22"
```

> The above command returns JSON structured like this:

```json
[  
   {  
      "date":"2017-09-20",
      "value":79
   },
   {  
      "date":"2017-09-21",
      "value":73
   },
   {  
      "date":"2017-09-22",
      "value":71
   }
]
```

This endpoint returns a list of FGI records in the provided date range.

### HTTP Request

`GET https://fear-and-greed.leejustin.com/api/fgi/records`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
start | false | The lower bound of the date range.
end | false| The upper bound of the date range.

<aside class="success">
Remember — the `start` and `end` should be formatted per the `Records` date format!
</aside>

## Get a Specific Record

```shell
curl "https://fear-and-greed.leejustin.com/api/fgi/records/2017-10-4"
```

> The above command returns JSON structured like this:

```json
{
  "date":"2017-10-04",
  "value":91
}
```

This endpoint returns the FGI record for given date.

### HTTP Request

`GET https://fear-and-greed.leejustin.com/api/fgi/records/{date}`