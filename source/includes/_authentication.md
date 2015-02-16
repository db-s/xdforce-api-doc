# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl --user "ACCOUNT_ID":"XDFORCE_API_KEY" "API_ENDPOINT"
```

> Make sure to replace `ACCOUNT_ID`, `XDFORCE_API_KEY` and `API_ENDPOINT` with your Account ID, API key and API endpoint respectively.

xDForce uses API keys to allow access to the API. You can register a new xDForce API key at our [developer portal](http://example.com/developers).

xDForce expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Basic ACCOUNT_ID:XDFORCE_API_KEY`

<aside class="notice">
You must replace `XDFORCE_API_KEY` with your personal API key.
</aside>