# Project Setup API

The Project Setup API is responsible for creating a new Project within Parcel.

## Available API Endpoints

The following endpoints are available in this API subsystem:

### <span style="background-color: #ebb747; font-weight: bold; color: #ffffff; padding: 3px 10px; border-radius: 14px;">POST</span> **Project Setup**

```text
/mobile/v1/project
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
| templateId | Yes | number | Template ID |
| siteType | Yes | String | Report Type |
| languageLibraryId | Yes | String | Language Library ID |
| accountId | Yes | number | Account ID : User ID |
| companyId | Yes | number | Company ID |
| siteInfo | Yes | Object | Site Info Envelop : reference siteInfo Parameters |
| propertyGUID | Yes | String | ??? |

#### Body Paramters : _siteInfo_

| Request Parameter | Required | Type | Description |
| :--- | :--- | :--- | :--- |
| projectName | Yes | String | Project Name |
| projectNumber | Yes | String | Project Number |
| siteName | Yes | String | Site Name |
| siteAddress | Yes | String | Site Address |
| siteCity | Yes | String | Site |
| siteState | Yes | String | Site |
| siteCounty | Yes | String | Site |
| siteZip | No | String | Site |
| siteCountry | No | String | Site |
| siteLatitude | No | number | Site |
| siteLongitude | No | number | Site |

##### Example JSON Request

A valid request to this endpoint would be structured as follows
(replacing the username and password with your actual values,
as appropriate):

```json
{
   "templateId": 604,
   "siteType": "PhaseI",
   "languageLibraryId": 1567,
   "accountId": 2663,
   "companyId": 1218,
   "siteInfo":  {
      "projectName": "Mobile Test Project 1",
      "projectNumber": "12345",
      "siteName": "Mobile Test 1",
      "siteAddress": "800 West Cummings Park",
      "siteCity": "Woburn",
      "siteState": "MA",
      "siteCounty": "Middlesex",
      "siteZip": "01801",
      "siteCountry": "USA",
      "siteLatitude": 42.49683,
      "siteLongitude": ‐71.12628
    },
   "propertyGUID": “123456”
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
| projectID | number | New Project ID |

##### Example JSON Response

Assuming a successful invocation of this endpoint, an OAuth2
bearer token will be generated in a response similar to the
following:

```json
{
    "response": {
        "code": 201,
        "timestamp": "2018-10-08T04:41:35.730Z"
    },
    "data": {
        "projectID": 123456
    }
}
```
