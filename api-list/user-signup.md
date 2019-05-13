# EDR Account Signup API

The EDR Account Signup API is responsible for handling the new account setup
for the mobile app. 

## Available API Endpoints

The following endpoints are available in this API subsystem:

### <span style="background-color: #ebb747; font-weight: bold; color: #ffffff; padding: 3px 10px; border-radius: 14px;">POST</span> **Login**

```text
/mobile/v1/user/signup
```

#### Request

##### Path Parameters

This endpoint does not accept URL path parameters.

##### Body Parameters

This endpoint accepts the following JSON-encoded parameters
as top-level attributes:

| Request Parameter | Required | Type | Description |
| :--- | :--- | :--- | :--- |
| edrAccount | Yes | String | Your EDR Account |
| edrPassword | Yes | String | Your password |
| firstName | Yes | String | Your first name |
| lastName | Yes | String | Your last name |
| emailAddress | Yes | String | Your email address |

##### Example JSON Request

A valid request to this endpoint would be structured as follows
(replacing the username and password with your actual values,
as appropriate):

```json
{
  "edrAccount": "{edr-account}",
  "edrPassword": "{password}",
  "firstName": "{first name}",
  "lastName": "{last name}",
  "emailAddress": "{email@domain.com}"
}
```

#### Response

##### Expected HTTP Response Code

When operating normally, this API endpoint will return
an HTTP response code of `201` ("OK").

##### Body Parameters

| Response Parameter | Type | Description |
| :--- | :--- | :--- |
| data | String |  |

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
    "data": []
}
```
