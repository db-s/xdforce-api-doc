## Cloaked Links Statistics

Users can view stats on the cloaked links through this endpoint.

### HTTP Request

`GET /api/v1/monitors/<MONITOR_ID>/cloakedlinks/<CLOAKEDLINK_ID>/stats`

> The above command returns JSON structured like this:

```json
{
    "ok": true,
    "stats": {
        "pageStats": {
            "http://localhost:3003/l/133L0CQ9Ke01": {
                "totalHitsOfExits": 3,
                "totalTimeOfExits": 90.571,
                "totalHitsInTimePeriod": 3,
                "exits": 3,
                "entries": 3,
                "bounces": 3,
                "bounceRate": "100.00%",
                "avgHits": "1.00",
                "avgTime": "30s"
            }
        },
        "hasNoPageStats": false
    }
}
```

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
startDate | String | The start date of the time period for statistics. The format should be: MM-DD-YYYY
endDate | String | The end date of the time period for statistics. The format should be: MM-DD-YYYY
pageUrls | String | The url or urls of target pages / website address
