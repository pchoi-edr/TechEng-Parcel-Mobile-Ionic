# Glossary

| Term | Definition |
| :--- | :--- |
| API | See "Application Programming Interface" |
| API Endpoint | The combination of a URL path and an HTTP method used to access a single function of the LOS API. For example, to create and update a draft service request, two separate API endpoints must be accessed. | 
| Application Programming Interface | A well-defined set of software interfaces designed to allow a program to interoperate with other programs. |
| C360 | See "Collateral 360" |
| Collateral 360 | EDR's workflow management software for managing real estate due diligence tasks. |
| Curl | A command-line application (invoked as `curl`) designed to perform requests using URLs. |
| Endpoint | See "API Endpoint" |
| JSON | An abbreviation for JavaScript Object Notation. This is a standard textual data format for representing complex data structures. It is defined at https://www.json.org/ |
| Loan Origination System | The software and computer system through which borrowers' requests for loans are processed by a lender. This system handles steps in this process up to (and sometimes including) disbursement of funds upon approval. |
| LOS | See "Loan Origination System" | 
| Service Request Form | A collection of data that identifies services to perform on one or more physical locations used as collateral for a loan. |
| SRF | See "Service Request Form" |
| URI | An abbreviation for Uniform Resource Identifier. Each URI uniquely identifies a resource using a standardized format. |
| URL | An abbreviation for Uniform Resource Locator. Each URL is a URI that specifies a resource's location according to the syntax defined in RFC 1738. Website addresses like `http://www.example.com/` are the most common form of URL, but other types exist (_e.g._ FTP addresses). |
| User Agent | A client application designed to connect to a Web server. Web browsers like Internet Explorer or Chrome are the most common types of user agents, but a client application that interfaces with the LOS API is also a user agent. |

## Glossary for Multi-Language Support
| Term | Definition |
| :--- | :--- |
| ASCII | An abbreviation for American Standard Code for Information Interchange. This is a character encoding where every character is represented in seven bits. Although designed in 1960 to support only the English language, for historical reasons ASCII was the most important character encoding until widespread adoption of the Unicode standard. |
| Basic Multilingual Plane | Unicode code points from `U+0000` to `U+FFFF` comprise the basic multilingual plane. Code points for most major world languages in current use reside here, though only the most common code points for CJK languages are in this range. |
| BOM | See "Byte Order Mark" |
| BMP | See "Basic Multilingual Plane." |
| Byte Order Mark | An optional character sequence whose presence at the beginning of a string of Unicode text identifies the order in which the bytes of any multi-byte character should be read (this will vary between big-endian and little-endian systems). The byte order mark can be used to distinguish between UTF-8, UTF-16, and UTF-32 encodings. |
| Case Folding | An operation that converts one alphabetic case to another (for example, uppercase to lowercase in the Latin alphabet used by the English language). Not all languages have the concept of alphabetic case, and in some languages case folding is not always reversible to obtain the original text. |
| Character | A single letter or symbol in a language. In Unicode, diacritics (such as accents diæreses, circumflexes, _etc._) are usually considered individual characters, but this varies by character set. |
| Character Encoding | A scheme for representing the code points of a character set digitally (_i.e._ how to store each code point as one or more bytes). |
| Character Set | A mapping of characters to their corresponding integer code points. |
| CJK | An abbreviation for "Chinese, Japanese, and Korean." This list of languages contains the major ideographic scripts in current use. |
| Code Point | An integer used to identify a single character in a character encoding. |
| Collation | An algorithm for comparing or sorting characters in a character set. |
| Emoji | A set of pictorial symbols defined as part of Unicode. These are most commonly used on smart phones. |
| i18n | An abbreviation for "internationalization" (indicating 18 characters excised from the middle of the word). |
| l10n | An abbreviation for "localization" (indicating 10 characters excised from the middle of the word). |
| SMP | See "Supplementary Multilingual Plane." |
| Supplementary Multilingual Plane | Unicode code points higher than `U+FFFF` comprise the supplementary multilingual plane. This includes less commonly used characters, including historical scripts, various mathematical symbols, and less frequently used characters in the CJK ideographic scripts. |
| Unicode | A standard character set containing most human languages and symbols in use, as well as historical scripts and emoji. Nearly all modern software that supports the input and display of multiple languages does so by supporting Unicode. |
| UCS | An abbreviation for Universal Coded Character Set. This is one of two character encoding schemes for Unicode (the other being UTF). The term "UCS" is usually suffixed by a number that indicates how many bytes are used to encode each code point. |
| UCS-2 | A character encoding scheme for Unicode where each code point is encoded in exactly two 8-bit bytes. This encoding cannot represent code points higher than `U+FFFF` (and therefore cannot represent any characters outside the basic multilingual plane). |
| UCS-4 | A character encoding scheme for Unicode where each code point is encoded in exactly four 8-bit bytes. |
| UTF | An abbreviation for Unicode Transformation Format. This is one of two character encoding schemes for Unicode (the other being UCS). The term "UTF" is usually suffixed by a number that indicates how many bits are used to encode each code point. | 
| UTF-8 | A character encoding scheme for Unicode where each character can be encoded in a variable number of 8-bit bytes. Code points 0 to 127 are compatible with ASCII. |
| UTF-16 | A character encoding scheme for Unicode where many code points are encoded in exactly two 8-bit bytes. Higher Unicode code points, however, are encoded in multiple adjacent two-byte UTF-16 units (called "surrogate pairs"). |
| UTF-32 | A character encoding scheme for Unicode where each code point is encoded in exactly four 8-bit bytes. |