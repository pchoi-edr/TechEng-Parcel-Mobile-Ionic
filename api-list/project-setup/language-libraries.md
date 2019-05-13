# Project Language Libraries API

The Project Setup API is responsible for creating a new Project within Parcel.

## Available API Endpoints

The following endpoints are available in this API subsystem:

### <span style="background-color: #72b566; font-weight: bold; color: #ffffff; padding: 3px 10px; border-radius: 14px;">GET</span> **Language Libraries**

```text
/mobile/v1/project/language/libraries/{reportType}
```

This endpoint is accessible via the HTTP `POST` method. It
is responsible for authenticating supplied credentials and
issuing a time-limited access token. This token must then
be provided with every subsequent API request.

Note that this API endpoint **does not** conform to the typical
API request and response structures for the API. This
endpoint instead provides a simpler interface, since it is
meant to be invoked before any other tasks are performed via
the API.

#### Request

Request will require a Header

#### Header Parameters

| Header Parameter | Required | Type | Description |
| :--- | :--- | :--- | :--- |
| Authorization | Yes | String | Bearer Token : JWT |


##### Path Parameters

| Header Parameter | Required | Type | Description |
| :--- | :--- | :--- | :--- |
| reportType | Yes | String | Report Type : ex. PhaseI |

#### Body Parameters

This endpoint does not accept and URL body parameters.

#### Response

##### Expected HTTP Response Code

When operating normally, this API endpoint will return
an HTTP response code of `200` ("OK").

##### Body Parameters

If the supplied credentials are valid and an access token
is successfully generated, then the API response will
contain the following parameters in its top-level `data`
element:

| Response Parameter | Type | Description |
| :--- | :--- | :--- |
| libraryId | number | Library ID |
| name | String | Library Name |
| ownerCid | String | Company ID |
| siteType | String | Site Type |

##### Example JSON Response

Assuming a successful invocation of this endpoint, an OAuth2
bearer token will be generated in a response similar to the
following:

```json
{
    "response": {
        "code": 200,
        "timestamp": "2018-10-08T04:41:35.730Z"
    },
    "data": [
        {
            "libraryId": 1567,
            "name": "AAI/05 Beta Phase I Library",
            "ownerCid": 0,
            "siteType": "PhaseI"
        }, 
        {
            "libraryId": 1414,
            "name": "ASTM Phase I ‐ PARCEL Default",
            "ownerCid": 0,
            "siteType": "PhaseI"
        }, 
        {
            "libraryId": 1717,
            "name": "AAI/05 Beta Phase I Test",
            "ownerCid": 101,
            "siteType": "PhaseI"
        }
    ]
}
```
