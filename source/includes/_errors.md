# Errors

The Candide Marketplace API uses the following error codes:

| Error Code | Meaning                                                                                           |
| ---------- | ------------------------------------------------------------------------------------------------- |
| 400        | <u>Bad Request</u><br/>Your request is invalid.                                                   |
| 401        | <u>Unauthorized</u><br/>Your API key is wrong.                                                    |
| 403        | <u>Forbidden</u><br/>You are not authorized to view this resource.                                |
| 404        | <u>Not Found</u><br/>The specified record or records could not be found.                          |
| 405        | <u>Method Not Allowed</u><br/>You tried to access a resource with an invalid method.              |
| 406        | <u>Not Acceptable</u><br/>You requested a format that isn't json.                                 |
| 410        | <u>Gone</u><br/>The records requested has been removed from our servers.                          |
| 429        | <u>Too Many Requests</u><br/>You're requesting too many records!                                  |
| 500        | <u>Internal Server Error</u><br/>We had a problem with our server. Try again later.               |
| 503        | <u>Service Unavailable</u><br/>We're temporarily offline for maintenance. Please try again later. |
