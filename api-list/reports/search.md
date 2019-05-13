# Reports Search API

The Reports Search API is responsible for searching existing reports within Parcel.

## Available API Endpoints

The following endpoints are available in this API subsystem:

### <span style="background-color: #ebb747; font-weight: bold; color: #ffffff; padding: 3px 10px; border-radius: 14px;">POST</span> **Reports Search**

```text
/mobile/v1/reports/search
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


##### Path Parameters

This endpoint does not accept and URL path parameters.

#### Body Parameters

This endpoint accepts the following JSON-encoded parameters
as top-level attributes:

| Request Parameter | Required | Type | Description |
| :--- | :--- | :--- | :--- |

#### Body Parameters : _siteInfo_

| Request Parameter | Required | Type | Description |
| :--- | :--- | :--- | :--- |
| paramID | Yes | number | Report Options ID |
| paramName | Yes | String | Report Param Name |
| paramField | Yes | String | Report Param Field Name |
| edrField | Yes | string | EDR Field Name |
| query | Yes | string | Query String: ex. 'test' |


##### Example JSON Request

A valid request to this endpoint would be structured as follows
(replacing the username and password with your actual values,
as appropriate):

```json
{
    "paramID": 1,
    "paramName": "Project Name",
    "paramField": "p.pName",
    "edrField": "project",
    "query": "test"
}
```

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
| siteId | Number | Site ID |
| address | String | Street Address |
| city | String | City |
| state | String | State |
| county | String | County |
| country | String | Country |
| zip | String | zip code |
| latitude | String | Latitude |
| longitude | String | Longitude |
| projectName | String | Project Name |
| shortName | String | Short Name |
| isEDROrder | Boolean | Is EDR Order |
| propertyGUID | String | Property GUID |

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
            "siteId": 13157,
            "address": "6120 Cowell Boulevard",
            "city": "Davis",
            "state": "CA",
            "county": "Yolo",
            "country": "US",
            "zip": "95616",
            "latitude": "32.982866",
            "longitude": "‐96.840228",
            "siteName": "Shade Tree Apartments",
            "projectName": " Demo Portfolio",
            "shortName": "PCA",
            "isEDROrder": true,
            "propertyGUID": "xxxxxxxx"
        }
    ]
}
```
