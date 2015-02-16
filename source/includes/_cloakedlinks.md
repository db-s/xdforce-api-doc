# Cloaked Links

## Create Cloaked Links (Single)

Users can create cloaked links with single url through this endpoint.

### HTTP Request

`POST /api/v1/monitors/<ID>/cloakedlinks/single`

> The above command returns JSON structured like this:

```json
{
    "ok": true,
    "message": "Cloaked Link created successfully",
    "cloaked_link_type": "single",
    "cloaked_link": {
        "_id": "133L0CQ9Ke02",
        "_rev": "1-357f38bfd244ad481a2682e653693cc8",
        "type": "Link",
        "monitorId": "12zu0CELWG01",
        "created": "1423861731407",
        "name": "Sample Cloaked Link with Single URL",
        "active": true,
        "targetUrls": [],
        "urlRotationIdx": 0,
        "targetUrl": "http://hello.world.com"
    }
}
```

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
name | String | Name of the Cloaked Link
targetUrl | String | Desired URL for cloaking

<aside class="notice">
mismatchRedirectUrl and dangerRedirectUrl will only be available to the users with premium/upgraded plans.
</aside>

## Create Cloaked Links (A/B Test)

Users can create cloaked links with A/B testing through this endpoint.

### HTTP Request

`POST /api/v1/monitors/<ID>/cloakedlinks/abtest`

> The above command returns JSON structured like this:

```json
{
    "ok": true,
    "message": "Cloaked Link created successfully",
    "cloakedLinkType": "abtest",
    "cloakedLink": {
        "_id": "133L0CQ9Ke01",
        "_rev": "1-12585a4ae2419818a3b9d4f7f60b1fef",
        "type": "Link",
        "monitorId": "12zu0CELWG01",
        "created": "1423860909012",
        "name": "Sample Cloaked Link with A/B Test",
        "active": true,
        "targetUrls": [
            {
                "url": "http://example.com",
                "weight": 100
            },
            {
                "url": "http://example.in",
                "weight": 150
            }
        ],
        "urlRotationIdx": 0,
        "visibleUrl": "http://localhost:3003/l/133L0CQ9Ke01"
    }
}
```

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
name | String | Name of the Cloaked Link
targetUrls1 | String | First URL for A/B Testing
targetUrlsWeight1 | String | Ratio of first URL
targetUrls2 | String | Second URL for AB Testing
targetUrlsWeight2 | String | Ratio of second URL


## List all Cloaked Links

Users can show list of cloaked links associated with a monitor through this endpoint.

### HTTP Request

`POST /api/v1/monitors/<ID>/cloakedlinks`

> The above command returns JSON structured like this:

```json
{
    "ok": true,
    "cloakedLinks": [
        {
            "_id": "14530CU5SA01",
            "_rev": "1-e87270226ba9b3277813f7ddcbb7b89e",
            "type": "Link",
            "monitorId": "12zu0CELWG01",
            "created": "1424095509651",
            "name": "Sample Cloaked Link 1",
            "active": true,
            "targetUrl": "http://example.com/",
            "urlRotationIdx": 0,
            "visibleUrl": "http://localhost:3003/l/14530CU5SA01"
        },
        {
            "_id": "16AO0CU8Kn01",
            "_rev": "2-c5718567543c60876f1f644f1504052a",
            "type": "Link",
            "monitorId": "12zu0CELWG01",
            "created": "1424098278269",
            "name": "Sample Cloaked Link 2",
            "active": true,
            "targetUrls": [
                {
                    "url": "http://clink3a.com",
                    "weight": 50
                },
                {
                    "url": "http://clink3b.com",
                    "weight": 40
                }
            ],
            "urlRotationIdx": 0,
            "visibleUrl": "http://localhost:3003/l/16AO0CU8Kn01"
        }
    ]
}
```

> If an invalid monitor id is given:

```json
{
    "ok": false,
    "message": "Invalid monitor id"
}
```

## Fetch a Cloaked Link

Users can view a cloaked link associated with a monitor through this endpoint.

### HTTP Request

`POST /api/v1/monitors/<MONITOR_ID>/cloakedlinks/<CLOAKEDLINK_ID>`

> The above command returns JSON structured like this:

```json
{
    "ok": true,
    "cloakedLink": {
        "_id": "16AO0CU8Kn01",
        "_rev": "2-c5718567543c60876f1f644f1504052a",
        "type": "Link",
        "monitorId": "12zu0CELWG01",
        "created": "1424098278269",
        "name": "Sample Cloaked Link 2",
        "active": true,
        "targetUrls": [
            {
                "url": "http://clink3a.com",
                "weight": 50
            },
            {
                "url": "http://clink3b.com",
                "weight": 40
            }
        ],
        "urlRotationIdx": 0,
        "visibleUrl": "http://localhost:3003/l/16AO0CU8Kn01"
    }
}
```

> If an invalid monitor id is given:

```json
{
    "ok": false,
    "message": "Invalid monitor id"
}
```

> If an invalid cloaked link id is given:

```json
{
    "ok": false,
    "message": "Invalid cloaked link id"
}
```

## Edit Cloaked Links (Single)

Users can edit cloaked links with single url through this endpoint.

### HTTP Request

`PUT /api/v1/monitors/<MONITOR_ID>/cloakedlinks/single/<CLOAKEDLINK_ID>`

> The above command returns JSON structured like this:

```json
{
    "ok": true,
    "message": "Cloaked Link updated successfully",
    "cloakedLinkType": "single",
    "cloakedLink": {
        "_id": "133L0CQ9Ke02",
        "_rev": "2-f342f01b44468226bf406e75cccdfe7d",
        "type": "Link",
        "monitorId": "12zu0CELWG01",
        "created": "1423861731407",
        "name": "CLink Single 1",
        "active": true,
        "targetUrl": "http://example.com/",
        "urlRotationIdx": 0,
        "visibleUrl": "http://localhost:3003/l/133L0CQ9Ke02"
    }
}
```

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
targetUrl | String | Website address to add as cloaked link


## Edit Cloaked Links (A/B Test)

Users can edit cloaked links with A/B Test through this endpoint.

### HTTP Request

`PUT /api/v1/monitors/<MONITOR_ID>/cloakedlinks/abtest/<CLOAKEDLINK_ID>`

> The above command returns JSON structured like this:

```json
{
    "ok": true,
    "message": "Cloaked Link updated successfully",
    "cloakedLinkType": "abtest",
    "cloakedLink": {
        "_id": "133L0CQ9Ke02",
        "_rev": "2-f342f01b44468226bf406e75cccdfe7d",
        "type": "Link",
        "monitorId": "12zu0CELWG01",
        "created": "1423861731407",
        "name": "CLink Single 1",
        "active": true,
        "targetUrls": [
            {
                "url": "http://clinksingle1a.com",
                "weight": 60
            },
            {
                "url": "http://clinksingle1b.com",
                "weight": 40
            }
        ],
        "urlRotationIdx": 0,
        "visibleUrl": "http://localhost:3003/l/133L0CQ9Ke02"
    }
}
```

### Query Parameters

Parameter | Type | Description
--------- | ------- | -----------
targetUrls1 | String | First URL for A/B Testing
targetUrlsWeight1 | String | Ratio of first URL
targetUrls2 | String | Second URL for AB Testing
targetUrlsWeight2 | String | Ratio of second URL


## Delete a Cloaked Link

Users can delete a cloaked link with A/B Test through this endpoint.

### HTTP Request

`DELETE /api/v1/monitors/<MONITOR_ID>/cloakedlinks/<CLOAKEDLINK_ID>`

> The above command returns JSON structured like this:

```json
{
    "ok": true,
    "message": "Cloaked Link deleted successfully"
}
```