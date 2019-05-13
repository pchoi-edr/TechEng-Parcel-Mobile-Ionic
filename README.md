# API Introduction

Data Warehouse Volume API...

## The RESTful Architecture

API requests follow a RESTful design, with appropriate usage of HTTP
methods (_i.e._ verbs) that match the type of operation being performed.
As used by the Parcel Mobile API system, this means the following:

| HTTP Method | Meaning in the RESTful Architecture |
| :--- | :--- |
| `GET` | Retrieve a resource (or information about a resource). |
| `POST` | Create a new resource. |
| `PUT` | Replace an existing resource. Depending on the API, a `PUT` request for a nonexistent resource may result in the creation of that resource. |
| `DELETE` | Delete a resource. |
| `PATCH` | Modify an existing resource. |

## Exceptions to RESTful Principles

Note that the length of most URLs is limited in practice, despite the HTTP
1.1 specification not requiring such a limit. The maximum length of a URL
may depend not only upon the server processing the request, but also on
the user agent from which a client performs an HTTP request. For example,
in common Web browsers the URL is typically limited to a few kilobytes in
length.

## API Endpoint Descriptions

The first set of APIs available to integration developers is the API product.

* Authentication OAuth2 (login) - provides and access token

Available API endpoints are as follow:

### EDR Account Login

EDR Account Login is a one time authentication process to stage the mobile app and verify EDR ACcount status.

### login

Login API accepts a json payload containing a username and password. Upon successful authentication a JWT (json web token) is returned to use for authenticating against all other API calls. Token expires after 7 days.

### Uer SignUp

Creates a new user account. Verification and account information is emailed to the account email address used in the sign-up.

### Project 

Creates a new Project. 





