# Handling Errors

Unless a catastrophic error occurs, Parcel Mobile API responses should
always contain an HTTP response status code indicating success.
Any errors encountered by the API server will be identified by
the value of the API response's `responseCode` datum in its
top-level `meta` element, which will be equal to an HTTP
response status code that describes the error that occurred.

### Field References in Error Attributes

