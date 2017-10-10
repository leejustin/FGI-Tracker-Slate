# Errors

The FGI API uses the following error codes:

```bash
```
> 400 responses will include an error message like this:

```json
{
  "message":"Invalid date format."
}
```

Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request sucks! The JSON response will tell you what's wrong.
401 | Unauthorized -- Your API key is invalid.
403 | Forbidden -- The request is reserved for administrators.
404 | Not Found -- Make sure your endpoint is correct!
429 | Too Many Requests -- You're making too many requests!
500 | Internal Server Error -- We had a problem with our server. Try again later.
