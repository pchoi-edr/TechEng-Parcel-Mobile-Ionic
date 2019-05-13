# API Transfer Protocol

Requests and responses issued as part of the API are
transferred across the public Internet via the World Wide Web.
The requirements of this process are detailed in this section.

## Communication Protocols

Properly formatted API requests and responses are communicated
over HTTP (Hypertext Transfer Protocol), and are cryptographically
secured using TLS (Transport Layer Security). The `https` protocol
specifier is used within the API system's URLs instead of
`http` because of the presence of this encryption.

The API will issue HTTP response codes that are only
understood by HTTP 1.1-compliant user agents. As such, your
client application must be capable of communicating using
HTTP 1.1. 

## Authentication

Requests issued to the API are only acted upon if they
contain a token indicating that the sender has been
authenticated as a known client application registered with
Envision Health. These tokens expire after a certain amount of time,
so client applications must periodically re-authenticate with
the API system.

The authentication framework used by the API is OAuth2.
The details of the authentication process are described fully
in the [Authentication](authentication.md) section of this
document. 

## Character Encodings

The API uses Unicode code points encoded as UTF-8 for all
requests and responses. Its underlying system currently uses
three-byte encoding instead of the full four-byte encoding
necessary to represent all Unicode code points, so client
applications must not send code points above `U+FFFF`.

### Code Point Limitations

In technical terms, the API includes support for all
characters in Unicode's basic multilingual plane, but does
not support code points above this range (_i.e._ the
supplementary multilingual plane). Pragmatically, this
means that the majority of characters currently in common
use by most human languages is handled by the API, including
the most commonly used CJK (Chinese, Japanese, and Korean)
characters. However, less commonly used CJK characters are
unsupported, as are several historical scripts, various symbols
used in mathematics, and emoji.

If your client application accepts characters with code points
higher than `U+FFFF`, then these must be stripped or otherwise
transliterated into a valid code point range before they are
sent to the API.

Note particularly that any client application that allows
smart phone access (or that processes text that was originally
submitted via a smart phone) may more commonly experience
this issue, even if the client application is only localized
for languages fully supported by code points ≤ `U+FFFF`. This
is because emoji can readily be inputted via most smart
phones, and no emoji characters are currently supported by
the API. 

### Limitations on the Use of Unicode

Despite the presence of Unicode support in the API, certain
HTTP header values are required to be encoded in ASCII according
to web standards. For example, RFC 7231, section 3.1.1.1.
dictates that HTTP `Content-Type` headers must only contain
characters whose code points fall within range permitted by
seven-bit ASCII. Your application must respect all such
specifications when constructing HTTP requests.
